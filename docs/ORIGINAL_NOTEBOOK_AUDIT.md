# Original notebook audit — DeepVision Masterclass

## Scope and method

The repository's original root notebooks were enumerated from the Git tree. A full notebook audit means reading every markdown/code cell, identifying external assets and paths, checking label mappings and preprocessing, and validating code. It does **not** mean merely reading the README or filenames.

## Cell-level inspection completed

| Original notebook | Inspection status | Observations |
|---|---|---|
| Autoencoders for image compression | Cell-level content retrieved and inspected (85 cells) | MNIST dense AE; Fashion-MNIST convolutional AE; hard-coded layer index/name; 50 epochs; reconstruction visualizations. The original decoder selects layers by positional indices. |
| CNN for image classification (ORIGINAL) | Cell-level content retrieved and inspected (53 cells) | Homer/Bart archive at private Google Drive path; legacy ImageDataGenerator/fit_generator; 64×64; large dense layers; HDF5 + JSON save/load; class mapping relies on directory order. |
| Transfer learning and fine-tuning | Cell-level content retrieved and inspected (72 cells) | Homer/Bart; ResNet50 ImageNet; frozen backbone then layer unfreezing; legacy HDF5/JSON serialization; test set used repeatedly during model selection; hard-coded sample path. |

## Not yet fully audited cell by cell

The following files were identified in the repository tree, but the GitHub file-content retrieval did not return their complete UTF-8 notebook bodies in this pass. Their contents must not be represented as fully reviewed:

- `Computer_Vision_Masterclass_Deep_dream.ipynb` (about 30.6 MB)
- `Computer_Vision_Masterclass_Face_detection.ipynb` (about 7.8 MB)
- `Computer_Vision_Masterclass_Face_recognition.ipynb` (about 3.9 MB)
- `Computer_Vision_Masterclass_GANs.ipynb` (about 2.8 MB)
- `Computer_Vision_Masterclass_Neural_networks_for_image_classification.ipynb` (about 2.0 MB)
- `Computer_Vision_Masterclass_Recognition_of_gestures_and_actions.ipynb` (about 3.5 MB)
- `openCVTutorial_Basics.ipynb` (about 24.3 MB)

The retrieval limit is a tooling constraint, not evidence that these notebooks are empty or invalid. A local clone or Git LFS/raw retrieval workflow is needed to complete their cell-level audit.

## Cross-cutting modernization targets observed

- Replace deprecated `ImageDataGenerator` / `fit_generator` workflows with `tf.data`, Keras preprocessing layers, or PyTorch Dataset/DataLoader.
- Remove private, machine-specific Google Drive paths; expose dataset roots as configuration variables.
- Preserve class names and class-index mappings explicitly; never assume directory ordering without checking it.
- Use validation data for checkpoint/early-stopping decisions and reserve the test set for final evaluation.
- Prefer `.keras` and PyTorch state dictionaries; store preprocessing, labels, versions and configuration alongside checkpoints.
- Add reproducible seeds, device checks, input-shape assertions, confusion matrices and per-class metrics.
- Keep original notebooks intact while new notebooks serve as modern companion lessons.

## Relationship to the new series

The new `notebooks/modern/` lessons are **modern companion material**, not claims of one-to-one conversion of every original notebook. Dataset-specific conversions (especially private Homer/Bart data, face assets, DeepDream inputs and gesture/action sequences) should only be added after source assets, labels and licenses are verified.
