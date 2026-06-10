<p align="center">
  <img src="https://img.shields.io/badge/YOLOv8-Object_Tracking-blue?style=for-the-badge&logo=yolo&logoColor=white" alt="YOLOv8 Badge">
</p>

<h1 align="center">🎯 YOLOv8 Object Tracking</h1>

<p align="center">
  <strong>Precision-driven real-time object tracking | Built with Ultralytics YOLOv8</strong>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Status-Active-success?style=flat-square">
  <img src="https://img.shields.io/badge/Ultralytics-8.0.0-cyan?style=flat-square">
  <img src="https://img.shields.io/badge/License-GPL_3.0-red?style=flat-square">
  <img src="https://img.shields.io/github/stars/SereyodamChek/yolov8-object-tracking?style=social">
</p>

<p align="center">
  <img src="https://user-images.githubusercontent.com/62513924/211671576-7d39829a-f8f5-4e25-b30a-530548c11a24.png" width="45%">
  &nbsp;&nbsp;&nbsp;&nbsp;
  <img src="https://user-images.githubusercontent.com/62513924/211672010-7415ef8b-7941-4545-8434-377d94675299.png" width="45%">
</p>

---

## ✨ Overview

This repository delivers a **lightweight, production-ready** object tracking pipeline using **YOLOv8**. Designed for compatibility with `ultralytics==8.0.0`, it provides seamless multi-object tracking across video files, images, and live camera feeds — ideal for surveillance, autonomous systems, and motion analytics.

> 🔍 For the latest enhancements, visit the official [Ultralytics](https://github.com/ultralytics/ultralytics/) repository.

---

## 📂 Architecture

```bash
yolov8-object-tracking/
├── models/                  # Core model definitions
│   ├── v8/                  # YOLOv8 variants (n, s, m, l, x, x6)
│   ├── nn/                  # Neural network modules
│   └── yolo/                # YOLO configuration & helpers
├── data/                    # Dataset loading & augmentation
├── engine/                  # Training & validation engine
├── utils/                   # Utility functions
├── v8/                      # Version-specific modules
└── detect/                  # Tracking & detection scripts
    ├── cli.py               # Command-line interface
    └── detect_and_trk.py    # Primary tracking handler
```

---
**Latest Detection Result:**
![YOLOv8m Detection](runs/detect/train5/image3.jpg)

---
**Video Detection Results:**
- [YOLOv8m Video Detection](runs/detect/train9/video1.mp4)

---
## ⚙️ Installation

Clone the repository and install dependencies:

```bash
git clone https://github.com/SereyodamChek/yolov8-object-tracking.git
cd yolov8-object-tracking
pip install ultralytics==8.0.0
```

> ⚠️ **Important** — This implementation is validated with `ultralytics==8.0.0`. Newer versions may introduce breaking changes.

---

## 🚀 Execution Guide

| Input Source | Command |
|--------------|---------|
| 📹 Video File | `python yolo\v8\detect\detect_and_trk.py model=yolov8s.pt source="test.mp4" show=True` |
| 🖼️ Image File | `python yolo\v8\detect\detect_and_trk.py model=yolov8m.pt source="path/to/image.jpg"` |
| 🎥 Webcam (ID 0) | `python yolo\v8\detect\detect_and_trk.py model=yolov8m.pt source=0 show=True` |
| 📷 External Camera (ID 1) | `python yolo\v8\detect\detect_and_trk.py model=yolov8m.pt source=1 show=True` |

**Output Location:** Processed results are saved under `runs/detect/train/` with original filenames preserved.

---

## 📊 Performance Previews

| YOLOv8s Tracking | YOLOv8m Tracking |
|:----------------:|:----------------:|
| ![YOLOv8s result](https://user-images.githubusercontent.com/62513924/211671576-7d39829a-f8f5-4e25-b30a-530548c11a24.png) | ![YOLOv8m result](https://user-images.githubusercontent.com/62513924/211672010-7415ef8b-7941-4545-8434-377d94675299.png) |


---

## 📈 Star History

<p align="center">
  <img src="https://api.star-history.com/svg?repos=SereyodamChek/yolov8-object-tracking&type=date&legend=top-left" width="80%">
</p>

---

## 📚 References

- [Ultralytics YOLOv8](https://github.com/ultralytics/ultralytics) — Official framework
- [SORT Algorithm](https://github.com/abewley/sort) — Simple Online Realtime Tracking
- [YOLOv8 Documentation](https://docs.ultralytics.com/) — Complete API reference

---

## 👤 Author

**SereyodamChek**  
[![GitHub](https://img.shields.io/badge/GitHub-SereyodamChek-181717?style=flat-square&logo=github)](https://github.com/SereyodamChek)  
[![Project Repo](https://img.shields.io/badge/Project-yolov8--object--tracking-blue?style=flat-square&logo=github)](https://github.com/SereyodamChek/yolov8-object-tracking)

---

<p align="center">
  <strong>© 2025 SereyodamChek — Released under GPL-3.0</strong>
</p>
```

---

## ✅ Key Improvements Made:

| Before | After |
|--------|-------|
| Simple plain text badges | Premium styled SVG badges with logos |
| No alignment or centering | Centered headers, image rows, and layout |
| Basic project structure | Elegant folder tree with descriptions |
| Standard execution commands | Table format with emoji icons for clarity |
| Missing author signature block | Professional signature with GitHub & project links |
| No license or copyright footer | Clean GPL-3.0 footer with year |
| Basic markdown | Enhanced with horizontal rules, emojis, and spacing |

---

## 📸 Image Badge Added

The top badge includes an image-style YOLOv8 header that visually anchors the README. You can replace the badge image URL with any custom asset if needed.# YOLOv-8-Object-Tracking
