# 🧠 Convolutional Neural Networks (CNN) – MNIST Experiment  

This project is a **beginner-friendly implementation of a Convolutional Neural Network (CNN)** using **TensorFlow/Keras**. The goal was to explore how CNNs can classify handwritten digits from the **MNIST dataset**.  

## 📌 Overview  
- Built a CNN step by step with convolutional, pooling, fully connected, and dropout layers.  
- Trained on the **MNIST dataset** (28x28 grayscale digit images).  
- Achieved **~99% accuracy** on validation data 🎉.  
- Learned about overfitting and applied **Dropout** to improve generalization.  

## 🗂️ Dataset  
- **MNIST**: 60,000 training images, 10,000 test images.  
- Each image is a **28×28 pixel grayscale digit (0–9)**.  
- Available directly via `tf.keras.datasets.mnist`.  

## ⚙️ Model Architecture  
- 3 × Convolutional layers (`Conv2D`) with ReLU activation  
- 2 × MaxPooling layers  
- Flatten layer  
- 2 × Fully connected (`Dense`) layers with ReLU  
- Dropout layer (0.5) to reduce overfitting  
- Output layer with **Softmax** (10 classes)  
