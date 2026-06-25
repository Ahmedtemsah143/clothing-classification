# clothing-classification
# 👕 Clothing Classification Model

This repository contains the core code and documentation for a multi-label Computer Vision model built to categorize clothing items. This model automatically sorts and classifies apparel, making it highly effective for organizing large inventories, such as categorizing donated clothing items for charitable platforms.

## 🚀 Live Demo
The model is deployed with an interactive UI using Gradio. 
👉 **[Click here to try the model on Hugging Face Spaces](https://huggingface.co/spaces/Ahmedtem/clothes)**  

## 🧠 Model Overview
* **Framework:** FastAI  
* **Architecture:** Fine-tuned `resnet18` 
* **Task:** Multi-label Image Classification. It predicts the clothing type (e.g., T-Shirt, Dress) and the target demographic (Kids vs. Adults) simultaneously.
* **Input Resolution:** Images are processed with a `RandomResizedCrop` of 128x128 pixels.

## 📊 Dataset
[THE DATASET](https://www.kaggle.com/datasets/agrigorev/clothing-dataset-full) was taked from the `agrigorev/clothing-dataset-full` sourced from Kaggle.
* The dataset spans 20 labels, including T-Shirt, Longsleeve, Pants, Shoes, Shirt, Dress, Outwear, and Shorts[cite: 69].
* **Data Preprocessing:** The original boolean `kids` column was mapped to explicit 'Kids' and 'Adults' labels , and then concatenated with the clothing type to create a comprehensive classification target[cite: 80]. 

## ⚙️ Training & Performance
* The model was initialized with pre-trained ImageNet weights (`resnet18`) and fine-tuned for 8 epochs.
* **Metrics:** Evaluated using `accuracy_multi` with a threshold of `0.2`.
* **Results:** Reached over **96.6% multi-label accuracy** on the validation set by the final epochs.
* Threshold analysis was conducted to find the optimal confidence score for separating predictions
