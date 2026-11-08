DeepVision-Masterclass — PyTorch Edition
A reproducible, notebook-first modern companion to the original DeepVision-Masterclass repository. The original TensorFlow/OpenCV notebooks remain available as a legacy edition; this package adds PyTorch implementations and supporting documentation.
What's included
New notebook	Contents
01_Image_Classification_MLP_CNN_and_Feature_Engineering_PyTorch.ipynb	Pixel MLP baseline, original six colour descriptors, CNN, metrics and checkpoints
02_Transfer_Learning_and_Fine_Tuning_ResNet50_PyTorch.ipynb	Pretrained ResNet50, frozen feature extractor, fine-tuning and evaluation
03_Deep_Convolutional_GAN_MNIST_PyTorch.ipynb	DCGAN on MNIST with PyTorch
04_Human_Pose_and_Action_Recognition_KeypointRCNN_LSTM_PyTorch.ipynb	COCO Keypoint R-CNN pose inference and an LSTM template for labelled sequences
05_OpenCV_Fundamentals_and_PyTorch_Interop.ipynb	New OpenCV companion and tensor conversion examples


Quick start
1. Keep the five original notebooks unchanged (or optionally copy them to notebooks/legacy/).
2. Install PyTorch and torchvision as a matching pair for your hardware using the official PyTorch selector. The current target family is PyTorch 2.14.0 / torchvision 0.29.0 (released September 2026); see the release announcement.
3. Install the other dependencies:
python -m pip install -r requirements.txt
4. Run from the repository root:
jupyter lab
5. Read docs/DATASETS_AND_ASSETS.md before running Homer/Bart or pose experiments.
Dataset status
- MNIST: automatically downloaded by torchvision in notebook 03.
- Homer/Bart archive 1: original private Drive path found; exact public source not verified.
- Homer/Bart archive 2: strong matching Kaggle candidate identified (aasousa/images-simpsons) because the folder structure, class mapping and reported counts match the original notebook output. Verify license and archive contents before use.
- Pose image / video: original private sample is missing; supply a permitted image/video.
- MPI/OpenPose Caffe assets: original .prototxt and .caffemodel are not in the repository. Notebook 04 uses torchvision Keypoint R-CNN (17 COCO keypoints), a replacement rather than an MPI port (15 points).
- Action sequences: no labelled temporal action dataset was found; the LSTM is a template, not a trained action model.
See docs/ORIGINAL_NOTEBOOK_AUDIT.md and docs/DATASETS_AND_ASSETS.md for precise details.
Important limitation
The original openCVTutorial_Basics.ipynb raw file is 18.4 MB and could not be retrieved cell-by-cell during this audit. Notebook 05 is a new companion, not a claimed line-by-line conversion. The new notebooks pass structure and code syntax checks; not all model training or external downloads were executed. See docs/VALIDATION_AND_LIMITATIONS.md.
Repository structure
DeepVision-Masterclass/
├── README.md
├── requirements.txt
├── .gitignore
├── docs/
├── notebooks/pytorch/
├── notebooks/legacy/       # optional; original root notebooks can remain in place
├── scripts/
├── data/                   # local datasets; ignored by Git
└── checkpoints/             # local weights; ignored by Git
License and responsible use
This package does not change the license of the original repository. Review the repository license and each dataset/model license before redistribution. Do not commit personal photos/videos, private Drive archives, third-party images, or model weights unless you have rights to do so.
