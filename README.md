﻿# Microstructure-Image-Denoising

# UNet-based Denoising Autoencoder for Microstructure-like Images

This project implements a deep **UNet-style Convolutional Autoencoder** to denoise images corrupted by Gaussian noise. The model architecture is inspired by biomedical and material-science applications where structural detail recovery is crucial, making it relevant for research environments like **IIT Hyderabad’s GOKUL Lab**.

---

## 🔍 Problem Statement

Noise in images—especially microstructure images in material science—can significantly impact downstream analysis like segmentation, classification, and pattern recognition. Traditional autoencoders often blur fine details during denoising due to loss of spatial information.

---

## 🎯 Objective

Build a **deep convolutional denoising architecture** using UNet principles to:
- Effectively remove Gaussian noise from images
- Preserve spatial features and textural integrity
- Demonstrate relevance for scientific imaging and metallurgical applications

---

## 🧠 Model Architecture

- **Type**: UNet-style Convolutional Autoencoder  
- **Encoder**: 2 downsampling blocks (Conv2D + MaxPooling)  
- **Bottleneck**: Deep convolutional layers  
- **Decoder**: 2 upsampling blocks with **skip connections**  
- **Output**: 64x64x3 denoised image via `sigmoid` activation  

Skip connections enable the model to retain high-frequency features, resulting in sharper and more detailed reconstructions.

---

## 🧪 Dataset

- **Base**: CIFAR-10 (resized to 64×64)  
- **Noise**: Gaussian noise (variance = 0.01) added using `skimage.util.random_noise`  
- Though not true microstructure data, CIFAR-10's texture diversity simulates complex structural noise patterns.

---

## 📈 Training Details

- **Epochs**: 30  
- **Batch Size**: 64  
- **Loss Function**: Mean Squared Error (MSE)  
- **Optimizer**: Adam  
- **Validation Split**: 10%

---

## 📊 Results

| Image | Description |
|-------|-------------|
| ![](examples/noisy.png) | Noisy Input |
| ![](examples/denoised.png) | Denoised Output |
| ![](examples/original.png) | Ground Truth |

The model learns to effectively reconstruct the clean image, reducing Gaussian noise while retaining edge structure and textures.

---

## 🧩 Applications

- **Metallurgical microstructure denoising**
- **Preprocessing for segmentation models**
- **Scientific imaging enhancement**
- **Noise-robust computer vision pipelines**

---

## ✅ Tech Stack

- Python, TensorFlow / Keras  
- NumPy, Matplotlib, Scikit-image  
- Deep CNN, Autoencoders, UNet architecture

---

## 📌 Future Improvements

- Add **perceptual loss** (e.g., VGG-based) for more photorealistic results  
- Train on **real microstructure datasets**  
- Experiment with **Denoising Diffusion Models (DDPM)**
