# Synthetic Image Detection and Analysis

## Overview
This project focuses on detecting synthetic images and understanding the reliability of these systems. Modern Gen AI models can create highly realistic images, making it difficult to distinguish them from real images. In this project, we not only build a model to detect synthetic images, but we also attempt to intentionally break the model to understand its weaknesses and improve its robustness.

The project is divided into three main phases:
* Build the image classification model
* Try to break the model using high quality synthetic images
* Improvise the model to handle such data
 
## Building the Model
This project explores the use of Convolutional Neural Networks(CNNs) to classify the images as being synthetic or real.
```mermaid
flowchart LR
    A[Input Image] --> B[Convolution Layer]
    B --> C[ReLU Activation]
    C --> D[Pooling Layer]
    D --> E[Feature Maps]
    E --> F[Flatten]
    F --> G[Fully Connected Layer]
    G --> H[Prediction: Real or Synthetic]
