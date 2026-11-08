# Modern Computer Vision Series

This directory contains the updated companion curriculum. Each lesson is designed to be read, executed and extended in Jupyter.

## Recommended learning path

1. **Classification foundations:** compare TensorFlow/Keras and PyTorch in the dual-framework notebook, then train a CNN on CIFAR-10.
2. **Generalization:** study augmentation, regularization and controlled experiments.
3. **Transfer learning:** freeze a pretrained ResNet50, train a task head, then fine-tune carefully.
4. **Representation learning:** train dense and convolutional autoencoders and inspect compression quality.
5. **Generative learning:** train a DCGAN and inspect generated samples and failure modes.
6. **Detection:** understand bounding boxes, class IDs, pretrained Faster R-CNN and custom dataset contracts.
7. **Segmentation:** build U-Net and evaluate pixel-level predictions with Dice and IoU.
8. **Transformers:** fine-tune ViT-B/16 and compare it fairly with CNN baselines.

## Notebook inventory

- [00 — TensorFlow + PyTorch comparison](Modern_Deep_Learning_Computer_Vision_TensorFlow_PyTorch.ipynb)
- [01 — CNN image classification (CIFAR-10)](01_CNN_Image_Classification_CIFAR10_PyTorch.ipynb)
- [02 — Data augmentation and regularization](02_Data_Augmentation_and_Regularization.ipynb)
- [03 — ResNet50 transfer learning (TensorFlow + PyTorch)](03_Transfer_Learning_ResNet50_TensorFlow_PyTorch.ipynb)
- [04 — Autoencoders and image compression](04_Autoencoders_Image_Compression_TensorFlow_PyTorch.ipynb)
- [05 — DCGAN on MNIST](05_GANs_DC_GAN_MNIST_PyTorch.ipynb)
- [06 — Object detection with Faster R-CNN](06_Object_Detection_Torchvision_FasterRCNN.ipynb)
- [07 — Semantic segmentation with U-Net](07_Semantic_Segmentation_U_Net_PyTorch.ipynb)
- [08 — Vision Transformers](08_Vision_Transformers_Transfer_Learning.ipynb)

## Execution notes

- Run notebooks from the repository root so relative paths such as `data/` work.
- Use a dedicated environment. Install PyTorch and torchvision as a compatible pair using the official selector; install TensorFlow only where needed.
- Dataset loaders may download public benchmark datasets. Object detection and segmentation require the user to connect a dataset and verify its annotation format.
- Training defaults are intentionally short for classroom smoke-runs. Increase epochs only after validating the pipeline and hardware budget.
- Save experiment metadata: seed, split, preprocessing, label mapping, package versions, checkpoint selection and evaluation metrics.

## Pedagogical and research standards

Use a validation set for model selection and keep the test set untouched until final evaluation. Report macro-F1/per-class metrics for imbalanced classification; mAP for detection; Dice/IoU for segmentation. Compare models under identical splits and compute budgets. Do not present example epochs or unexecuted cells as achieved experimental results.

## Exercise solutions

Each numbered lesson has a separate solutions notebook in its own numbered folder. Keep solutions separate from the teaching notebook so learners can attempt exercises independently.

| Lesson | Solutions notebook |
|---|---|
| 00 — TensorFlow + PyTorch comparison | [Exercise solutions](solutions/00_00_tensorflow_pytorch/Exercise_Solutions.ipynb) |
| 01 — CNN image classification | [Exercise solutions](solutions/01_01_cnn_classification/Exercise_Solutions.ipynb) |
| 02 — Augmentation and regularization | [Exercise solutions](solutions/02_02_augmentation/Exercise_Solutions.ipynb) |
| 03 — Transfer learning | [Exercise solutions](solutions/03_03_transfer_learning/Exercise_Solutions.ipynb) |
| 04 — Autoencoders | [Exercise solutions](solutions/04_04_autoencoders/Exercise_Solutions.ipynb) |
| 05 — GANs | [Exercise solutions](solutions/05_05_gans/Exercise_Solutions.ipynb) |
| 06 — Object detection | [Exercise solutions](solutions/06_06_object_detection/Exercise_Solutions.ipynb) |
| 07 — Semantic segmentation | [Exercise solutions](solutions/07_07_segmentation/Exercise_Solutions.ipynb) |
| 08 — Vision Transformers | [Exercise solutions](solutions/08_08_vit/Exercise_Solutions.ipynb) |

Solutions provide reference implementations, reasoning and evaluation guidance. Dataset-specific training and measured performance remain learner tasks where data or hardware is not bundled.
