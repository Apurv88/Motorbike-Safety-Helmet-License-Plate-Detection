# Motorbike-Safety-Helmet-License-Plate-Detection

This repository contains the training, evaluation, and inference code for a computer vision project aimed at detecting motorbike riders' helmets and license plates. The project utilizes various lightweight YOLO models to achieve real-time performance.

## Project Overview

The primary goal of this project is to enhance road safety by automatically classifying and detecting objects such as `helmet` and `no-helmet`. The repository includes benchmarking and comparisons across three YOLO nano architectures: **YOLOv10n**, **YOLOv11n**, and **YOLOv26n**. 

## Repository Structure

* **`yolov10n.ipynb`**: Jupyter notebook for training and evaluating the YOLOv10 Nano model.
* **`yolo11n.ipynb`**: Jupyter notebook for training and evaluating the YOLOv11 Nano model.
* **`yolo26.ipynb`**: Jupyter notebook configured for YOLOv26 Nano training, tested in a Kaggle environment.
* **`best.pt` / `best (1).pt`**: Saved PyTorch model checkpoint weights containing the best detection results.
* **`args.yaml`**: Training hyperparameter configuration files.
* **`results.csv` & `results.png`**: Logs of training/validation loss, precision, recall, and mAP metrics across epochs.
* **`val_batch*_pred.jpg`**: Visualizations of batch predictions on the validation set.

## Dataset

The models were trained using a custom dataset hosted on Roboflow.
* **Workspace**: `object-detection-8uqdh`
* **Project**: `helmet-and-number-plate-detection-for-motorbike-safety-iityz-nhuwd`
* **Version**: 1 (yolov11 format)

## Training Configuration

The models were trained with the following default parameters defined in `args.yaml`:
* **Task**: detect
* **Epochs**: 50
* **Batch Size**: 16
* **Patience**: 100

## Evaluation Metrics & Performance

The models were evaluated on the test set to compare accuracy and inference speed. Below is the performance summary:

| Model Architecture | mAP@0.5 | mAP@0.5:0.95 | Precision (mean) | Recall (mean) | Inference Speed |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **YOLOv10n** | 0.948 | 0.730 | 0.926 | 0.887 | 4.09 ms/image |
| **YOLOv11n** | 0.950 | 0.730 | 0.926 | 0.897 | 4.39 ms/image |
| **YOLOv26n** | 0.949 | 0.734 | 0.923 | 0.892 | 3.99 ms/image |

### Key Insights
* **YOLOv11n** achieved the highest overall detection accuracy at `0.950 mAP@0.5`.
* **YOLOv26n** provided the best localization accuracy (`0.734 mAP@0.5:0.95`) and the fastest inference speed (`3.99 ms/image`).

## How to Run

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/your-username/your-repo-name.git](https://github.com/your-username/your-repo-name.git)
   cd your-repo-name
