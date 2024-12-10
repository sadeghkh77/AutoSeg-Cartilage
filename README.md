# AutoSeg-Cartilage
Automatic Segmentation of Articular Cartilage in the Knee Joint Using MONAI
Description
This project implements an automated pipeline for segmenting articular cartilage in the knee joint using MONAI, a deep learning framework for medical imaging. The workflow processes 3D medical images, organizes the data, and prepares it for training and testing a segmentation model. This project is specifically designed for medical researchers and practitioners who aim to study knee joint biomechanics or pathologies.
Key Features
Data Preprocessing:

Loads 3D knee MRI data and corresponding segmentation labels from .npz files.
Normalizes and reshapes the data for deep learning model compatibility.
Reduces dimensionality by slicing 3D volumes into 2D images for faster processing.
Dataset Management:

Splits data into training and testing subsets (e.g., 5% for testing).
Converts datasets to NIfTI format (.nii.gz) for standardized medical imaging workflows.
Compatibility with MONAI:

Generates training and testing datalists required by MONAI's AutoRunner and other pipelines.
Installation
Prerequisites
Python 3.8 or higher.
Google Colab (recommended for execution).
Libraries:
MONAI: For medical imaging workflows.
nibabel: For handling .nii.gz files.
NumPy, Matplotlib: For data manipulation and visualization.
Steps
Clone or download the project files.
Open the Jupyter Notebook in Google Colab.
Mount Google Drive to access the required datasets (X1.npz and Y1.npz).
Install required libraries by running:
css
Copy code
!pip install --upgrade monai nibabel
Usage
Data Preparation:

Place the data files (X1.npz and Y1.npz) in the specified Google Drive folder.
Use the load_data() function to load and normalize the data.
Training and Testing Splits:

The notebook automatically splits the data into training and testing sets.
NIfTI File Conversion:

Converts the processed data to .nii.gz format using the save_arrays_to_nii() function.
Dataset Configuration:

Verify the dataset paths in the sim_datalist dictionary to ensure compatibility with MONAI pipelines.
Run Segmentation:

Use MONAI’s AutoRunner for automated segmentation pipeline setup and training.


File Structure
project-folder/
│
├── Auto-Segmentation/               # Directory containing processed NIfTI files.
│   ├── tr_image_001.nii.gz          # Training image 1.
│   ├── tr_label_001.nii.gz          # Corresponding training label 1.
│   ├── te_image_001.nii.gz          # Testing image 1.
│   ├── te_label_001.nii.gz          # Corresponding testing label 1.
│   └── ...                          # Additional training/testing files.
│
├── data/
│   ├── X1.npz                       # Original 3D image data.
│   ├── Y1.npz                       # Original segmentation labels.
│
├── Monai_Auto_Seg.ipynb             # Jupyter Notebook with the implementation.
├── README.txt                       # This file.
