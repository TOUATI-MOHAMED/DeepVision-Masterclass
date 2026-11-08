# DeepVision-Masterclass
### Practical Computer Vision & Deep Learning with TensorFlow, PyTorch and OpenCV

[![Python](https://img.shields.io/badge/Python-3.10%2B-blue?logo=python&logoColor=white)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Notebooks-Jupyter-orange?logo=jupyter&logoColor=white)](https://jupyter.org/)
[![PyTorch](https://img.shields.io/badge/PyTorch-modern%20edition-ee4c2c?logo=pytorch&logoColor=white)](https://pytorch.org/)
[![OpenCV](https://img.shields.io/badge/OpenCV-computer%20vision-5c3ee8?logo=opencv&logoColor=white)](https://opencv.org/)

**DeepVision-Masterclass** is a practical, notebook-first collection for learning and experimenting with computer vision and deep learning. It brings together the original educational notebooks and a modernized PyTorch edition, covering image classification, convolutional neural networks, transfer learning, generative adversarial networks, human pose estimation, and image processing with OpenCV.

The repository is designed for students, instructors, developers, and researchers who want to study complete workflows, inspect implementations, adapt experiments, and build their own computer-vision projects.

---

## Contents

- [Learning topics](#learning-topics)
- [Repository editions](#repository-editions)
- [Notebook catalogue](#notebook-catalogue)
- [Getting started](#getting-started)
- [Datasets and external assets](#datasets-and-external-assets)
- [Reproducibility and hardware](#reproducibility-and-hardware)
- [Suggested learning path](#suggested-learning-path)
- [Known limitations](#known-limitations)
- [Contributing](#contributing)
- [Citation and acknowledgement](#citation-and-acknowledgement)
- [License](#license)

## Learning topics

| Area | Topics and techniques |
|---|---|
| Image processing | Image loading, resizing, color spaces, filtering, contours and OpenCV operations |
| Image classification | Pixel-based baselines, handcrafted features, multilayer perceptrons and CNNs |
| Transfer learning | ImageNet-pretrained ResNet50, feature extraction, layer freezing and fine-tuning |
| Generative models | GAN fundamentals, generator/discriminator design and DCGAN training |
| Human pose estimation | Body keypoints, skeleton visualization and pose inference |
| Sequence modelling | LSTM architecture template for temporal keypoint/action sequences |
| Model evaluation | Train/validation/test splits, accuracy, precision, recall, F1-score and confusion matrices |

## Repository editions

### 1. Original notebooks

The original notebooks are retained as the historical/legacy educational edition. They include TensorFlow/Keras, OpenCV and pretrained OpenPose/Caffe examples.

| Original notebook | Main subject |
|---|---|
| `Computer_Vision_Masterclass_GANs.ipynb` | GAN implementation and MNIST generation |
| `Computer_Vision_Masterclass_Neural_networks_for_image_classification.ipynb` | Homer/Bart image classification and handcrafted color features |
| `Computer_Vision_Masterclass_Recognition_of_gestures_and_actions.ipynb` | OpenCV DNN / OpenPose-style body-keypoint detection |
| `Computer_Vision_Masterclass_Transfer_learning_and_fine_tuning.ipynb` | ResNet50 transfer learning and fine-tuning |
| `openCVTutorial_Basics.ipynb` | OpenCV fundamentals |

The original notebooks are kept for learning-history and comparison purposes. Their dependencies, paths and external assets may need adjustment before execution on a new machine.

### 2. Modern PyTorch notebooks

The PyTorch edition provides updated, separate implementations. It is intended to complement—not silently overwrite—the original notebooks.

| Notebook | Main contents |
|---|---|
| `01_Image_Classification_MLP_CNN_and_Feature_Engineering_PyTorch.ipynb` | Pixel MLP baseline, six handcrafted color descriptors, CNN, evaluation and checkpoints |
| `02_Transfer_Learning_and_Fine_Tuning_ResNet50_PyTorch.ipynb` | Pretrained ResNet50, frozen feature extractor, fine-tuning and evaluation |
| `03_Deep_Convolutional_GAN_MNIST_PyTorch.ipynb` | DCGAN-style generator/discriminator and MNIST training |
| `04_Human_Pose_and_Action_Recognition_KeypointRCNN_LSTM_PyTorch.ipynb` | COCO Keypoint R-CNN inference and an LSTM template for labelled keypoint sequences |
| `05_OpenCV_Fundamentals_and_PyTorch_Interop.ipynb` | OpenCV image-processing companion and NumPy/PyTorch tensor interoperability |

> **Architecture note:** The original gesture notebook uses an MPI/OpenPose-style model with 15 keypoints. The modern notebook uses torchvision Keypoint R-CNN with the COCO keypoint convention (17 keypoints). This is a modern alternative, not a weight-compatible or exact architectural port.

## Notebook catalogue

### Image classification

The classification material demonstrates why flattening image pixels into a large fully connected network can be expensive, and how convolutional layers preserve and exploit spatial structure. The PyTorch edition includes an MLP baseline and a CNN so their behaviour can be compared under the same data pipeline.

### Transfer learning

The transfer-learning material uses an ImageNet-pretrained ResNet50. It introduces:
- loading a pretrained backbone;
- replacing the classification head;
- freezing the backbone for feature extraction;
- selectively unfreezing layers for fine-tuning; and
- evaluating the resulting classifier.

### Generative adversarial networks

The GAN material introduces the generator/discriminator training game and a DCGAN-style convolutional model trained on MNIST. Generated samples are illustrative outputs, not evidence of image-generation quality on more complex domains.

### Pose estimation and action recognition

The original material demonstrates body-keypoint detection and skeleton visualization. The PyTorch companion uses a pretrained Keypoint R-CNN for pose inference and includes an LSTM modelling template. A properly trained action-recognition experiment still requires a labelled temporal dataset, sequence construction, and a defined evaluation protocol.

### OpenCV

The OpenCV material introduces practical image-processing operations and demonstrates how OpenCV/NumPy arrays can be converted to PyTorch tensors for subsequent model inference or training.

---

## Getting started

### Requirements

- Python 3.10 or newer is recommended.
- JupyterLab or Jupyter Notebook.
- PyTorch and torchvision installed as a compatible pair for your operating system and hardware.
- The additional packages listed in `requirements.txt` (if present in the PyTorch edition).

### 1. Clone the repository

```bash
git clone https://github.com/TOUATI-MOHAMED/DeepVision-Masterclass.git
cd DeepVision-Masterclass
```

### 2. Create and activate a virtual environment

**macOS / Linux**

```bash
python3 -m venv .venv
source .venv/bin/activate
```

**Windows PowerShell**

```powershell
python -m venv .venv
.venv\Scripts\Activate.ps1
```

### 3. Install PyTorch

Install the appropriate PyTorch/torchvision build for your CPU, CUDA or ROCm setup using the official selector:

https://pytorch.org/get-started/locally/

Then install the remaining dependencies:

```bash
python -m pip install -r requirements.txt
```

If you are using only the original notebooks, install the framework versions required by those notebooks separately. Avoid mixing incompatible legacy TensorFlow and modern PyTorch environments; separate virtual environments are recommended.

### 4. Launch Jupyter

```bash
python -m pip install jupyterlab
jupyter lab
```

Open a notebook and execute its cells from top to bottom. Read the relevant dataset and asset notes before running experiments that require external files.

---

## Datasets and external assets

Some original notebooks refer to datasets or model files stored outside the Git repository (including personal Google Drive paths). These assets are **not automatically included** in this repository.

| Dataset / asset | Used by | Availability and notes |
|---|---|---|
| MNIST | GAN notebook | Downloaded by the PyTorch/torchvision data pipeline when the notebook is run; internet access may be required on first use |
| Homer/Bart archive 1 (`homer_bart_1.zip`) | Original classification notebook | Original notebook references a Google Drive archive. A verified public source has not been established |
| Homer/Bart archive 2 (`homer_bart_2.zip`) | Original classification and transfer learning | A Kaggle dataset appears to be a close match to the notebook's reported folder/classes/counts. Treat it as a candidate until archive contents are checked: [Kaggle – Images Simpsons](https://www.kaggle.com/datasets/aasousa/images-simpsons) |
| Sample photos/videos | Pose and OpenCV demonstrations | Supply your own permitted images/videos; original local sample files are not guaranteed to be present |
| MPI/OpenPose Caffe configuration and weights | Original pose notebook | The `.prototxt` and `.caffemodel` files are external assets and are not included |
| Labelled action sequences | LSTM action-recognition template | A suitable labelled temporal dataset must be selected and prepared by the user |

### Expected image-folder layout

For the Homer/Bart classification notebooks, arrange your own dataset in a folder structure such as:

```text
data/
└── homer_bart/
    ├── train/
    │   ├── bart/
    │   └── homer/
    └── test/
        ├── bart/
        └── homer/
```

The exact directory names and class-to-index mapping must match the paths and labels configured in the notebook. Do not assume that a similarly named public dataset is identical to the original private archive.

### Dataset and model licensing

Before downloading, using, or redistributing any dataset, image, video, pretrained checkpoint or model configuration:
1. read its original license and terms of use;
2. check whether research, teaching and commercial use are permitted;
3. preserve required attribution; and
4. do not commit private, sensitive or unlicensed data to Git.

More detailed provenance notes should be maintained in `docs/DATASETS_AND_ASSETS.md` when that file is included in the PyTorch modernization package.

---

## Reproducibility and hardware

- Run notebooks from a clean environment and record package versions.
- Set and document random seeds when comparing experiments.
- Keep training, validation and test data separate.
- Report class counts and preprocessing steps.
- Save model weights and experiment metadata outside version control unless there is a clear reason and permission to publish them.
- Use a GPU when available for training; CPU execution may be considerably slower.
- Pretrained torchvision models may download weights on first use, requiring network access.
- Results can vary with random seeds, hardware, library versions and dataset composition. Re-run experiments before reporting metrics.

Suggested local directories (do not commit large/private assets by default):

```text
data/
checkpoints/
outputs/
```

## Suggested learning path

1. Start with OpenCV fundamentals and image representation.
2. Build a simple pixel-based classification baseline.
3. Compare the baseline with a CNN.
4. Learn transfer learning and fine-tuning with ResNet50.
5. Study GAN components and train a DCGAN on MNIST.
6. Explore pose estimation and keypoint visualization.
7. Extend keypoints into temporal sequences for action recognition.

## Known limitations

- Dataset archives referenced through private Drive paths are not bundled.
- The Homer/Bart Kaggle link is a **candidate source**, not confirmed provenance for the original ZIP archive.
- The PyTorch pose notebook changes the keypoint model and convention from MPI/OpenPose to COCO Keypoint R-CNN.
- The LSTM sequence model is a template; it is not a pretrained or validated action-recognition system unless trained on a suitable labelled dataset.
- The modern OpenCV notebook is a companion tutorial. The original OpenCV notebook was too large to verify cell-by-cell during the initial modernization audit, so the companion must not be described as an exact port.
- Notebook syntax and structure checks do not guarantee that every cell, download, training run or metric will work in every environment. Validate locally before using results in teaching or publications.

## Contributing

Contributions and educational improvements are welcome. When adding a notebook:
- give it a descriptive, numbered filename;
- state its learning objectives and prerequisites;
- explain the dataset source, license and expected folder structure;
- provide a reproducible installation and execution path;
- include evaluation methodology and limitations;
- clear unnecessary outputs and avoid committing private data or large checkpoints.

## Citation and acknowledgement

If you use or adapt this repository in teaching, research or another project, please cite the repository URL and acknowledge the original authors of datasets, libraries, pretrained models and tutorials used by each notebook.

**Repository:** https://github.com/TOUATI-MOHAMED/DeepVision-Masterclass

## License

Unless a license file is present in the repository, no blanket reuse or redistribution permission should be assumed. The original notebooks, third-party datasets, pretrained models and the PyTorch additions may have different licensing terms. Add or update a repository-level `LICENSE` only after deciding which content you have the right to license.
