# Infrared-Aerial-Drone-Detection-System
A computer vision project designed to detect small drones in infrared aerial footage using a deep learning-based object detection pipeline.

##Objective
To develop an accurate and scalable detection system for drones flying in sensitive airspace using thermal(IR) imagery.

##Dataset
-Source: [Anti-UAV dataset](https://anti-uav.github.io/)
-Type: Infrared sequences with annotated bounding boxes.
-Size: 6 sequences(8500 images) selected.

##Model
-Architecture: YOLOv8m
-Training: Custom dataset(train/valid/test split)
-Evaluation Metrics:
  -Precision: 96.4%
  -Recall: 73.5%
  -mAP@0.5: 82.7%
-Size-wise Evaluation: Small, Medium, Large drones.

##Features
-IR drone detection from still images and sequences.
-Size-based performance reporting.
-Auto-generated Excel metric reports.
-Future Scope: Motion tracking, real-time alerts, and reducing/distinguishing false positives.

##Sample Detection output
<img width="1011" height="802" alt="image" src="https://github.com/user-attachments/assets/0ccf9dc0-529f-4ca8-b3a6-f84aad8201df" />

##Tech Stack
-Python, Ultralytics YOLOv8, Google Colab

##Status
-Detection model complete
-Real-time streaming and alerting in progress

