# Datasets and external assets inventory

This document distinguishes datasets confirmed by notebook code from external archives that are merely referenced. The repository does not automatically contain every dataset.

| Dataset / asset | Original or modern notebook | Source / path evidence | Status |
|---|---|---|---|
| Homer/Bart ZIP | Original CNN and transfer learning | Google Drive paths ending in `Datasets/homer_bart_2.zip` | Referenced, not committed here |
| MNIST | Original autoencoder and GAN lessons | `tf.keras.datasets.mnist` / framework loaders | Public framework dataset download |
| Fashion-MNIST | Original convolutional autoencoder | `tf.keras.datasets.fashion_mnist` | Public framework dataset download |
| CIFAR-10 | New modern classification/transfer lessons | Keras / torchvision download APIs | Public framework dataset download |
| Face images / recognition assets | Original face notebooks | External notebook paths and outputs need audit | Not yet fully inventoried |
| Pose model assets | Original gesture/action notebook | OpenPose Caffe model/config referenced | External; verify version and license |
| DeepDream model/input | Original DeepDream notebook | Large notebook not fully retrieved | Not yet inventoried |
| OpenCV sample files | Original OpenCV notebook | Large notebook not fully retrieved | Not yet inventoried |

## Expected Homer/Bart folder structure

```text
Datasets/
└── homer_bart_2.zip
    └── homer_bart_2/
        ├── training_set/
        │   ├── bart/
        │   └── homer/
        └── test_set/
            ├── bart/
            └── homer/
```

The path in the original CNN notebook is `/content/drive/MyDrive/Computer Vision Masterclass/Datasets/homer_bart_2.zip`; transfer learning uses another Drive folder spelling. The archive should be copied to a consistent local path, e.g. `data/homer_bart_2.zip`, and extracted to `data/homer_bart_2/`.

## Verify a ZIP before training

```python
from pathlib import Path
from zipfile import ZipFile
archive = Path("data/homer_bart_2.zip")
assert archive.exists(), f"Missing dataset: {archive}"
with ZipFile(archive) as z:
    bad = z.testzip()
    print("ZIP integrity:", "OK" if bad is None else f"bad member: {bad}")
    members = z.namelist()
    print("Files:", len(members))
    print("\\n".join(members[:30]))
```

Do not extract untrusted archives without checking paths and size. Check archive contents, class counts, file integrity, provenance and license. Never commit personal/private datasets or credentials. A similarly named Kaggle dataset is not proof that it is the exact historical ZIP.
