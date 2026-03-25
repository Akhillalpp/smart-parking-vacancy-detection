# Smart Parking Vacancy Detection using YOLO

📄 Published in IEEE ICCC 2023

An intelligent computer vision system for detecting vacant parking spaces from surveillance camera footage using YOLO-based object detection and custom algorithms for both demarcated and non-demarcated parking lots.

---

## 📌 Overview

Urban areas suffer from inefficient parking usage due to lack of real-time vacancy information. This project proposes a vision-based smart parking system that detects occupied and vacant parking spaces using camera feeds.

Unlike traditional approaches, this system works for:
- Parking lots with marked slots  
- Open/unstructured parking areas (no slot boundaries)

---

## ⚙️ Approach

### 1. Vehicle Detection
- YOLOv3 is used to detect cars in each frame
- Outputs bounding boxes with confidence scores

### 2. Motion Filtering
- Moving vehicles are filtered using IoU-based frame comparison
- Only stationary vehicles are considered for occupancy

### 3. Vacancy Detection

#### Case A: Demarcated Parking
- Total capacity is predefined
- Vacant slots = Capacity − Detected vehicles

#### Case B: Non-Demarcated Parking (Key Contribution)

Two custom approaches:

**Sliding Window Estimation**
- Scans image using reference car dimensions
- Detects regions with low overlap

**Reference Box Algorithm (Improved)**
- Uses a fully occupied parking image as baseline
- Compares overlap to detect vacancy
- Handles irregular layouts and orientations

---

## 📊 Results

<img src="images/eq3.PNG" width="300">

- Average Precision (AP): ~88.25%  
- Accuracy (Non-demarcated parking): ~96.47%  
- Robust performance across:
  - Different lighting conditions  
  - Irregular parking layouts  
  - Partial occlusions  

---

## 📄 Publication

**Machine Learning based Vacant Space Detection for Smart Parking Solutions**  
Presented at *IEEE International Conference on Control, Communication and Computing (ICCC)*, 2023  
📍 Thiruvananthapuram, India  
📅 May 2023  
🔗 DOI: https://doi.org/10.1109/ICCC57789.2023.1016555

