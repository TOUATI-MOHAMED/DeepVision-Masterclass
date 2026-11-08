# Datasets directory

This folder documents the expected location of data files; private or third-party datasets are intentionally not committed.

## Homer/Bart original archive

Expected archive name from the original Colab notebooks:

```text
Datasets/homer_bart_2.zip
```

For local execution, place a lawfully obtained copy at `data/homer_bart_2.zip` and extract to:

```text
data/homer_bart_2/
├── training_set/
│   ├── bart/
│   └── homer/
└── test_set/
    ├── bart/
    └── homer/
```

The original CNN notebook used the Google Drive path:
`/content/drive/MyDrive/Computer Vision Masterclass/Datasets/homer_bart_2.zip`.

The transfer-learning notebook used a different Drive path spelling:
`/content/drive/MyDrive/Cursos - /Computer Vision Masterclass/Datasets/homer_bart_2.zip`.

These paths identify the archive reference, not an archive included in Git. Verify ZIP integrity, class counts, duplicate images, file dimensions, provenance and license before training. Do not commit the ZIP unless redistribution is explicitly permitted.

## Public benchmark datasets

- MNIST: downloaded by TensorFlow/Keras or torchvision.
- Fashion-MNIST: downloaded by TensorFlow/Keras or torchvision.
- CIFAR-10: downloaded by torchvision in the modern PyTorch track.

See [the dataset inventory](../docs/DATASETS_AND_ASSETS.md) and [image preprocessing guide](../docs/IMAGE_DATA_UNDERSTANDING_AND_PREPROCESSING.md).
