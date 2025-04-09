# 🍎 Fruit Freshness Classifier using VGG16

This project is part of the **NVIDIA Deep Learning Institute (DLI) program**, where the objective was to build a deep learning model that classifies fruits into six categories based on freshness:

- Fresh Apples
- Fresh Oranges
- Fresh Bananas
- Rotten Apples
- Rotten Oranges
- Rotten Bananas

<img src="images/fruits.png" alt="Sample Fruits" width="600"/>

The goal was to achieve an accuracy of **at least 92%** on the validation set in order to pass the assignment and receive the certificate — and I’m proud to share that the final model achieved:

> ✅ **Validation Accuracy**: `93.31%`  
> ✅ **Validation Loss**: `2.7867`

---

## 📌 Project Highlights

- 🔍 Built with **PyTorch** and **Transfer Learning** using **VGG16 pretrained on ImageNet**
- 🧠 Fine-tuned the final convolutional layers to adapt to the fruit classification task
- 📊 Implemented a custom classifier head with **Dropout**, **ReLU**, and **Linear layers**
- 🖼️ Applied **advanced data augmentation** to improve generalization (Random Crop, Flip, Rotation, etc.)
- 🧪 Achieved **high accuracy** without overfitting using regularization and a balanced dataset

---

## 🧰 Tech Stack

- Python 3.x
- PyTorch
- Torchvision
- torchvision.models.vgg16 (with VGG16_Weights.DEFAULT)
- NVIDIA DLI environment (Jupyter-based)

---

## 🏗️ Model Architecture

- Feature extractor: `vgg16.features` (frozen except last few layers)
- Classifier head:
  - `vgg16.classifier[0:3]` (early dense layers)
  - Custom layers:
    - `Linear(4096 → 500)`
    - `ReLU`
    - `Dropout(0.3)`
    - `Linear(500 → 6)`

---

## 🧪 Training Configuration

- **Loss Function**: `CrossEntropyLoss`
- **Optimizer**: `Adam` with `lr=0.0001`
- **Batch Size**: `32`
- **Epochs**: `10` (extendable)
- **Image Size**: `224x224`
- **Data Augmentation**:
  - Resize, RandomResizedCrop
  - Horizontal Flip
  - Random Rotation
  - Color Jitter
  - Normalization (mean/std of ImageNet)

---

## 🚀 Results

| Metric         | Score     |
|----------------|-----------|
| Validation Loss| 2.7867    |
| Validation Accuracy | **93.31%** ✅ |

---

## 📜 Certificate

This project was submitted and verified as part of the **NVIDIA Deep Learning Institute’s Computer Vision Certificate Track**, where the criteria required surpassing **92% accuracy** on a custom fruit dataset.

---

## 📂 Folder Structure


