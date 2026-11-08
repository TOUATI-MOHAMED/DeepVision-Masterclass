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

The new TensorFlow track declares TensorFlow **2.21.0 / Keras 3** as its baseline. Check the official installation guide and the Python/platform compatibility matrix before installation. If a particular machine cannot install this version, install a currently supported compatible version and record the exact `tf.__version__`.

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
