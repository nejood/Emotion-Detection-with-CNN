# Emotion Detection using Convolutional Neural Networks (CNN)

## Overview
This project implements a deep learning model for facial emotion recognition using a Convolutional Neural Network (CNN). The model is trained to classify facial expressions into seven emotional categories using grayscale images.

The goal of this project is to automatically detect human emotions from facial images using deep learning techniques.

---

## Student Information
**Name:** Nujud Abdulaziz Alghamdi  
**Student Number:** 2300450  
**Assignment:** Emotion Detection with CNN

---

## Dataset
The dataset used in this project is the **FER Emotion Detection dataset** obtained from Kaggle.

It contains facial images categorized into seven emotion classes:

- Angry  
- Disgusted  
- Fearful  
- Happy  
- Neutral  
- Sad  
- Surprised  

### Dataset Structure
dataset/
│
├── train/
│ ├── angry
│ ├── disgusted
│ ├── fearful
│ ├── happy
│ ├── neutral
│ ├── sad
│ └── surprised
│
└── test/
├── angry
├── disgusted
├── fearful
├── happy
├── neutral
├── sad
└── surprised

### Dataset Size

- Training images: **22,967**
- Validation images: **2,871**
- Test images: **2,871**

---

## Technologies Used

The project is implemented in **Python** using the following libraries:

- TensorFlow / Keras
- NumPy
- Pandas
- Matplotlib
- Seaborn
- Scikit-learn
- KaggleHub

---

## Data Preprocessing

The following preprocessing steps were applied:

- Converting images to **grayscale**
- Resizing images to **48 × 48 pixels**
- Splitting the dataset into:
  - **Training set (80%)**
  - **Validation set (10%)**
  - **Test set (10%)**
- Creating image generators using `ImageDataGenerator`
- Batch size: **64**

---

## CNN Model Architecture

The CNN model consists of several layers designed to extract features from facial images.

### Convolutional Blocks

Each block includes:

- Convolution layer
- Batch normalization
- Max pooling
- Dropout

The model includes:

- Conv2D layers with **32, 64, 128, and 512 filters**
- Kernel sizes **3×3 and 5×5**
- **Batch Normalization** for stable training
- **Dropout layers** to reduce overfitting
- **L2 Regularization** in deeper layers

### Fully Connected Layers

After feature extraction, the model includes:

- Flatten layer
- Dense layer (256 neurons)
- Dense layer (512 neurons)
- Output layer with **7 neurons** using **Softmax activation**

### Model Parameters

Total parameters: **4,496,903**

---

## Model Training

The model was trained using:

- **Optimizer:** Adam  
- **Loss Function:** Sparse Categorical Crossentropy  
- **Evaluation Metric:** Accuracy  
- **Epochs:** 20  

Training and validation accuracy and loss were tracked during training.

---

## Model Evaluation

### Test Accuracy

The final model achieved approximately:

**58% accuracy on the test dataset**

### Classification Report

| Emotion | Precision | Recall | F1-score |
|--------|-----------|--------|---------|
| Angry | 0.50 | 0.48 | 0.49 |
| Disgusted | 1.00 | 0.05 | 0.09 |
| Fearful | 0.43 | 0.33 | 0.37 |
| Happy | 0.87 | 0.75 | 0.80 |
| Neutral | 0.57 | 0.57 | 0.57 |
| Sad | 0.39 | 0.65 | 0.49 |
| Surprised | 0.80 | 0.56 | 0.66 |

---

## Model Visualization

The project includes several visualizations:

- Sample images from the dataset
- Data distribution of emotion classes
- Training vs validation accuracy
- Training vs validation loss
- Confusion matrix

---

## Sample Prediction

The trained model can predict the emotion of a given facial image.

Example prediction:
Predicted Emotion: happy

---


---

## References

- https://www.kaggle.com/code/kirollosashraf/emotion-detection-cnn
- https://www.kaggle.com/code/odins0n/emotion-detection
- https://www.kaggle.com/code/kanncaa1/deep-learning-tutorial-for-beginners
- https://www.comet.com/site/blog/how-to-train-your-deep-learning-models-faster/
- https://stackoverflow.com

---

## Conclusion

This project demonstrates the use of **Convolutional Neural Networks for facial emotion recognition**. Although the model achieved moderate accuracy, performance can be improved by:

- Applying stronger **data augmentation**
- Using **transfer learning models** such as ResNet or VGG
- Training with larger datasets
- Performing hyperparameter tuning
