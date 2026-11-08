# TensorFlow version audit

## Evidence-based findings from original notebook outputs

| Original notebook | TensorFlow version | Evidence |
|---|---:|---|
| `Computer_Vision_Masterclass_Convolutional_neural_network_for_image_classification_ORIGINAL.ipynb` | **2.4.0** | Stored output from `tf.__version__` in the import cell |
| `Computer_Vision_Masterclass_Transfer_learning_and_fine_tuning.ipynb` | **2.4.0** | Stored output from `tf.__version__` in the import cell |
| `Computer_Vision_Masterclass_Autoencoders_for_image_compression.ipynb` | **2.4.1** | Stored output from `tf.__version__` in the import cell |
| GAN, MLP/features, face detection, face recognition, gesture/action, DeepDream, OpenCV | Not verified yet | The full files or outputs were not all retrieved successfully in the current audit. |

These are historical runtime outputs stored inside the notebooks. They are not inferred from syntax or current package compatibility.

## Modern edition target

The new TensorFlow track declares TensorFlow **2.21.0 / Keras 3** as its baseline on supported platforms. The official installation matrix lists Python 3.10–3.13 for TensorFlow 2.21.0 and notes that **2.16.2 was the last TensorFlow release supporting Intel macOS (x86_64)**. On Intel Mac use TensorFlow 2.16.2; on Apple Silicon, TensorFlow 2.21.0 wheels are listed for arm64. Verify the current platform matrix before installation and record the exact `tf.__version__`.

Official references:
- [TensorFlow pip installation and platform/Python matrix](https://www.tensorflow.org/install/pip)
- [TensorFlow tested build configurations](https://www.tensorflow.org/install/source)

Each TensorFlow lesson prints its installed framework version at runtime. This avoids implying that a notebook's target version is the version installed on every learner's machine.

## Main API modernization

| Legacy pattern | Modern approach |
|---|---|
| `ImageDataGenerator.flow_from_directory` | `tf.keras.utils.image_dataset_from_directory` + `tf.data` |
| `fit_generator(...)` | `model.fit(...)` |
| implicit label order | explicit `class_names` and stored class mapping |
| model JSON + separate HDF5 weights | `.keras` model save format |
| test data used as validation | separate training/validation/test partitions |
| hard-coded Drive path | configurable `Path('data/...')` |

## Validation status

The notebook JSON files and selected source cells have been inspected. The new TensorFlow notebooks have not yet been run end-to-end on CPU/GPU, and no training results are claimed.
