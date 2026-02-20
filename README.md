# 🍎 CNN Fruit Classification

CNN-based multi-class fruit image classification with structured hyperparameter tuning and stability evaluation.

## 📌 Project Overview

This project implements a Convolutional Neural Network (CNN) to classify fruit images into **14 categories**.

The focus of this work was not only on achieving high accuracy, but on:

- Systematic architectural exploration  
- Controlled hyperparameter tuning  
- Stability validation through repeated runs  
- Explicit overfitting checks  

## 🧠 Model Architecture

The model follows a VGG-style convolutional design:

- Three convolutional stages  
- ReLU activation  
- MaxPooling  
- Dense layer (64 units)  
- Dropout (0.3)  
- Softmax output (14 classes)  

The implementation was structured using an object-oriented design (`FruitClassifier`) to support reproducible experimentation.

## 🔍 Hyperparameter Exploration

### Structural Parameters Tested

- Filters: `[16, 32, 16]` vs `[32, 64, 32]`
- Kernel size: `3×3` vs `5×5`
- Dense units: `32` vs `64`
- Stride: `1` vs `2`

Model capacity was evaluated before training.  
Architectures exceeding **10× dataset size** were flagged and excluded.

### Training Parameters Tested

- Optimizer: **Adam** vs **SGD**  
- Learning rate variations  
- Batch size: `32` vs `64`  

A total of **24 hyperparameter combinations** were evaluated across **five repeated runs**.

The final configuration was selected based on validation stability and consistency.

## ⚙️ Final Configuration

- Filters: `[16, 32, 64]`
- Kernel size: `(3, 3)`
- Stride: `2`
- Dense units: `64`
- Optimizer: `Adam`
- Learning rate: `0.001`
- Batch size: `32`
- Dropout rate: `0.3`

## 📊 Model Evaluation

The final model was tested using **663 unseen images**.

Across six independent test runs:

- 100% accuracy in 4 runs  
- 99.85% accuracy in 2 runs  

Worst-case performance showed minor confusion between visually similar classes (e.g., Apricot and Strawberry), while the remaining classes maintained perfect precision and recall.

## ✨ Why This Project Matters

This project demonstrates:

- Structured experimental design  
- Model capacity control  
- Stability validation  
- Practical generalisation awareness  

## 📖 Project Documentation

A detailed explanation of the experimental design, architectural decisions, hyperparameter tuning process, and evaluation analysis is available here:

👉 [Full Project Documentation (Notion)](https://www.notion.so/Convolutional-Neural-Network-for-Multi-Class-Fruit-Image-Classification-30cd6b546c7a80ffae92e2fec8632361?source=copy_link)
