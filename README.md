# Anime Face GAN using StyleGAN3
This repository contains the implementation of a generative adversarial network (GAN) model trained to generate high-quality anime faces on google colab. The model is built using StyleGAN3, a state-of-the-art generative model for high-quality image synthesis. The dataset used for training consists of various anime face images sourced from Kaggle.

![Screenshot 2025-03-10 124014](https://github.com/user-attachments/assets/10241780-2ebe-4a17-b80b-2599d7e28049)

# Table of Contents
- Overview
- Installation
- Dataset
- Training the Model
- Generating Images

# Overview
This project uses StyleGAN3, a powerful architecture for generating high-quality, realistic images. The goal is to generate anime-style faces that resemble the aesthetic of popular anime characters.

The process involves:

1. Collecting an anime face dataset.
2. Preprocessing the dataset into a format suitable for training (TFRecords).
3. Training the model using StyleGAN3.
4. Using the trained model to generate new anime faces.

# Installation
## 1. Clone the repository
```
git clone https://github.com/your-username/anime-face-gan.git
cd anime-face-gan
```
Now you have the jupyter notebook

## 2. Install StyleGAN3
```
git clone https://github.com/NVlabs/stylegan3.git
cd stylegan3
```
Install Necessary Libraries:-
```
!pip install torch torchvision numpy scipy tqdm
```

# Dataset
I used Kaggle for downloading dataset here is the link https://www.kaggle.com/datasets/arnaud58/selfie2anime.
You must have a kaggle API key to download this dataset. Follow the notebook to download and preprocess the dataset.

The dataset contain 4 folder test A, test B, train A, train B. Remove all folders except train B and rename the folder to images.
Now convert images into tfrecords using this :-
```
!mkdir outputs
!python dataset_tool.py --source=/content/selfie2anime/processed_anime_images --dest=anime_tfrecords --resolution=256x256
```

# Training the Model
Once your dataset is ready create a folder output in stylegan3 folder, this folder contain the final model, images etc.
```
!python train.py --outdir=/content/stylegan3/outputs \
                 --cfg=stylegan3-t \
                 --data=anime_tfrecords \
                 --gpus=1 \
                 --batch=8 \
                 --snap=10 \
                 --gamma=5 \
                 --kimg=5000 \
                 --metrics=fid50k_full
```



