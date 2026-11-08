# DeepVision Masterclass

Notebook-first educational repository for computer vision, image processing and deep learning. Original Google Colab notebooks are preserved, with separate modern TensorFlow/Keras and PyTorch learning tracks.

## Start here

- **[Modern curriculum](notebooks/modern/README.md)** — framework-separated lessons and solutions
- [TensorFlow/Keras track](notebooks/modern/tensorflow/README.md)
- [PyTorch track](notebooks/modern/pytorch/README.md)
- [Original Colab notebooks](notebooks/original_colab/README.md)
- [Dataset and asset inventory](docs/DATASETS_AND_ASSETS.md)
- [Image understanding and preprocessing guide](docs/IMAGE_DATA_UNDERSTANDING_AND_PREPROCESSING.md)
- [TensorFlow version audit](docs/TENSORFLOW_VERSION_AUDIT.md)

## Why separate frameworks?

TensorFlow/Keras and PyTorch are taught in independent notebooks and environments. This avoids dependency conflicts and helps learners understand each framework's native data pipeline, model API, training loop and checkpoint conventions.

## Historical and modern material

Original notebooks remain in the repository root with their Colab badges. Their old TensorFlow outputs are documented in the version audit. Modern notebooks are new companions; they are not presented as exact reproductions of every original experiment.

## Dataset policy

The original Homer/Bart notebook references `Datasets/homer_bart_2.zip` in Google Drive. This ZIP is not included in the repository. Public benchmark datasets (MNIST, Fashion-MNIST, CIFAR-10) are downloaded by framework utilities. Read [dataset provenance and setup](docs/DATASETS_AND_ASSETS.md) before running experiments.

## Installation

Use a separate virtual environment for each framework. Follow the installation instructions in the TensorFlow and PyTorch track READMEs. Select a framework build compatible with your Python version, operating system and accelerator.

## Validation

Notebook JSON structure has been checked. Full end-to-end execution, GPU compatibility, dataset downloads and training results are not claimed until run and recorded. See the documentation for audit scope and limitations.

## License and attribution

Respect the licenses of the original material, datasets, pretrained weights and third-party libraries. Do not redistribute archives unless their licenses explicitly permit it.
