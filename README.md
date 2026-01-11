# Human-Activity-Recognition-from-Smartphone-Accelerometer-Data

This repository contains an end-to-end analysis of human activity recognition (HAR) using the WISDM accelerometer dataset. The project evaluates both classical machine learning algorithms and deep learning architectures to classify physical activities such as walking, jogging, sitting, standing, and stair-related movements.

The work compares k-Nearest Neighbors (kNN), Support Vector Machines (SVM), Multilayer Perceptrons (MLP), Convolutional Neural Networks (CNN), Long Short-Term Memory networks (LSTM), and Bidirectional LSTMs (BiLSTM), highlighting how each approach performs on raw sensor windows. This project was completed as part of **SYDE 522 (Machine Intelligence)** at the University of Waterloo.  

---

## Dataset

The project uses the **WISDM v1.1** smartphone accelerometer dataset:

- **Tri-axial acceleration signals**
- **20 Hz sampling rate**
- **36–51 participants reported across sources**
- Activities include:
  - Walking  
  - Jogging  
  - Sitting  
  - Standing  
  - Walking upstairs  
  - Walking downstairs

Windowed segments (≈ 5–10 seconds) are used as model inputs, flattened or kept as sequences depending on the model.  


---

## Models Implemented

### **Classical ML Models**
- **kNN** (k = 3, 5, 7; Euclidean & Manhattan distances)
- **SVM** (RBF kernel; grid search over C ∈ {0.1, 1, 10} and γ ∈ {scale, auto})

### **Deep Learning Models**
- **Multilayer Perceptron (MLP)** — varying hidden sizes (64, 128, 256)
- **Convolutional Neural Network (CNN)** — kernel sizes of 3, 5, 7  
- **LSTM** — hidden sizes {32, 64, 128}  
- **Bidirectional LSTM** — hidden sizes {32, 64, 128}

Architectures, hyperparameters, and loss functions follow Sections I–B and II–C of the report.  


---

## Key Findings

- **SVM and CNN were the top-performing models**, reaching weighted F1-scores of **0.807** and **0.796**, respectively.
- **CNNs** excel due to strong local pattern extraction in short accelerometer windows.
- **SVM** performs robustly even with handcrafted statistical features.
- **MLP** performs moderately well but lacks temporal modeling capability.
- **LSTM/BiLSTM underperform**, likely due to:
  - Short window sizes
  - Limited long-range temporal structure
