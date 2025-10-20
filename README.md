# 🧠 Siamese Neural Network for Face Recognition

This project implements a **Siamese Neural Network (SNN)** for **face recognition and verification**, inspired by [Nicholas Renotte’s YouTube tutorial](https://www.youtube.com/c/NicholasRenotte).  
The network learns to determine whether two face images belong to the same person by comparing their **feature embeddings** rather than classifying identities directly.

---

## 📸 Project Overview

The Siamese Neural Network is a type of **twin neural network** architecture that takes **two input images** and outputs their **similarity score**.  
It is trained to **minimize the distance** between embeddings of the same person and **maximize it** for different people.  

This approach is useful for:
- Face recognition  
- Signature verification  
- One-shot or few-shot learning tasks  
- Person re-identification  

---

## ⚙️ Features

- ✅ Face verification using **Contrastive Loss**
- ✅ Custom preprocessing pipeline for image loading, resizing, and normalization
- ✅ Automatic positive and negative pair generation
- ✅ Built using **TensorFlow / Keras**
- ✅ Real-time verification using webcam or pre-stored images
- ✅ Performance evaluation using **accuracy and distance metrics**
- ✅ Save and load trained models easily for inference

---

## 🧩 Architecture

The architecture follows a **twin CNN structure** with shared weights.

1. **Base Network (Embedding Model):**
   - A Convolutional Neural Network (CNN) that extracts a fixed-dimensional embedding from an input face.
   - Shared weights ensure that both branches learn the same feature representation.

2. **Similarity Computation:**
   - The embeddings from both branches are compared using a **distance function** (L1 or Euclidean).
   - The result is passed through a **Dense layer with a sigmoid activation** to output similarity between 0 and 1.

3. **Loss Function:**
   - **Contrastive Loss** is used to penalize incorrect similarity predictions for positive and negative pairs.

---

## 🧠 Model Pipeline

**Input:** Two face images (Anchor and Positive/Negative)  
**Output:** A similarity score between 0 and 1  

**Training Steps:**
1. Load and preprocess face images.  
2. Generate pairs:  
   - **Positive pair:** Two images of the same person.  
   - **Negative pair:** Images of two different people.  
3. Pass the pairs through the Siamese Network.  
4. Train using **Contrastive Loss**:
   \[
   L = (1 - Y) \frac{1}{2}(D_w)^2 + (Y)\frac{1}{2}\{max(0, m - D_w)\}^2
   \]
   Where \(Y\) is the label (1 for dissimilar, 0 for similar) and \(D_w\) is the distance between embeddings.

---

## 📈 Future Improvements

- Implement triplet loss for better separation.  
- Add real-time webcam-based facial verification.  
- Use a pre-trained embedding extractor (e.g., FaceNet or MobileNet).  
- Optimize model for mobile deployment using TensorFlow Lite.  

---

## 🧑‍💻 Author

**Developed by:** Vatsal Garg
**Inspired by:** [Nicholas Renotte’s Tutorial on YouTube](https://www.youtube.com/c/NicholasRenotte)  
**Tools Used:** TensorFlow, Keras, OpenCV, Python  

---

## 📜 License

This project is open source and available under the **MIT License**.

---

