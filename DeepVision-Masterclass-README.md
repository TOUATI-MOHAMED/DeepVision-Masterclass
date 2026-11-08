# DeepVision Masterclass — Repository guide

This file is the detailed guide to the repository. The original Google Colab notebooks are preserved in the repository root. The modern curriculum is now split into independent framework tracks.

## Recommended entry points

- [Modern curriculum index](notebooks/modern/README.md)
- [TensorFlow / Keras track](notebooks/modern/tensorflow/README.md)
- [PyTorch track](notebooks/modern/pytorch/README.md)
- [Original Colab notebook catalogue](notebooks/original_colab/README.md)
- [Annotated original notebooks](notebooks/original_colab/annotated/)
- [Dataset and asset inventory](docs/DATASETS_AND_ASSETS.md)
- [Image data understanding and preprocessing article](docs/IMAGE_DATA_UNDERSTANDING_AND_PREPROCESSING.md)
- [TensorFlow version audit](docs/TENSORFLOW_VERSION_AUDIT.md)

## Learning scope

Image processing, CNN classification, transfer learning, autoencoders, GANs, object detection, semantic segmentation, Vision Transformers, face analysis, pose/action recognition and DeepDream.

## Framework separation

The new lessons are separated into TensorFlow/Keras and PyTorch folders. Each track has its own README, environment instructions, lessons and separate exercise solutions. Use separate Python environments to avoid dependency conflicts.

## Original Colab material

Original notebooks remain at repository root with their existing Colab badges. Numbered catalogue O00–O09 is provided in `notebooks/original_colab/README.md`. Three historical notebooks have annotated copies with explanations of their original APIs, datasets, preprocessing and known pitfalls. The source originals are unchanged.

## Dataset policy

The Homer/Bart archive is referenced by the original notebooks at Google Drive paths ending in `Datasets/homer_bart_2.zip`; the ZIP is not stored in the repository. MNIST and Fashion-MNIST are downloaded using Keras dataset utilities. CIFAR-10 is downloaded by TensorFlow/torchvision utilities. Face, pose, action, DeepDream and OpenCV external assets still require a complete inventory. See `docs/DATASETS_AND_ASSETS.md`.

## TensorFlow history

Stored outputs verify TensorFlow 2.4.0 in the original CNN and ResNet50 transfer-learning notebooks, and TensorFlow 2.4.1 in the autoencoder notebook. Other original versions remain unverified. Modern TensorFlow target: 2.21.0 on supported platforms; Intel macOS should use 2.16.2 per the official compatibility matrix. See `docs/TENSORFLOW_VERSION_AUDIT.md`.

## Image data and preprocessing

See `docs/IMAGE_DATA_UNDERSTANDING_AND_PREPROCESSING.md` for formulas, image dimensions, normalization, augmentation rules, resizing/interpolation, class imbalance, data leakage and evaluation tips.

## Validation limits

New notebooks have been structurally authored and reviewed, but full runtime execution and model training are not claimed. Some large legacy notebooks could not be retrieved fully by the GitHub connector; they remain marked as not yet audited. Never treat unexecuted notebook code or illustrative examples as measured experimental results.

## License and attribution

Respect the licenses of datasets, model weights, images, videos and third-party software. Do not redistribute private or unlicensed archives.
