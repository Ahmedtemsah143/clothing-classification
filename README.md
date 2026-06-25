# clothing-classification
# 👕 Clothing Classification Model

This repository contains the core code and documentation for a multi-label Computer Vision model built to categorize clothing items. This model automatically sorts and classifies apparel, making it highly effective for organizing large inventories, such as categorizing donated clothing items for charitable platforms.

## 🚀 Live Demo
The model is deployed with an interactive UI using Gradio. 
👉 **[Click here to try the model on Hugging Face Spaces](https://huggingface.co/spaces/Ahmedtem/clothes)** *(Replace `#` with your Space URL)*

## 🧠 Model Overview
* [cite_start]**Framework:** FastAI  
* [cite_start]**Architecture:** Fine-tuned `resnet18` [cite: 110]
* **Task:** Multi-label Image Classification. [cite_start]It predicts both the clothing type (e.g., T-Shirt, Dress) and the target demographic (Kids vs. Adults) simultaneously[cite: 11, 79].
* [cite_start]**Input Resolution:** Images are processed with a `RandomResizedCrop` of 128x128 pixels[cite: 96].

## 📊 Dataset
[cite_start]The model was trained on the `agrigorev/clothing-dataset-full` sourced from Kaggle.
* [cite_start]The dataset spans 20 labels, including T-Shirt, Longsleeve, Pants, Shoes, Shirt, Dress, Outwear, and Shorts[cite: 69].
* [cite_start]**Data Preprocessing:** The original boolean `kids` column was mapped to explicit 'Kids' and 'Adults' labels [cite: 79][cite_start], and then concatenated with the clothing type to create a comprehensive classification target[cite: 80]. 

## ⚙️ Training & Performance
* [cite_start]The model was initialized with pre-trained ImageNet weights (`resnet18`) and fine-tuned for 8 epochs[cite: 110, 111].
* [cite_start]**Metrics:** Evaluated using `accuracy_multi` with a threshold of `0.2`[cite: 110].
* [cite_start]**Results:** Reached over **96.6% multi-label accuracy** on the validation set by the final epochs[cite: 115].
* [cite_start]Threshold analysis was conducted to find the optimal confidence score for separating predictions[cite: 116, 121, 122].

## 💻 Local Usage & Inference

If you want to run the model locally, follow these steps:

### 1. Install Dependencies
```bash
pip install fastai
