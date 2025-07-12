# Social Distancing Detector using Deep Learning
This project presents a real-time deep learning-based solution to monitor and detect social distancing violations in public places using object detection and tracking methods.

## Problem Statement
Social distancing has been one of the most effective measures to limit the spread of COVID-19. However, enforcing it in public and workplace settings remains a challenge. This project addresses this issue by providing an automated solution to detect and alert for violations of social distancing using computer vision techniques.

## Abstract

Using video feeds from surveillance cameras, this system detects individuals using the **YOLOv3 object detection model**, calculates the pairwise distances between them, and identifies if any individuals are violating the minimum social distance threshold. The individuals are marked with red bounding boxes if the distance is too close and green if it’s safe. This model is trained using the **COCO dataset** and performs real-time detection and alerting.

## Tools and Technologies

- **Language**: Python  
- **Framework**: Deep Learning (YOLOv3)  
- **Libraries**: OpenCV, NumPy, SciPy, imutils, argparse  
- **Hardware Requirements**:  
  - Intel i5 or above, 8GB RAM  
  - GPU recommended for model performance  
- **Software Requirements**:  
  - Windows 8 or higher  
  - Visual Studio / Command Prompt  
  - YOLOv3 model with coco.names, yolov3.cfg, and yolov3.weights files  

## System Design

### Pipeline
1. Input video frame from surveillance camera
2. Object detection using YOLOv3 (only detects pedestrians)
3. Bird’s-eye transformation for accurate distance mapping
4. Centroid calculation of each bounding box
5. Euclidean distance computation between every pair
6. Social distance violation detection and alerting

### Architecture Components
- **Object Detection**: YOLOv3 with COCO dataset
- **Object Tracking**: Bounding box centroid tracking
- **Distance Measurement**: Top-down perspective + Euclidean distance
- **Violation Detection**: Red box = violation; Green box = safe

## Algorithm Summary

- Load YOLO model with pretrained weights
- Process video frames and detect people
- Measure Euclidean distances between bounding box centroids
- Mark violations based on a threshold distance
- Display results in real-time with bounding boxes and violation count

## Results
- The system successfully detects and differentiates individuals based on distance.
- Alerts are generated in real-time for violations.
- Accuracy is reliable under controlled lighting and fixed camera angle.

## Future Enhancements
1. Integrate mask detection and temperature screening
2. Use YOLOv5 or EfficientDet for better performance
3. Real-time deployment on edge devices like Raspberry Pi with camera modules
4. Implement alert systems for live public spaces (buzzer/notifications)
