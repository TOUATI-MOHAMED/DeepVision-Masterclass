# Validation and limitations

## Checks performed

- New notebook files are valid Jupyter Notebook JSON structures (nbformat 4).
- Code cells were authored with empty outputs and no execution-count claims.
- The series covers classification, augmentation, transfer learning, autoencoders, GANs, object detection, segmentation and vision transformers.
- Original notebooks are preserved in their original paths.

## Not claimed

- Full end-to-end training of all notebooks on CPU/GPU.
- Download availability or licensing of external datasets and pretrained weights.
- Reproduction of reported performance values from the original masterclass.
- Complete cell-by-cell review of the seven large original notebooks listed in `ORIGINAL_NOTEBOOK_AUDIT.md`.

## Known teaching-lab caveats to check before long runs

- Select a compatible Python / TensorFlow / PyTorch / torchvision combination for the machine.
- Detection requires a real dataset, verified bounding boxes and a correct class map. The notebook includes a dataset contract and model-head example, not a complete labeled dataset.
- Segmentation requires paired image/mask paths and synchronized transforms. The loader intentionally contains a `NotImplementedError` placeholder until the learner supplies their dataset.
- Transfer-learning preprocessing must match the selected pretrained weights.
- For publication-quality results, use train/validation/test separation, multiple seeds, appropriate metrics and documented compute budgets.
