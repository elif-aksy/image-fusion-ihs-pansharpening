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

## Results

The fusion methods are compared using quantitative image quality metrics.
The table below reports example results obtained from the notebook.

| Method              | PSNR (dB) | MSE        | SAM (deg) |  SCC  |
|---------------------|-----------|------------|-----------|-------|
| IHS-based Fusion    | 26.82     | 0.002078   |   4.87    | 0.996 |
| IHS-like Baseline   | 21.36     | 0.007305   |   5.04    | 0.988 |
| Brovey Transform    | 26.82     | 0.002078   |   4.87    | 0.996 |
| Gram–Schmidt / DI   | 21.73     | 0.006708   |   5.14    | 0.996 |
| Hybrid (IHS+Brovey) | 26.82     | 0.002078   |   4.87    | 0.996 |

Overall observations:
- **IHS-based methods** better preserve color information.
- **Brovey** provides stronger spatial enhancement at the cost of spectral distortion.
- **Hybrid fusion** balances sharpness and color fidelity.

<Figure size 1800x600 with 4 Axes><img width="1415" height="345" alt="image" src="https://github.com/user-attachments/assets/360093aa-d6cc-41bc-ab64-6e980449d160" />
<Figure size 1500x500 with 3 Axes><img width="1151" height="427" alt="image" src="https://github.com/user-attachments/assets/3d9f981a-490d-4378-8423-1eadeb36d01a" />

