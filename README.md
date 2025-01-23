# IntroGANProj  

An introductory Generative Adversarial Network (GAN) project designed to understand how GANs work by generating handwritten digits similar to those in the MNIST dataset.

---

## Overview  
The goal of this project is to train a simple GAN to generate realistic grayscale images of handwritten digits from random latent vectors. This project served as a stepping stone for understanding GAN architecture, training processes, and their applications before moving on to more advanced GAN projects.

---

## Dataset  
**Dataset Used:** [MNIST Handwritten Digits Dataset](http://yann.lecun.com/exdb/mnist/)  

- Contains 60,000 training images and 10,000 test images of handwritten digits (28x28 grayscale).
- Images were rescaled to the range [-1, 1] during preprocessing for training stability.

---

## Project Structure  

### 1. **IntroGANProj_training_mnist.py**  
This script trains the GAN on the MNIST dataset. Key components:  
- **Generator:**  
  - Accepts a 100-dimensional random latent vector.  
  - Outputs a 28x28 grayscale image (range [-1, 1]).  
- **Discriminator:**  
  - Takes in 28x28 grayscale images.  
  - Outputs a single value indicating whether the image is real or fake.  

#### Training Details:  
- **Optimizer:** Adam (Learning Rate: 0.0002, Beta 1: 0.5)  
- **Loss Function:** Binary Crossentropy for both generator and discriminator.  
- **Batch Size:** 32  
- **Training Duration:** 100,000 epochs  
- **Saving Outputs:** Saves generated samples every 10 epochs to visualize GAN progress.

---

### 2. **IntroGANProj_predict_mnist.py**  
This script loads the trained generator model (`generator_model.h5`) to generate and visualize new images.  
Key Features:  
- Generates a single random image from a latent vector.  
- Generates multiple images (e.g., a 4x4 grid) for better visualization.  

---

## How to Run  

### Prerequisites  
Ensure the following libraries are installed:  
- `tensorflow`  
- `keras`  
- `numpy`  
- `matplotlib`  

### Training  
To train the GAN:  
```bash
python IntroGANProj_training_mnist.py
