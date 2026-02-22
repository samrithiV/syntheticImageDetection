# Synthetic Image Detection and Analysis

## Overview
This project focuses on detecting synthetic images and understanding the reliability of these systems. Modern Gen AI models can create highly realistic images, making it difficult to distinguish them from real images. In this project, we not only build a model to detect synthetic images, but we also attempt to intentionally break the model to understand its weaknesses and improve its robustness.

The project is divided into three main phases:
* Build the image classification model
* Try to break the model using high quality synthetic images
* Improvise the model to handle such data
 
## Building the Model
This project builds a synthetic image detection system using a ResNet-50 deep learning model trained on the CIFAKE dataset. The model is designed to classify images as real or synthetic, and the workflow below illustrates the main steps involved in training, prediction, and analysis.

```mermaid
flowchart LR
    A[Load CIFAKE Dataset] --> B[Image Preprocessing]
    B --> C[Load Pretrained ResNet50]
    C --> D[Freeze Early Layers]
    D --> E[Replace Final Layer for 2 Classes]
    E --> F[Train Model]
    F --> G[Validate Each Epoch]
    G --> H[Save Best Model]
    H --> I[Run Prediction]
    I --> J[GradCAM and Saliency Maps]
