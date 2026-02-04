# Image Fusion & Resolution Enhancement using IHS Pansharpening

## Overview
This project implements an **IHS (Intensity–Hue–Saturation) pansharpening** pipeline to fuse a **low-resolution RGB** image with a **high-resolution grayscale** image in order to produce a sharper, high-resolution color output.

In addition to visual comparisons, the results are evaluated using quantitative image quality metrics.

---

## Problem
In many real-world scenarios (e.g., imaging systems and remote sensing), we may have:
- a **low-resolution color (RGB)** image, and
- a **high-resolution grayscale** (or panchromatic) image.

The goal is to combine them to obtain a **high-resolution color image** that preserves both:
- spatial detail (from grayscale), and
- color information (from RGB).

---

## Method (IHS Pansharpening)
1. Convert RGB → IHS
2. Match intensity / histogram (if applicable)
3. Replace or fuse the **Intensity** channel using the high-resolution grayscale image
4. Convert IHS → RGB to obtain the enhanced output

---

## Evaluation
The pipeline includes quantitative evaluation using metrics such as:
- **MSE**
- **PSNR**
- **SAM** (Spectral Angle Mapper) *(if available in the notebook)*

Visual comparisons are also provided throughout the notebook.

---

## Tech Stack
- Python
- NumPy
- OpenCV / scikit-image
- Matplotlib

---

## How to Run
1. Clone the repository
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
