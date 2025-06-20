# **Object Classification for Automated CCTV**

This project aims to automate CCTV recording using object classification. By leveraging deep learning models, the system only records footage when relevant objects such as humans, vehicles, or animals are detected. This reduces unnecessary storage usage and enhances surveillance efficiency.

Features

CNN-based classification on Fashion-MNIST dataset for benchmarking

Custom object detection using YOLOv5

Real-time detection via webcam

Automatic frame capture on detecting selected objects

YOLO-format dataset preparation

Project Structure

├── yolov5/                      # YOLOv5 source code
├── dataset_cctv/                # Custom dataset in YOLO format
│   ├── images/
│   │   ├── train/
│   │   └── val/
│   ├── labels/
│   │   ├── train/
│   │   └── val/
│   └── data.yaml
├── train.py                     # Training script for YOLOv5
├── webcam_inference.py          # Real-time webcam detection script
├── report.ipynb                 # Jupyter notebook with full workflow
├── README.md

Setup Instructions

Clone this repository and navigate to the project directory.

Install requirements:

pip install -r yolov5/requirements.txt

Train YOLOv5 model:

python train.py --img 640 --batch 16 --epochs 30 --data dataset_cctv/data.yaml --weights yolov5s.pt --name cctv_model

Run real-time detection with webcam:

python webcam_inference.py

Dataset

Benchmark: Fashion-MNIST

Custom CCTV-like dataset created in YOLO format with three classes:

0: human

1: vehicle

2: animal

Results

Fashion-MNIST model accuracy: ~91%

YOLOv5 detection confidence: configurable

Real-time frame saving when target classes appear

Future Improvements

Add audio alerts

Integrate with CCTV streams or RTSP

Optimize for Jetson Nano or Raspberry Pi

Developed By

Nidhi Sharma
Student, Guru Jambheshwar University of Science and Technology

References

YOLOv5 GitHub

PyTorch Hub

OpenCV

Fashion-MNIST Dataset

