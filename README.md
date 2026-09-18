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
