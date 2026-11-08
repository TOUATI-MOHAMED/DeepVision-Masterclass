# PyTorch track

**Independent framework environment:** PyTorch + torchvision installed as a compatible pair. These notebooks do not import TensorFlow.

| Lesson | Notebook | Dataset |
|---|---|---|
| 00 | [CNN classification](00_CNN_Image_Classification_CIFAR10_PyTorch.ipynb) · [solutions](solutions/00_CNN_CIFAR10_Solutions.ipynb) | CIFAR-10 |
| 01 | [ResNet50 transfer learning](01_Transfer_Learning_ResNet50_PyTorch.ipynb) · [solutions](solutions/01_ResNet50_Solutions.ipynb) | CIFAR-10 |
| 02 | [Autoencoders](02_Autoencoders_MNIST_FashionMNIST_PyTorch.ipynb) · [solutions](solutions/02_Autoencoders_Solutions.ipynb) | MNIST |
| 03 | [DCGAN](03_DC_GAN_MNIST_PyTorch.ipynb) · [solutions](solutions/03_DCGAN_Solutions.ipynb) | MNIST |

Install PyTorch and torchvision using the official selector for your CPU/CUDA/ROCm configuration: https://pytorch.org/get-started/locally/

Then install: `python -m pip install jupyterlab matplotlib numpy scikit-learn pillow`.

Start from repository root: `jupyter lab`. [PyTorch exercise solutions](solutions/Exercise_Solutions_PyTorch.ipynb) are separate from the lessons. Training has not been executed as part of this repository change.
