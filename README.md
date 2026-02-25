# ASL Alphabet Classification Model 

This project focuses on training a deep learning model to classify **American Sign Language (ASL) alphabets (A–Z)** along with special classes **Delete, Nothing, and Space** from processed hand sign images.

---

## Dataset

We have used the **ASL Alphabet Dataset** for training and evaluation.

### Dataset Link
**ASL Alphabet Dataset:**  
-> https://www.kaggle.com/datasets/grassknoted/asl-alphabet

This dataset contains labeled images of hand signs for all 26 alphabets (A–Z) and additional classes:
- **Delete**
- **Nothing**
- **Space**

Each class has multiple images to support reliable training.

Total Classes Used: **29 (26 Alphabets + 3 Special Classes)**

---

## Project Description

This repository contains the implementation of a **Convolutional Neural Network (CNN)** model trained to recognize ASL alphabet hand signs.

The model takes preprocessed hand images (skeleton/landmark-based or processed images) as input and predicts one of the 29 classes:

- A–Z  
- Delete  
- Nothing  
- Space  

This project covers:

- Data preprocessing  
- Feature extraction  
- Model architecture  
- Model training  
- Model evaluation  
- Saving the trained model  
- Model prediction (inference on new images)

---

## Model Details

### Model Type
Convolutional Neural Network (CNN)

### Input
- Preprocessed hand sign images  
- Resized and normalized  
- Shape depends on training configuration  

### Output
- 29 classes (A–Z + Delete + Nothing + Space)  
- Softmax activation in output layer  

### Architecture (Typical Structure)
- Convolutional Layers  
- ReLU Activation  
- MaxPooling Layers  
- Flatten Layer  
- Fully Connected (Dense) Layers  
- Output Layer (Softmax)

### Loss Function
Categorical Crossentropy

### Optimizer
Adam

### Evaluation Metric
Accuracy

---

## Training Process

1. Load dataset  
2. Preprocess images (resize, normalize)  
3. Encode labels (One-Hot Encoding)  
4. Split into training and validation sets  
5. Train model using `model.fit()`  
6. Evaluate performance  
7. Save trained model (`.h5`)  

---

## Prediction (Model Inference)

After training, the saved model can be loaded to predict ASL alphabets and special classes from new input images.

The prediction process includes:

1. Loading the trained model.  
2. Providing a new hand sign image as input.  
3. Preprocessing the image in the same way as during training (resizing, normalization, etc.).  
4. Passing the processed image to the model.  
5. Obtaining the predicted class using the highest probability from the Softmax output layer.  

The model outputs one of the following 29 classes:

- A–Z  
- Delete  
- Nothing  
- Space  

It is important that:
- The input image size matches the training configuration.
- The preprocessing steps remain consistent with training.
- The class label order remains the same as used during training.

---

## Model Performance

- **Training Accuracy:** 0.9779  
- **Validation Accuracy:** 0.9876
- **Test Accuracy:** 0.9890
- **Number of Epochs:** 35
<img width="1319" height="853" alt="image" src="https://github.com/user-attachments/assets/5dd93b03-e7b3-403e-aae6-ae8dc0e0b20f" />
<img width="1299" height="848" alt="image" src="https://github.com/user-attachments/assets/74977ab6-2f64-4d61-b74a-62814c719984" />


---

Note: The trained model file is not included in this repository due to GitHub size limitations.
Please download it from the link above and place it in the project root directory.
-> https://www.kaggle.com/models/harshdabhiz/asl-classification

## Purpose

The goal of this model is to create a reliable ASL classifier that can later be integrated into:

- Real-time recognition systems  
- Text conversion systems  
- Assistive communication tools  
