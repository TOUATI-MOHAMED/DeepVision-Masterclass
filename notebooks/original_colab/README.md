# Original notebooks — preserved Colab edition

The original notebooks remain unchanged in the repository root. This index numbers the historical lessons for teaching and preserves the embedded **Open in Colab** badges in each notebook. They are not silently converted or overwritten.

| ID | Original notebook | Subject | Dataset / assets |
|---|---|---|---|
| O00 | [CNN image classification — ORIGINAL](../../Computer_Vision_Masterclass_Convolutional_neural_network_for_image_classification_ORIGINAL.ipynb) | Homer/Bart CNN, ImageDataGenerator | `Datasets/homer_bart_2.zip` |
| O01 | [Transfer learning and fine-tuning](../../Computer_Vision_Masterclass_Transfer_learning_and_fine_tuning.ipynb) | ResNet50, frozen backbone, fine-tuning | `Datasets/homer_bart_2.zip` |
| O02 | [Autoencoders for image compression](../../Computer_Vision_Masterclass_Autoencoders_for_image_compression.ipynb) | Dense AE on MNIST; convolutional AE on Fashion-MNIST | Keras datasets |
| O03 | [GANs](../../Computer_Vision_Masterclass_GANs.ipynb) | GAN / MNIST | Inspect notebook data loader |
| O04 | [Neural networks for image classification](../../Computer_Vision_Masterclass_Neural_networks_for_image_classification.ipynb) | Pixel and feature classification | Homer/Bart archive referenced by original |
| O05 | [Face detection](../../Computer_Vision_Masterclass_Face_detection.ipynb) | Face detection | Verify model weights and sample assets |
| O06 | [Face recognition](../../Computer_Vision_Masterclass_Face_recognition.ipynb) | Face recognition | Verify dataset and model assets |
| O07 | [Gesture and action recognition](../../Computer_Vision_Masterclass_Recognition_of_gestures_and_actions.ipynb) | OpenPose/keypoints and sequence modelling | Video samples, Caffe config/weights, action labels |
| O08 | [Deep Dream](../../Computer_Vision_Masterclass_Deep_dream.ipynb) | Feature visualization / DeepDream | Verify input images and pretrained model |
| O09 | [OpenCV basics](../../openCVTutorial_Basics.ipynb) | Image processing | Sample images/videos |

## How to run the original Colab notebooks

1. Open the notebook from its link above or use its embedded Colab badge.
2. In Colab, select **Runtime → Change runtime type** and choose GPU only if the lesson needs it.
3. Mount Google Drive only if the notebook's asset paths are present in your Drive.
4. Verify the archive path, extracted directory structure and class mapping before running training.
5. Run cells from top to bottom. Read the modernization notes before using old APIs.

## Historical TensorFlow versions verified from stored notebook outputs

- O00 CNN: TensorFlow **2.4.0** (printed output in the notebook).
- O01 Transfer learning: TensorFlow **2.4.0** (printed output).
- O02 Autoencoders: TensorFlow **2.4.1** (printed output).
- Other original notebooks: version not yet verified in this audit. Their files were too large for complete content retrieval through the GitHub connector; do not assume they used the same release.

The original code can still be useful for studying historical APIs. In particular, `ImageDataGenerator`, `fit_generator`, legacy HDF5/JSON model saving and older Colab path assumptions should be treated as legacy examples, not the recommended modern workflow.
