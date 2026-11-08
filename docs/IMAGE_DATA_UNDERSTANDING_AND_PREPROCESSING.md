# Image data understanding and preprocessing — practical reference

## 1. Understand the dataset before training

For each dataset, record:
- number of images and class counts;
- file formats, dimensions, channels and color mode;
- missing/corrupt files and duplicate images;
- class-to-index mapping;
- train/validation/test split provenance;
- image source, annotation method and license.

Never split after augmentation. Split at the patient/person/video/source level where related images could otherwise leak across partitions.

## 2. Pixel and image formulas

**Min–max scaling for 8-bit pixels**

\[
x' = \\frac{x}{255}, \\qquad x\\in[0,255],\\quad x'\\in[0,1]
\]

**Per-channel standardization**

\[
x'_c=\\frac{x_c-\\mu_c}{\\sigma_c+\\epsilon}
\]

Estimate mean and standard deviation from training data only. For pretrained networks, use the exact preprocessing expected by the chosen weights.

**Image tensor shapes**
- PIL / OpenCV image: typically `(H,W,C)`.
- TensorFlow default: `(N,H,W,C)` (NHWC).
- PyTorch convolution input: `(N,C,H,W)` (NCHW).

**Convolution output size**

\[
H_{out}=\\left\\lfloor\\frac{H+2P-D(K-1)-1}{S}+1\\right\\rfloor
\]

where (K) is kernel size, (S) stride, (P) padding and (D) dilation.

**Class imbalance**

\[
w_c=\\frac{N}{C\\,n_c}
\]

where (N) is the number of training samples, (C) number of classes and (n_c) count for class (c). Use training counts only.

## 3. Image treatment workflow

1. Decode and verify image files.
2. Convert color mode deliberately (RGB/BGR/grayscale).
3. Inspect dimensions and aspect ratio.
4. Resize with an appropriate interpolation method.
5. Normalize consistently.
6. Apply label-preserving augmentation only to training images.
7. Check visual examples before fitting.
8. Cache/prefetch when the data pipeline and memory budget permit.

### Interpolation choices
- RGB photos: bilinear or bicubic for resizing.
- Downsampling: area interpolation can preserve aggregate appearance.
- Segmentation masks / categorical labels: nearest-neighbour only.
- Do not apply independent geometric transforms to image and mask; use the same sampled transform.

### Common augmentation
- Horizontal flip, crop, small rotation, brightness/contrast jitter.
- Domain constraints matter: flips can change text, traffic signs, laterality, medical orientation or directional labels.
- Never assume augmentation is valid without inspecting samples and task semantics.

## 4. Evaluation and leakage

- Train: fit parameters.
- Validation: choose architecture, hyperparameters and checkpoint.
- Test: final estimate after all decisions are frozen.
- Classification: accuracy + macro-F1 + per-class precision/recall + confusion matrix.
- Detection: mAP at documented IoU thresholds.
- Segmentation: Dice and IoU, with background handling stated.
- Report seeds, splits, versions, hardware and compute budget.

## 5. Useful quality-control code

```python
from pathlib import Path
from PIL import Image
from collections import Counter
root=Path("data/homer_bart_2/training_set")
counts=Counter()
bad=[]
for cls in sorted(p for p in root.iterdir() if p.is_dir()):
    for p in cls.rglob("*"):
        if p.suffix.lower() in {".jpg",".jpeg",".png",".bmp"}:
            try:
                with Image.open(p) as im:
                    im.verify()
                counts[cls.name]+=1
            except Exception:
                bad.append(str(p))
print("Class counts:",counts)
print("Corrupt files:",bad[:20], "total:",len(bad))
```

## 6. Further reading

- TensorFlow image classification: https://www.tensorflow.org/tutorials/images/classification
- TensorFlow data performance: https://www.tensorflow.org/guide/data_performance
- PyTorch data loading: https://pytorch.org/tutorials/beginner/basics/data_tutorial.html
- torchvision transforms: https://pytorch.org/vision/stable/transforms.html
- OpenCV image processing: https://docs.opencv.org/
