# Basic Cat Image Generator 
 
# 🐱 Basic Cat Image Generator

This project implements a Generative Adversarial Network (GAN) using TensorFlow/Keras to generate synthetic 32×32 pixel images of cats, based on the CIFAR-10 dataset. It demonstrates the application of adversarial training for class-specific image generation in the context of AI-generated content (AIGC).

---

## 📌 Project Overview

- **Goal**: Generate visually coherent images of cats using a class-conditional GAN.
- **Dataset**: CIFAR-10 (filtered for class label = 3, corresponding to cats).
- **Image Size**: 32x32x3 RGB.
- **Model Type**: Deep Convolutional GAN (DCGAN-style).

---

## ⚙️ Technologies Used

- Python
- TensorFlow & Keras
- NumPy
- Matplotlib (for visualization)
- CIFAR-10 dataset (via Keras API)

---

## 🧪 Key Steps

### 1. Data Preprocessing
- Loaded CIFAR-10 dataset using Keras.
- Filtered images with class label `3` (cats only).
- Reshaped to 32x32x3 and normalized pixel values to `[-1, 1]`.
- Merged training and test sets to create a unified dataset for GAN training.

### 2. Model Architecture

#### Generator
- Input: 100-dimensional noise vector.
- Layers: Dense → BatchNorm → LeakyReLU → Conv2DTranspose → `tanh` activation.

#### Discriminator
- Input: 32×32×3 image.
- Layers: Conv2D → LeakyReLU → Dropout → Dense → Sigmoid.

### 3. Training
- Trained for 100+ epochs.
- Used Binary Crossentropy loss.
- Monitored convergence through image sampling every 5 epochs.

---

## 🎯 Results

- Successfully generated low-resolution cat images.
- Observed improvement in image quality across training epochs.
- Visual outputs were saved and displayed using Matplotlib.

---

## 📁 Files

- `GAN.ipynb`: Main notebook for training the GAN model.
- `README.md`: Project overview and instructions.
- `.gitattributes`: Git metadata.

---

## 🔗 Future Work

- Upgrade model to conditional GAN (cGAN) with multi-class support.
- Train on higher-resolution datasets (e.g. CelebA, LSUN).
- Deploy image generation as a web app using Streamlit or Flask.

---

## 🚀 How to Run

```bash
# Clone the repository (if public)
git clone https://github.com/yourusername/Basic-Cat-Image-Generator.git

# Install dependencies
pip install tensorflow matplotlib numpy

# Open and run the notebook
jupyter notebook GAN.ipynb
