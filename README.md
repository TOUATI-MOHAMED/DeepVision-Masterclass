# DeepVision Masterclass

A notebook-first computer vision teaching repository. The original notebooks remain intact in the repository root. The **Modern Series** adds updated, reproducible examples using current TensorFlow/Keras and PyTorch APIs.

## Modern computer vision series

Start here: [Modern series index](notebooks/modern/README.md).

| Notebook | Topic | Framework |
|---|---|---|
| [00 — TensorFlow + PyTorch comparison](notebooks/modern/Modern_Deep_Learning_Computer_Vision_TensorFlow_PyTorch.ipynb) | Comparable CNN classifiers, metrics and confusion matrices | TensorFlow + PyTorch |
| [01 — CNN image classification](notebooks/modern/01_CNN_Image_Classification_CIFAR10_PyTorch.ipynb) | CIFAR-10, CNN, training loop, evaluation and checkpoint | PyTorch |
| [02 — Augmentation and regularization](notebooks/modern/02_Data_Augmentation_and_Regularization.ipynb) | Augmentation, dropout, weight decay, mixup | PyTorch + Keras |
| [03 — Transfer learning](notebooks/modern/03_Transfer_Learning_ResNet50_TensorFlow_PyTorch.ipynb) | ResNet50 feature extraction and fine-tuning | TensorFlow + PyTorch |
| [04 — Autoencoders](notebooks/modern/04_Autoencoders_Image_Compression_TensorFlow_PyTorch.ipynb) | Dense and convolutional autoencoders | TensorFlow + PyTorch |
| [05 — GANs](notebooks/modern/05_GANs_DC_GAN_MNIST_PyTorch.ipynb) | DCGAN on MNIST | PyTorch |
| [06 — Object detection](notebooks/modern/06_Object_Detection_Torchvision_FasterRCNN.ipynb) | Faster R-CNN, boxes, labels and custom dataset contract | PyTorch |
| [07 — Semantic segmentation](notebooks/modern/07_Semantic_Segmentation_U_Net_PyTorch.ipynb) | U-Net, masks, Dice and IoU | PyTorch + Keras guidance |
| [08 — Vision Transformers](notebooks/modern/08_Vision_Transformers_Transfer_Learning.ipynb) | ViT-B/16 transfer learning and patch tokens | PyTorch |

## Getting started

1. Create a clean Python environment (Python 3.10 or 3.11 recommended; check framework support for your platform).
2. Install a matching PyTorch/torchvision build for your CPU/CUDA/ROCm setup using the [official PyTorch selector](https://pytorch.org/get-started/locally/).
3. Install TensorFlow separately if you plan to run the TensorFlow notebooks, following the [official TensorFlow installation guide](https://www.tensorflow.org/install).
4. Install notebook and evaluation dependencies: `python -m pip install jupyterlab numpy matplotlib scikit-learn pillow scikit-image`.
5. Launch JupyterLab from the repository root: `jupyter lab`.

Framework packages are deliberately not pinned to speculative future versions. Use the official install selectors for a compatible combination of Python, OS, accelerator and framework release.

## Original material and audit status

The original notebooks are preserved and are not overwritten. See [the original notebook audit](docs/ORIGINAL_NOTEBOOK_AUDIT.md) for what was inspected and what still requires a complete cell-by-cell review. Large notebooks with embedded outputs/assets may exceed the GitHub content retrieval limit; this is stated rather than treating them as reviewed.

## Datasets and responsible use

- MNIST and CIFAR-10 are loaded through Keras/torchvision dataset utilities.
- Object detection and segmentation notebooks define dataset interfaces; users must supply correctly annotated, licensed datasets.
- Homer/Bart data referenced by the legacy notebooks may have been stored in private Google Drive locations. Do not assume a public archive is identical or redistributable; verify provenance, contents and license.
- Never commit private datasets, personal images/videos, model weights or credentials without permission.
- This modernization does not change the repository's existing license or the licenses of third-party datasets and pretrained weights.

## Validation

Notebook JSON and code syntax should be checked before execution. Full training, accelerator compatibility, remote dataset downloads and end-to-end metric reproduction are not claimed unless explicitly recorded in the validation notes. See [validation and limitations](docs/VALIDATION_AND_LIMITATIONS.md).
