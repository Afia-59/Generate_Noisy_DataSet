# Generate_Noisy_DataSet

This repository contains an R script that adds two types of noise—Gaussian noise and spike noise—to hyperpolarized gas (HPG) MRI images. The script simulates realistic imaging artifacts, helping researchers study the impact of noise in MRI processing and deep learning models.


## Introduction
MRI images often contain two types of noise that affect their quality and accuracy:

-  Random Gaussian Noise: Caused by thermal fluctuations and electronic system noise.
- Spike Noise: High-intensity values in k-space, often due to hardware instability or interference.
This script simulates these noise types in Fourier-transformed images and generates a noisy dataset that can be used for testing noise reduction algorithms, deep learning models, or statistical analysis.

## Noise Types
- Gaussian Noise:	Random fluctuations in pixel intensity	Added to real and imaginary components of k-space
- Spike Noise:	Isolated high-intensity points in k-space	Injected at random locations with varying magnitudes

## Installation & Dependencies
Prerequisites
Make sure you have R installed on your system. You can download it from:
🔗 https://cran.r-project.org/

## Required R Packages
Ensure you have the following R packages installed before running the script:

```bash
install.packages("stats")
```

## Usage
## Step 1: Set Up Directories
Modify the script to specify:
source_dir → Directory containing original HPG MRI images in .Rdata format.
output_dir → Directory where noisy datasets will be saved.
## Step 2: Run the Script

## Step 3: Output Files
After execution, the script generates and saves noisy images with:

- Original MRI image
- Fourier Transformed (FT) image
- Noisy Fourier Transformed image
- Inverse Fourier Transformed noisy image (back to image space)

## How It Works
1. Loads Original MRI Data
    Reads .Rdata files containing HPG MRI images.
2. Performs Fourier Transform (FT)
    Converts images to k-space representation using FFT.
3. Adds Noise to k-space
    Randomly selects Gaussian noise or spike noise.
    Gaussian noise: Generated from a normal distribution and added to k-space.
    Spike noise: Random high-intensity spikes are inserted at different locations.
4. Performs Inverse FT
    Converts noisy k-space data back to image space using inverse FFT.
5. Saves Processed Data
     Noisy and original images are saved for further analysis.
