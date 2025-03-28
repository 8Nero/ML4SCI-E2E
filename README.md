This repository contains Jupyter notebooks for the tasks: Electron/Photon Classification and Semi-Supervised Symmetry Discovery.

## Common Task 1. Electron/Photon classification
**Description**: Binary classification problem for 32×32 matrices (with energy and time channels).

**Model Architecture:** A custom ResNet15 model is used. The model architecture contains an initial 5x5 convolutional layer, 3 ResNet blocks, followed by a dropout layer and a fully-connected layer. 

Since the data sample is only 32x32 size, I used 5x5 kernel for the initial convolutional layer instead of the standard 7x7 kernel size.

**Optimiser:** Adam with Reduce Learning on Plateau.

**Notebook**: [![Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1EdVOdGL6L_yyi5rEg8x0eTKhx2bS0Cfv?usp=sharing)

**Weights**: https://drive.google.com/file/d/1tV7p5oU6uDoWKYavzMcwqXrDxNtntSlH/view?usp=sharing

**Results**: AUC score: 0.8044

<p float="left">
  <img src="https://github.com/8Nero/ML4SCI-E2E/blob/main/images/loss_curves.png" width="50%"  />
  <img src="https://github.com/8Nero/ML4SCI-E2E/blob/main/images/auc_curve.png" width="50%" />
  <img src="https://github.com/8Nero/ML4SCI-E2E/blob/main/images/roc_curve.png" width="50%" />
</p>

## Task 2j: Semi-Supervised Symmetry Discovery

**Task 1**: Train VAE for rotated MNIST (1s and 2s)
**Task 2**: Supervised symmetry discovery using MLP on latent space
**Task 3**: Unsupervised symmetry discovery with latent dimensions 2 and 5

The notebook `task2-part1.ipynb` contains supervised symmetry and unsupervised symmetry discovery task (with latent dimension 2).
While `task2-part2.ipynb` contains unsupervised symmetry discovery task with latent dimension 5 and multiple generators were trained.

**Notebook 1**: [![Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/18q5ip3GeaPOhZ3lDZPXDK4-U6tGxtg0V?usp=sharing)

**Notebook 2**: [![Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1s8NBza49b5LRmLp2nAlBKUSjN4mKxR4O?usp=sharing)

**Results**
The supervised symmetry discovery task was successfully completed. For the unsupervised symmetry discovery, the notebooks are divided into two parts. In the first part, I used latent dimension of size 2 for the VAE and used a single generator NN model for discovering symmetries. The model seems to have discovered rotational symmetry on the digit 1. The generator doesn't seem to effectively rotate the digit 2, which might be constrained by the VAE model's performance.

<p float="left">
  <img src="https://github.com/8Nero/ML4SCI-E2E/blob/main/images/gen1-2d.png" width="50%"  />
  <img src="https://github.com/8Nero/ML4SCI-E2E/blob/main/images/latent_flow.png" width="50%" />
</p>

In the second part, I increased VAE model's latent dimension to 5 and trained four generator models. These models seem to be stuck on trivial transformations.

<p float="left">
  <img src="https://github.com/8Nero/ML4SCI-E2E/blob/main/images/gens-5d.png" width="50%"  />
</p>

