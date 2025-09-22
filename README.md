# 🐟 Freshwater Fish Disease Classification using ResNet50

This project implements a **deep learning-based image classification system** to identify **freshwater fish diseases** in aquaculture in South Asia.  
The model leverages **Transfer Learning** with **ResNet50** pretrained on ImageNet to achieve high accuracy on multi-class disease detection.

---

## 📌 Motivation

Fish diseases cause **significant losses in aquaculture**.  
Manual detection is **time-consuming and error-prone**, especially with visually similar diseases.  
This project aims to **automate disease identification** using computer vision and deep learning to support aquaculture monitoring and management.

---

## 📂 Dataset

- **Source:** Freshwater Fish Disease Aquaculture in South Asia  
- **Training Images:** 1747  
- **Test Images:** 697  
- **Classes (7 disease categories):**
  - Fungal diseases Saprolegniasis  
  - Bacterial diseases  
  - Parasitic diseases  
  - Viral diseases  
  - Injuries  
  - Nutritional deficiencies  
  - Healthy fish  

### 📊 Dataset Split
- **Training Set:** 90%  
- **Validation Set:** 10%  
- **Test Set:** Used for final evaluation  

---

## ⚙️ Methodology

### 1. Data Preprocessing
- Images resized to **256×256** and normalized (`rescaling 1./255`).  
- **Data augmentation** applied to training data: random rotations.  

### 2. Model Architecture
#### 🔹 Transfer Learning with ResNet50
- **Base Model:** ResNet50 (pretrained on ImageNet)  
- **Top Layers:** Flatten → Dense(384, ReLU) → Dense(7, Softmax)  
- **Frozen Base Layers** to retain pretrained features.  

#### 🔹 Training Configuration
- **Optimizer:** Adam  
- **Loss Function:** Sparse Categorical Crossentropy  
- **Batch Size:** 32  
- **Epochs:** 20  
- **Callbacks:** ModelCheckpoint to save best model  

---

## 📈 Results

- **Training Accuracy:** ~94.25%  
- **Validation Accuracy:** ~93.75%  
- **Test Accuracy:** ~93.4%  
- **F1 Score:** 0.935  
- **Precision:** 0.943  
- **Recall:** 0.934  

### 🔹 Confusion Matrix
- High precision across all disease categories  
- Some misclassifications between visually similar diseases  

---

## 📊 Visualizations

- **Sample Images** from each class  
- **Training vs Validation Accuracy & Loss Curves**  
- **Confusion Matrix** for performance evaluation  
- **Predicted vs Actual samples** on test dataset  

---

## 🚀 How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/fish-disease-classification.git
   cd fish-disease-classification
