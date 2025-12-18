# Deep learning object detection-based Hierarchical Fuzzy model to early detection of Spinal Metastatic Bone Cancer

## Description
This repository introduces a complete deep learning model for detecting and classifying spine metastatic bone cancer from CT scan images. The method combines modern YOLO-based object detection models with a hierarchical fuzzy logic–based decision system to improve reliability, especially when predictions are uncertain or unclear.

The system classifies spine CT images into three clinically significant categories: **Normal**, **Lytic**, and **Blastic**. Multiple YOLO architectures are implemented and evaluated to ensure comprehensive performance comparison and reproducibility.


## Dataset Information
- **Imaging Modality:** Spine CT scans  
- **Source:** Publicly available medical imaging datasets (The Cancer Imaging Archive – TCIA)  
- **Classes:**  
  - Normal  
  - Lytic  
  - Blastic  
- **Annotation Format:** YOLO format (`.txt`)  
- **Annotation Tool:** Makesense AI  

## Dataset Structure
- DATASET/
  - images/
    - train/
    - test/
  - labels/
    - train/
    - test/

Each image has a corresponding YOLO-format annotation file containing bounding box and class information.

---

## Code Information
This repository includes:
- Dataset preprocessing and splitting scripts  
- YOLO-based training and testing pipelines  
- Model evaluation and performance comparison scripts  
- Hierarchical fuzzy logic–based post-processing module for handling prediction uncertainty  

All experiments are designed to be executed in **Google Colab** for ease of reproducibility.

---

## Usage Instructions

### 1. Clone the Repository
```bash
!git clone https://github.com/ultralytics/yolov5.git
```
### 2. Install Required Libraries
```bash

!pip install ultralytics --quiet
```
### 3. Prepare the Dataset
- Organize images and labels according to the dataset structure above.
- Update paths in dataset.yaml to point to my dataset in Google Drive.
- Ensure YOLO-format annotation files are present.
  
### 4. Train the Model
```bash

python train.py --model yolov11n.pt --data data.yaml --epochs 100 --img 640
```
### 5. Evaluate the Model
```bash

python val.py --weights best.pt --data data.yaml
```
### 6. Run Inference
```bash

python detect.py --weights best.pt --source test_images/
```
## Requirements
- Python >= 3.8
- PyTorch
- Ultralytics YOLO
- OpenCV
- NumPy
- Matplotlib
- scikit-learn

## Methodology
- Data Preprocessing: Resize and normalize CT images to match YOLO input requirements.
- Annotation Handling: Validate YOLO-format labels.
- Model Training: Train YOLOV5, YOLOv8, YOLOV9, YOLOV10, YOLOv11 and YOLOV12 models are train and tested.
- Evaluation: Measure mAP, precision, recall, and F1-score.
- Hierarchical Fuzzy Model: Refine predictions in ambiguous cases using fuzzy logic.
- Comparative Analysis: Compare YOLO variants to select the best model.





