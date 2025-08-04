# Real-Time Drone Detection Using YOLO Architectures

This repository contains the implementation and analysis of a real-time drone detection system developed as part of an internship at IIT Tirupati. The project leverages YOLO (You Only Look Once) object detection models to detect, classify, and localize drones from both visible and infrared imagery.

## Project Overview

The proliferation of UAVs (drones) raises security and surveillance challenges in sensitive airspaces. This project develops and evaluates a deep learning-based detection pipeline to achieve:

- Real-time drone detection
- Classification and localization using bounding boxes
- Performance comparison of YOLOv8m and YOLOv10n architectures
- Evaluation on multiple public datasets (Visible & IR)

## Features

- End-to-end YOLO pipeline for drone detection
- Multiple model evaluation (YOLOv8m & YOLOv10n)
- Precision, Recall, mAP@0.5, FPS analysis
- Dataset preprocessing and annotation conversion scripts
- Size-wise detection performance for small, medium, and large drones
- Inference speed vs. accuracy trade-off analysis

## Datasets Used

1. **Anti-UAV Dataset**
   - Visible + IR imagery
   - ~223 video sequences
2. **DUT Anti-UAV Dataset**
   - Public GitHub dataset with visible drone images
3. **Kaggle Drone YOLO Dataset**
   - Pre-annotated YOLO format dataset

**Annotation format:** YOLO `[class x_center y_center width height]`  
**Image size:** 640×640 (preprocessed for YOLO input)  
**Split:** 80% Train / 10% Validation / 10% Test

## Models Trained

| Model   | Architecture | Dataset Type | FPS  | mAP@0.5 |
|--------|-------------|-------------|------|--------|
| Model-1 | YOLOv8m     | IR          | 58.82 | 0.791 |
| Model-2 | YOLOv10n    | IR          | 145   | 0.573 |
| Model-3 | YOLOv8m     | Visible     | 48.78 | 0.919 |
| Model-4 | YOLOv8m     | Visible     | 68.97 | 0.911 |

## Key Observations

- YOLOv8m provides higher accuracy, especially for small & medium drones.
- YOLOv10n achieves high FPS, suitable for speed-critical applications.
- Dataset choice significantly influences model generalization.
- Kaggle-trained model (Model-4) showed robust cross-size detection.

## Tools & Technologies

- **Languages:** Python
- **Frameworks:** PyTorch, Ultralytics YOLO
- **Libraries:** OpenCV, NumPy, Pandas, Matplotlib, Seaborn
- **Platforms:** Google Colab (GPU), Jupyter Notebook, PyCharm
- **Storage:** Google Drive for datasets & trained weights

## Challenges Faced

- Limited GPU runtime on Colab for large-scale training
- Dataset annotation conversion (JSON → YOLO format)
- Small object detection and class imbalance
- Maintaining consistent evaluation metrics (Precision, Recall, mAP, FPS)

## Project Demonstration

Detection results on DUT Anti-UAV dataset using YOLOv8m:

![DEMONSTRATION](https://github.com/user-attachments/assets/1a98c20e-11cc-4c6b-bd42-ab44e59f98fc)


## Future Scope

- Multi-drone tracking and temporal consistency
- Swarm detection with multiple drone classes
- Edge deployment optimization (TensorRT, ONNX)
- Integration with real-time alert systems

## References

1. Z. Zhu et al., “Detection and Tracking Meet Drones Challenge,” CVPR Workshops 2020.  
2. Wang, Dong et al., “DUT Anti-UAV: A Large Benchmark for Vision-Based Drone Monitoring,” arXiv:2103.05224.  
3. Jocher, G. et al., “YOLO by Ultralytics” – [GitHub](https://github.com/ultralytics/yolov5)  
4. Redmon, J. & Farhadi, A., “YOLOv3: An Incremental Improvement,” arXiv:1804.02767
