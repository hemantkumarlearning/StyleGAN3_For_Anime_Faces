# Anime Face GAN using StyleGAN3
This repository contains the implementation of a generative adversarial network (GAN) model trained to generate high-quality anime faces. The model is built using StyleGAN3, a state-of-the-art generative model for high-quality image synthesis. The dataset used for training consists of various anime face images sourced from Kaggle.

![Screenshot 2025-03-10 124014](https://github.com/user-attachments/assets/10241780-2ebe-4a17-b80b-2599d7e28049)

# Table of Contents
-Overview
-Installation
-Dataset
-Training the Model
-Generating Images
-Model Evaluation
-Licensing

# Overview
This project uses StyleGAN3, a powerful architecture for generating high-quality, realistic images. The goal is to generate anime-style faces that resemble the aesthetic of popular anime characters.

The process involves:

1. Collecting an anime face dataset.
2. Preprocessing the dataset into a format suitable for training (TFRecords).
3. Training the model using StyleGAN3.
4. Using the trained model to generate new anime faces.

# Installation
## 1. Clone the repository
git clone https://github.com/your-username/anime-face-gan.git
cd anime-face-gan

## 2. Install Dependencies
python3 -m venv stylegan3-env
source stylegan3-env/bin/activate  # On Windows, use `stylegan3-env\Scripts\activate`
pip install -r requirements.txt

## 3. Install StyleGAN3
git clone https://github.com/NVlabs/stylegan3.git
cd stylegan3
pip install -r requirements.txt


