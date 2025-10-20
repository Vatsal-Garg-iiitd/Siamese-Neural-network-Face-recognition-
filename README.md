# 🧠 Siamese Neural Network for Face Recognition

This project implements a **Siamese Neural Network (SNN)** for **face recognition and verification**, inspired by [Nicholas Renotte’s YouTube tutorial](https://www.youtube.com/c/NicholasRenotte).  
The network learns to determine whether two face images belong to the same person by comparing their feature embeddings rather than classifying identities directly.

---

## 📸 Project Overview

The Siamese Neural Network is a type of **twin neural network** architecture that takes **two input images** and outputs their **similarity score**.  
It is trained to **minimize the distance** between embeddings of the same person and **maximize it** for different people.  

This approach is useful for:
- Face recognition  
- Signature verification  
- One-shot learning tasks  

---

## ⚙️ Features

- ✅ Face verification using contrastive loss  
- ✅ Preprocessing pipeline for image loading, resizing, and normalization  
- ✅ Positive and negative pair generation  
- ✅ Built using **TensorFlow/Keras**  
- ✅ Evaluation with accuracy and distance metrics  
- ✅ Save and load trained models easily  

---

## 🧩 Architecture

The model uses a **convolutional base network (CNN)** that extracts feature embeddings from input images.  
Two identical CNN branches (with shared weights) process the image pair, and their embeddings are compared using a **distance metric (L1 or Euclidean)** followed by a **sigmoid output layer** to predict similarity.

