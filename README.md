# Synthetic Image Detection and Analysis

## Overview
With the rapid development of generative AI models, synthetic images are becoming increasingly realistic and difficult to distinguish from real photographs. This creates challenges in areas such as misinformation detection, digital forensics, and cybersecurity.  
In this project, we build a deep learning system capable of detecting synthetic images and analyze how robust the model is when faced with adversarial image modifications.

Our work follows a research-oriented workflow:

1. **Build** – Train a synthetic image detection model  
2. **Break** – Apply adversarial modifications to fool the detector  
3. **Improve** – Propose a mitigation strategy based on observed weaknesses  

The complete experimental analysis and results are available in the [**full project report**](https://docs.google.com/document/d/18w2fyaXJejX5-pdx30O5_YTF_keLgAn0sTKeSDNP7Wg/edit?usp=sharing).

---

## Model Development
We implemented a synthetic image classification model using a **pretrained ResNet-50 architecture** and fine-tuned it on the **CIFAKE dataset**, which contains both real and synthetic images.

Instead of training a model entirely from scratch, we used **transfer learning**:
- Early layers of the network were **frozen** to retain pretrained visual features.
- The final classification layer was **replaced and retrained** to classify images into two categories: **REAL** and **FAKE**.
- The model was trained using supervised learning with labeled data.

The overall workflow of the model pipeline is shown below:

```mermaid
flowchart LR
    A[Load CIFAKE Dataset] --> B[Preprocess Images]
    B --> C[Load Pretrained ResNet50]
    C --> D[Freeze Early Layers]
    D --> E[Replace Final Layer]
    E --> F[Train Model]
    F --> G[Validate Model]
    G --> H[Save Best Model]
    H --> I[Make Predictions]
    I --> J[Generate GradCAM and Saliency Maps]
