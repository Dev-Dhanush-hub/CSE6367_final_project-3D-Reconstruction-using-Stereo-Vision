# Stereo Vision 3D Reconstruction

This project implements a classical stereo vision pipeline using Sum of Absolute Differences (SAD) for disparity estimation, followed by post-processing and 3D point cloud generation. Built using Python, OpenCV, and Open3D, the system reconstructs depth from stereo image pairs with calibration data.

## 📁 Dataset
- **Source**: Middlebury 2014 Stereo Dataset (Recycling)
- **Input**: Rectified stereo image pair (`im0.png`, `im1.png`)
- **Calibration**: Intrinsics and baseline from `calib.txt`

## 🛠️ Features
- Grayscale image preprocessing and resizing
- SAD-based disparity estimation
- Mode filtering, smoothing, and thresholding
- Depth calculation via calibrated triangulation
- `.ply` point cloud generation with color mapping
- Interactive 3D visualization using Plotly

## 📦 Dependencies
- Python 3.11
- NumPy
- OpenCV 4.8+
- Pillow
- Open3D 0.18+
- Plotly

Install via:
```bash
pip install -r requirements.txt


Dhanush Srinivas
GitHub: https://github.com/Dev-Dhanush-hub/CSE6367_final_project-3D-Reconstruction-using-Stereo-Vision
UTA ID: 1002232331