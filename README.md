

# Traffic Sign Recognition

## 🚦 Project Overview

This project focuses on recognizing and classifying traffic signs using deep learning and image classification techniques.

The project uses the **German Traffic Sign Recognition Benchmark (GTSRB)** dataset. The images are preprocessed and used to train a convolutional neural network (CNN) for traffic sign classification.

The project was developed and tested using **Google Colab** with **TensorFlow/Keras**.

---

## 🎯 Objectives

- Recognize and classify different types of traffic signs.
- Preprocess traffic sign images for model training.
- Build and train a CNN-based image classification model.
- Evaluate the model using test data.
- Predict previously unseen traffic sign images.

---

## 📊 Dataset

The project uses the **GTSRB (German Traffic Sign Recognition Benchmark)** dataset.

Dataset source:

[GTSRB - German Traffic Sign Recognition Benchmark](https://www.kaggle.com/meowmeowmeowmeowmeow/gtsrb-german-traffic-sign)

### Dataset Details

- **Training examples:** 31,367
- **Validation examples:** 7,842
- **Testing examples:** 12,630
- **Number of classes:** 43
- **Image shape:** `(32, 32, 1)`
- **Image type:** Grayscale

---

## 🔧 Data Preprocessing

The original traffic sign images have different sizes, so they were processed into a consistent format.

The preprocessing steps include:

- Resizing images to `32 × 32`
- Converting images to grayscale
- Normalizing pixel values
- Splitting the dataset into training, validation, and testing sets

---

## 🧠 Model Architecture

The project uses **EfficientNetB0** as the main deep learning architecture for traffic sign classification.

EfficientNetB0 is a convolutional neural network pretrained on the **ImageNet** dataset. Transfer learning is used to take advantage of the features learned from ImageNet and adapt them to the traffic sign classification task.

The EfficientNetB0 base model is loaded using TensorFlow/Keras:

```python
base_model = EfficientNetB0(
    weights="imagenet",
    include_top=False,
    input_shape=(IMG_SIZE, IMG_SIZE, 3)
)

base_model.trainable = False

---

## 📈 Model Evaluation

The trained model was evaluated using the test dataset containing **12,630 images**.

### Test Results

| Metric | Result |
|---|---:|
| Test Loss | 0.3518 |
| Test Accuracy | **92.03%** |
| Macro Average F1-score | 0.8624 |
| Weighted Average F1-score | 0.9194 |

The model achieved a **test accuracy of 92.03%** on the GTSRB test dataset.

---

## 📸 Results

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
traffic-sign-recognition/
│
├── Traffic_Sign_Recognition.ipynb
├── README.md
├── requirements.txt
├── .gitignore
├── accuracy.png
├── confusion_matrix.png
└── prediction.png
