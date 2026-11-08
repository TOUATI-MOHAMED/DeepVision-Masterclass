# TensorFlow / Keras track

**Independent framework environment:** TensorFlow 2.21.0 / Keras 3 on supported platforms. On Intel macOS, the official TensorFlow compatibility table lists 2.16.2 as the last supported release; use that version there. Install TensorFlow in its own environment. These notebooks do not import PyTorch.

| Lesson | Notebook | Dataset |
|---|---|---|
| 00 | [CNN image classification — Homer/Bart](00_CNN_Image_Classification_Homer_Bart_TensorFlow.ipynb) | External `Datasets/homer_bart_2.zip` |
| 01 | [ResNet50 transfer learning](01_Transfer_Learning_ResNet50_TensorFlow.ipynb) | Homer/Bart folder dataset |
| 02 | [Autoencoders](02_Autoencoders_MNIST_FashionMNIST_TensorFlow.ipynb) | MNIST, Fashion-MNIST |
| 03 | [DCGAN](03_DC_GAN_MNIST_TensorFlow.ipynb) | MNIST |

Install:
```bash
python -m venv .venv-tf
# activate environment, then:
python -m pip install --upgrade pip
python -m pip install "tensorflow==2.21.0" jupyterlab matplotlib numpy scikit-learn pillow
# Intel macOS: use the supported 2.16.2 build instead
# python -m pip install "tensorflow==2.16.2" jupyterlab matplotlib numpy scikit-learn pillow
```
Check official TensorFlow install compatibility for your OS, Python and accelerator before installing. If this pinned baseline is unavailable on your platform, use the current supported release and record `tf.__version__`.

Start from repository root: `jupyter lab`.

[TensorFlow exercise solutions](solutions/Exercise_Solutions_TensorFlow.ipynb) are separate from the lessons. All notebook cells are authored for modern TensorFlow/Keras APIs. Training has not been executed as part of this repository change.
