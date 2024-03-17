# PINN-Classification

This repository contains the solution to the evaluation test of the GSoC: ML4Sci Project named Deeplense. The project aims to explore deep learning techniques for gravitational lensing analysis.

## Overview
In this repository, you will find two main notebooks:

1. **multiclassclassification.ipynb**: This notebook contains the training process for the common task, which involves multi-class classification of strong lensing images into three categories: images with no substructure, subhalo substructure, and vortex substructure.

2. **PINN-GravitationalLensingeq.ipynb**: This notebook is dedicated to the specific task 5, where we implement a Physics Informed Neural Network (PINN) architecture. The goal is to utilize the gravitational lensing equation within the architecture to enhance the network's performance compared to the results obtained in the common task.

**My Approach for integrating Gravitational Lensing Equation with neural network:**


1. **Encoder for Feature Extraction:**
   - I use a pre-trained Resnet18 model as the encoder to extract features from the observed images.
   - 
2. **Lens Equation and Source Image Reconstruction:**
   - I implement a lensing equation method within the model to compute the angular distortion caused by gravitational lensing.
   - Using this equation, I generate reconstructed source images by applying the angular distortion to the observed images.
   - This step effectively accounts for the gravitational lensing effects, providing a more accurate representation of the true source images.

3. **Classification Component:**
   - After reconstructing the source images, I concatenate them with the observed images to create two-channel input images.
   - These two-channel images are then passed through a secondary encoder model, which performs the classification task.
