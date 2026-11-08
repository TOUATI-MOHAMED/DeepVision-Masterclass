# Modern DeepVision — framework-separated curriculum

The modern curriculum is deliberately separated into independent framework tracks. **Do not mix TensorFlow and PyTorch imports in a lesson notebook.** Use separate virtual environments and follow the relevant track README.

## Framework tracks

- [TensorFlow / Keras lessons](tensorflow/README.md)
- [PyTorch lessons](pytorch/README.md)
- [Original Colab notebook index](../original_colab/README.md)

## Numbered TensorFlow track

| ID | Lesson |
|---|---|
| TF00 | CNN image classification on Homer/Bart |
| TF01 | ResNet50 transfer learning and fine-tuning |
| TF02 | Dense and convolutional autoencoders |
| TF03 | DCGAN on MNIST |

## Numbered PyTorch track

| ID | Lesson |
|---|---|
| PT00 | CNN image classification on CIFAR-10 |
| PT01 | ResNet50 transfer learning |
| PT02 | Dense and convolutional autoencoders |
| PT03 | DCGAN on MNIST |

## Exercises and solutions

- [TensorFlow solutions](tensorflow/solutions/Exercise_Solutions_TensorFlow.ipynb)
- [PyTorch solutions](pytorch/solutions/Exercise_Solutions_PyTorch.ipynb)

Solutions are maintained separately from the teaching notebooks. The first-generation mixed-framework series remains for historical continuity; the new separate tracks are the recommended learning path.

## Data and reading material

- [Dataset and asset inventory](../../docs/DATASETS_AND_ASSETS.md)
- [Image understanding and preprocessing guide](../../docs/IMAGE_DATA_UNDERSTANDING_AND_PREPROCESSING.md)
- [TensorFlow version audit](../../docs/TENSORFLOW_VERSION_AUDIT.md)
- [Original notebook Colab guide](../original_colab/README.md)

## Important
The original Colab notebooks at repository root are preserved. New lessons use clearer local data roots, modern input pipelines and separate validation sets. New notebooks have been structurally authored but still require actual runtime/training validation on supported environments.
