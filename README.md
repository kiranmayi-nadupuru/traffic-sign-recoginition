# Traffic Sign Recognition using EfficientNetB0

## 🚦 Project Overview

This project focuses on recognizing and classifying traffic signs using **deep learning and transfer learning**.

The project uses the **German Traffic Sign Recognition Benchmark (GTSRB)** dataset and an **EfficientNetB0-based image classification model**. EfficientNetB0 is a pretrained convolutional neural network that uses **ImageNet pretrained weights** to extract useful visual features for traffic sign classification.

The project was developed and tested using **Google Colab with TensorFlow/Keras**.

---

## 🎯 Objectives

- Recognize and classify different types of traffic signs.
- Preprocess traffic sign images for deep learning.
- Apply **transfer learning using EfficientNetB0**.
- Use **ImageNet pretrained weights** for feature extraction.
- Train a multi-class traffic sign classification model.
- Evaluate the model using test data and classification metrics.
- Analyze classification performance using a confusion matrix.
- Predict previously unseen traffic sign images.

---

## 📊 Dataset

The project uses the **GTSRB (German Traffic Sign Recognition Benchmark)** dataset.

### Dataset Source

[GTSRB - German Traffic Sign Recognition Benchmark](https://www.kaggle.com/meowmeowmeowmeowmeow/gtsrb-german-traffic-sign)

### Dataset Details

| Property | Details |
|---|---:|
| Training Examples | 31,367 |
| Validation Examples | 7,842 |
| Testing Examples | 12,630 |
| Number of Classes | 43 |

The dataset contains images belonging to different categories of German traffic signs.

---

## 🔧 Data Preprocessing

The traffic sign images are preprocessed before being provided to the EfficientNetB0 model.

The preprocessing pipeline includes:

- Resizing images to the required input size.
- Preparing images in RGB format.
- Normalizing pixel values.
- Preparing the dataset for multi-class classification.
- Splitting the data into training, validation, and testing sets.

---

## 🧠 Model Architecture

The main deep learning architecture used in this project is **EfficientNetB0**.

EfficientNetB0 is a convolutional neural network pretrained on the **ImageNet** dataset. Transfer learning is used to take advantage of the features learned from ImageNet and adapt them to the traffic sign classification task.

The EfficientNetB0 base model is loaded using TensorFlow/Keras:

```python
base_model = EfficientNetB0(
    weights="imagenet",
    include_top=False,
    input_shape=(IMG_SIZE, IMG_SIZE, 3)
)

base_model.trainable = False
```
---

## 🧠 EfficientNetB0 Configuration

- **Architecture:** EfficientNetB0
- **Pretrained Weights:** ImageNet
- **Include Top:** False
- **Input Format:** RGB
- **Input Shape:** `(IMG_SIZE, IMG_SIZE, 3)`
- **Transfer Learning:** Yes
- **Base Model:** Initially Frozen
- **Number of Classes:** 43

The pretrained **EfficientNetB0** is used as the feature extraction backbone for traffic sign classification.

---

## 🔄 Transfer Learning

- **Technique:** Transfer Learning
- **Pretrained Model:** EfficientNetB0
- **Pretrained Dataset:** ImageNet
- **Base Model:** Initially frozen
- **Purpose:** Use pretrained visual features for traffic sign classification
- **Classification Task:** 43-class traffic sign recognition

The EfficientNetB0 base model is initially frozen so that its pretrained features can be used as a feature extractor for the traffic sign classification task.

---

## 🤔 Why EfficientNetB0?

EfficientNetB0 was selected for this project because it provides a good balance between:

- **Model Performance:** Provides strong performance for image classification.
- **Computational Efficiency:** Requires fewer computational resources compared with larger models.
- **Model Size:** EfficientNetB0 is relatively lightweight and suitable for practical applications.
- **Training Requirements:** Suitable for transfer learning and can be trained efficiently using pretrained ImageNet weights.

This makes **EfficientNetB0** suitable for image classification tasks such as traffic sign recognition.

---

## 📈 Model Evaluation

The trained model was evaluated using the test dataset containing **12,630 images**.

### 📊 Test Results

- **Test Loss:** 0.3518
- **Test Accuracy:** **92.03%**
- **Macro Average F1-score:** 0.8624
- **Weighted Average F1-score:** 0.9194

The model achieved a **test accuracy of 92.03%** on the GTSRB test dataset.

### Model Accuracy

![Model Accuracy](accuracy.png)

### Confusion Matrix

![Confusion Matrix](confusion_matrix.png)

### Prediction Output

![Prediction Output](prediction.png)

---

## 🛠️ Technologies Used

- Python
- TensorFlow
- Keras
- NumPy
- Pandas
- Matplotlib
- Scikit-learn
- Google Colab
- Jupyter Notebook

---

## 📂 Project Structure

```text
traffic-sign-recoginition/
│
├── 📓 Traffic_Sign_Recoginition.ipynb
├── 📄 README.md
├── 📄 requirements.txt
├── 📄 .gitignore
├── 🖼️ accuracy.png
├── 🖼️ confusion_matrix.png
└── 🖼️ prediction.png

```
---

## 📌 Conclusion

This project uses **ImageNet-pretrained EfficientNetB0** and transfer learning for traffic sign recognition on the **GTSRB dataset**. The model classifies **43 traffic sign classes** and achieved **92.03% test accuracy** with a **0.9194 weighted F1-score** on **12,630 test images**.

---

## 👩‍💻 Author

**Kiranmayi Nadupuru**

GitHub: [kiranmayi-nadupuru](https://github.com/kiranmayi-nadupuru)
