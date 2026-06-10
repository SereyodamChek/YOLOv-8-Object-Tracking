<div align="center">

<!-- Header Banner -->
<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=0:0f2027,50:203a43,100:2c5364&height=200&section=header&text=YOLOv8%20Object%20Tracking&fontSize=48&fontColor=ffffff&fontAlignY=38&desc=Precision-driven%20real-time%20multi-object%20tracking&descAlignY=60&descSize=16&animation=fadeIn" />
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
  <img src="https://img.shields.io/badge/Python-3.8+-blue?style=flat-square&logo=python">
  <img src="https://img.shields.io/badge/OpenCV-4.5+-green?style=flat-square&logo=opencv">
</p>

<p align="center">

  <img src="https://media2.giphy.com/media/v1.Y2lkPTc5MGI3NjExY2N5bWp1ZmxtZ2s3YjRldDJsaDk1eWxpdGp0Z2I5dTNsdDFuMTNxMiZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/26tn33aiTi1jkl6H6/giphy.gif" width="45%">
</p>
<!-- Badges Row -->
<br/>
<br/>

<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=600&size=16&duration=3000&pause=800&color=00CFFF&center=true&vCenter=true&multiline=true&width=600&height=60&lines=Real-time+detection+%2B+tracking+%7C+GPU+accelerated;Video+%E2%80%A2+Webcam+%E2%80%A2+Image+%E2%80%A2+RTSP+%E2%80%94+All+sources+supported" />

</div>

---

## Overview

A **lightweight, production-ready** object tracking pipeline built on **YOLOv8** — one of the fastest and most accurate detection architectures available. This repository integrates the SORT tracking algorithm with Ultralytics' inference engine to deliver frame-by-frame identity-consistent multi-object tracking across any input source.

Engineered for compatibility with `ultralytics==8.0.0`, it is ready for use in surveillance systems, autonomous vehicle pipelines, sports analytics, and industrial motion monitoring.

> **Tip** — For the latest upstream improvements, check the official [Ultralytics repository](https://github.com/ultralytics/ultralytics/).

---

## Architecture

```
yolov8-object-tracking/
│
├── models/                        # Core model definitions
│   ├── v8/                        # YOLOv8 variants — nano, small, medium, large, x, x6
│   ├── nn/                        # Neural network building blocks
│   └── yolo/                      # YOLO config and helper utilities
│
├── data/                          # Dataset loading and augmentation pipeline
├── engine/                        # Training and validation engine
├── utils/                         # Shared utility functions
│
├── v8/                            # Version-specific modules
│   └── detect/                    # Tracking and detection scripts
│       ├── cli.py                 # Command-line interface
│       └── detect_and_trk.py     # Primary tracking handler
│
└── README.md
```

---
**Latest Detection Result:**
![YOLOv8m Detection](results/image3.jpg)

**Video Detection Results:**
- [YOLOv8m Video Detection](https://github.com/SereyodamChek/YOLOv-8-Object-Tracking/raw/main/results/video1.mp4) (Download MP4 - 6.3MB)
- Note: GitHub doesn't preview large video files inline. Use the raw download link above.

## Installation

**Step 1 — Clone the repository**

```bash
git clone https://github.com/SereyodamChek/yolov8-object-tracking.git
cd yolov8-object-tracking
```

**Step 2 — Install dependencies**

```bash
pip install ultralytics==8.0.0
```

> **Warning** — This implementation is validated against `ultralytics==8.0.0` only. Newer versions may introduce API-breaking changes. Pin your environment accordingly.

---

## Usage

Run tracking across any supported input source:

| Source | Command |
|---|---|
| **Video file** | `py -3.13 yolo/v8/detect/detect_and_trk.py model=yolov8s.pt source="test.mp4" show=True` |
| **Image file** | `py -3.13 yolo/v8/detect/detect_and_trk.py model=yolov8m.pt source="path/to/image.jpg"` |
| **Webcam (default)** | `py -3.13 yolo/v8/detect/detect_and_trk.py model=yolov8m.pt source=0 show=True` |
| **External camera** | `py -3.13 yolo/v8/detect/detect_and_trk.py model=yolov8m.pt source=1 show=True` |

> **Note:** Use `py -3.13` to run with Python 3.13 (required for Hydra compatibility). Standard `python` uses Python 3.14 which has compatibility issues.

Processed output is saved under `runs/detect/train/` with original filenames preserved.

---

## Model Variants

| Model | Size | Speed | Accuracy | Best For |
|---|---|---|---|---|
| `yolov8n.pt` | 3.2 MB | ⚡ Fastest | ★★☆☆☆ | Edge / embedded devices |
| `yolov8s.pt` | 11.2 MB | ⚡ Fast | ★★★☆☆ | Real-time inference |
| `yolov8m.pt` | 25.9 MB | ◑ Balanced | ★★★★☆ | General purpose |
| `yolov8l.pt` | 43.7 MB | ◑ Moderate | ★★★★☆ | High-accuracy tasks |
| `yolov8x.pt` | 68.2 MB | ◎ Slower | ★★★★★ | Maximum precision |


---

## How It Works

```
┌─────────────────┐     ┌──────────────────┐     ┌──────────────────────┐
│   Input Source  │────▶│  YOLOv8 Detector │────▶│   SORT Tracker       │
│  Video / Image  │     │  Bounding Boxes  │     │  ID Assignment       │
│  Webcam / RTSP  │     │  + Class Labels  │     │  Kalman Filtering    │
└─────────────────┘     └──────────────────┘     └──────────┬───────────┘
                                                             │
                                                             ▼
                                                  ┌──────────────────────┐
                                                  │  Annotated Output    │
                                                  │  Tracked IDs overlaid│
                                                  │  Saved to runs/      │
                                                  └──────────────────────┘
```

Detection bounding boxes from YOLOv8 are fed into a SORT (Simple Online Realtime Tracking) layer, which uses Kalman filters and the Hungarian algorithm to consistently assign unique IDs to objects across frames — even under occlusion or brief disappearance.

---

## References

| Resource | Description |
|---|---|
| [Ultralytics YOLOv8](https://github.com/ultralytics/ultralytics) | Official framework and pretrained weights |
| [SORT Algorithm](https://github.com/abewley/sort) | Simple Online Realtime Tracking paper & implementation |
| [YOLOv8 Docs](https://docs.ultralytics.com/) | Complete API reference and training guides |

---

## Author

<div align="center">

**SereyodamChek**

[![GitHub Profile](https://img.shields.io/badge/GitHub-SereyodamChek-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/SereyodamChek)
[![Project Repo](https://img.shields.io/badge/Repo-yolov8--object--tracking-0078D6?style=flat-square&logo=github&logoColor=white)](https://github.com/SereyodamChek/yolov8-object-tracking)

</div>

---

<div align="center">

<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=0:2c5364,50:203a43,100:0f2027&height=100&section=footer" />

**© 2025 SereyodamChek — Released under [GPL-3.0 License](LICENSE)**

</div>
