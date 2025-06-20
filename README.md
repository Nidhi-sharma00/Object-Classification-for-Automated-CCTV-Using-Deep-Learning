# Object Classification for Automated CCTV

This project aims to automate CCTV recording using object classification. By leveraging deep learning models, the system only records footage when relevant objects such as humans, vehicles, or animals are detected. This reduces unnecessary storage usage and enhances surveillance efficiency.

---

## Features

* CNN-based classification using Fashion-MNIST for benchmarking
* Object detection using YOLOv5 on custom CCTV-like dataset
* Real-time detection via webcam
* Automatic frame capture when relevant objects are detected
* YOLO-format dataset annotation and processing

---

## Project Structure

```
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
├── webcam_inference.py          # Webcam-based real-time detection
├── report.ipynb                 # Complete project report notebook
├── README.md
```

---

## Setup Instructions

1. Clone the repository:

   ```bash
   git clone https://github.com/your-username/cctv-object-classification.git
   cd cctv-object-classification
   ```
2. Install dependencies:

   ```bash
   pip install -r yolov5/requirements.txt
   ```
3. Train the model:

   ```bash
   python train.py --img 640 --batch 16 --epochs 30 --data dataset_cctv/data.yaml --weights yolov5s.pt --name cctv_model
   ```
4. Run real-time detection using webcam:

   ```bash
   python webcam_inference.py
   ```

---

## Dataset

* **Benchmark**: [Fashion-MNIST](https://github.com/zalandoresearch/fashion-mnist)
* **Custom YOLO Dataset**:

  * Classes:

    * `0`: human
    * `1`: vehicle
    * `2`: animal
  * Format: YOLO annotation with `.txt` files corresponding to each image

---

## Results

* CNN on Fashion-MNIST: \~91% accuracy
* YOLOv5 trained on custom dataset for object classification
* Real-time detection worked accurately with webcam input
* Frames saved only when selected object classes were detected

---

## Future Improvements

* Add audio alerts for detections
* Support for RTSP/IP camera streams
* Deployment on edge devices (Jetson Nano, Raspberry Pi)
* Logging detections with timestamps

---

## Developed By

**Nidhi Sharma**
Role: Student, Guru Jambheshwar University of Science and Technology

---

## References

* [YOLOv5 GitHub](https://github.com/ultralytics/yolov5)
* [PyTorch Hub](https://pytorch.org/hub)
* [OpenCV](https://opencv.org)
* [Fashion-MNIST Dataset](https://github.com/zalandoresearch/fashion-mnist)


Fashion-MNIST Dataset

