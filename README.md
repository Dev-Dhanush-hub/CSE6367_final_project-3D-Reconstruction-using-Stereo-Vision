3D Reconstruction using Stereo Vision: SAD Disparity and Classical Stereo Triangulation
Author
Dhanush Srinivas
Student ID: 1002232331
Course: CSE 6367 - Computer Vision
University of Texas at Arlington
📧 dxs2331@mavs.uta.edu

📌 Project Overview
This project implements a complete classical stereo vision pipeline to reconstruct 3D geometry from 2D image pairs. We use the 2014 Middlebury Stereo Dataset and rely on Sum of Absolute Differences (SAD) for disparity estimation and classical triangulation for depth recovery.

Rather than using deep learning models (which require training and GPU memory), we rely on lightweight, interpretable algorithms, ideal for educational and embedded vision contexts.

🧠 Theory
Stereo vision mimics human depth perception. Two cameras separated by a known baseline capture the same scene from different perspectives. The difference in horizontal location (disparity) allows us to calculate depth using:

ini
Copy
Edit
z = f * b / (d + doffs)
Where:

f = focal length

b = baseline (distance between cameras)

d = disparity

doffs = disparity offset

📁 Dataset
We use the “Recycling” pair from the 2014 Middlebury Stereo Dataset. Images are downsampled to 358x240 for faster computation. Calibration parameters are sourced from the accompanying calib.txt.

⚙️ Pipeline
Preprocessing: Convert to grayscale, resize to 1/8 original.

Disparity Estimation: SAD-based block matching on rectified image pairs.

Post-Processing: Mode filter, averaging, outlier clipping.

Depth Calculation: Triangulation using calibration.

3D Reconstruction: OpenCV and Open3D used to generate .ply point cloud.

Visualization: Plotly used for interactive 3D display.

🖼️ Sample Output
Left Image	Right Image

Disparity Maps

Raw Disparity	Post-Processed

3D Point Cloud Output


🧪 Results
Points generated: ~22,000

SAD Window Size: 11x11

Disparity Range: 0 to 32

Runtime: ~28 seconds on RTX 4060

PLY File Size: ~2.3 MB

Performance Comparison
✅ No training
✅ Runs on modest hardware
✅ Color-preserving .ply output viewable in Blender, MeshLab, CloudCompare

✅ Use Cases
Field Robotics: No LiDAR required

Embedded Vision: Low-memory devices

Educational Tools: Classical methods for teaching CV fundamentals

🔧 Environment & Tools
Component	Version/Specs
OS	Windows 11
IDE	Visual Studio Code
CPU	AMD Ryzen 7
GPU	NVIDIA RTX 4060
Python	3.11
Libraries	NumPy 1.24, OpenCV 4.8, Pillow 9.5, Open3D 0.18, Plotly 5.14

📎 References
Full list available in references.bib.
Key references:

Middlebury Dataset Paper

Howard & Rogers, 2012 – Perceiving in Depth

Yang et al., 2024 – Real-Time SAD on Embedded Platforms

