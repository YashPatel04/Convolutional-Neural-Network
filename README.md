# Digit Detection Using MNIST Dataset  

Author: [Yash Patel](https://yashbpatel.vercel.app)  

## 📌 Dataset  
This project uses the **MNIST dataset**, an open-source collection of handwritten digit images (0–9).  
- **60,000 training images**  
- **10,000 testing images**  
- Each image is **28 × 28 pixels**, grayscale  
- Each image is labeled with the digit it represents (0–9)  

## 🎯 Objective  
The goal of this project is to build a **Convolutional Neural Network (CNN)** that can recognize and classify handwritten digits with high accuracy.  

## 🛠 Preprocessing  
- **Normalization:** Pixel values were scaled to the range [0,1] for faster convergence.  
- **One-hot encoding:** Labels were converted to vectors so that the model outputs probabilities across 10 classes.  

## 🏗 Model Architecture  
The model is a **CNN**, consisting of the following layers:  

1. **Conv2D (32 filters, 3×3, ReLU)** ×2  
   - Extracts local features (edges, corners, textures).  
   - ReLU introduces non-linearity.  

2. **MaxPooling2D (2×2)**  
   - Reduces spatial dimensions, speeds up computation, and reduces overfitting.  

3. **Dropout (25%)**  
   - Randomly drops neurons during training to prevent overfitting.  

4. **Conv2D (128 filters, 3×3, ReLU)** ×2  
   - Learns deeper, more detailed patterns.  

5. **MaxPooling2D (2×2) + Dropout (25%)**  

6. **Conv2D (256 filters, 3×3, ReLU)**  
   - Detects high-level abstract features.  

7. **MaxPooling2D (2×2) + Dropout (25%)**  

8. **Flatten**  
   - Converts 2D feature maps into a 1D vector.  

9. **Dense Layers**  
   - 128 → 128 → 100 → 80 → 40 neurons (ReLU)  
   - Fully connected layers for feature combination.  

10. **Dense (10, Softmax)**  
   - Outputs probabilities for digits 0–9.  
   - The highest probability corresponds to the predicted digit.  

## ⚙️ Training & Testing  
- **Optimizer:** Adam (adaptive learning rate)  
- **Loss Function:** Categorical Cross-Entropy (multi-class classification)  
- **Metric:** Accuracy  

The model was trained for **10 epochs** with a **batch size of 128**.  

## 📊 Results  
- **Test Accuracy:** **99.36%** on the 10,000 test images  
- The model demonstrates excellent performance in handwritten digit recognition.  

---
