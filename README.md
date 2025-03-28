This repository contains Jupyter notebooks for the tasks: Electron/Photon Classification and Semi-Supervised Symmetry Discovery.

## Common Task 1. Electron/Photon classification
**Description**: Binary classification problem for 32×32 matrices (with energy and time channels).

**Model Architecture:** A custom ResNet15 model is used. The model architecture contains an initial 5x5 convolutional layer, 3 ResNet blocks, followed by a dropout layer and a fully-connected layer. 

Since the data sample is only 32x32 size, I used 5x5 kernel for the initial convolutional layer instead of the standard 7x7 kernel size.

**Optimiser:** Adam with Reduce Learning on Plateau.

**Files**:
- `particle_classification.ipynb`: Contains data loading, model training, and evaluation
- `model_weights.pth`: Trained model weights

**Notebook**: [![Colab](https://colab.research.google.com/assets/colab-badge.svg)]([https://colab.research.google.com/github/your-username/your-repo/blob/main/MNIST_Symmetry_Discovery.ipynb](https://colab.research.google.com/drive/1EdVOdGL6L_yyi5rEg8x0eTKhx2bS0Cfv?usp=sharing))
**Weights** https://drive.google.com/file/d/1tV7p5oU6uDoWKYavzMcwqXrDxNtntSlH/view?usp=sharing
**Results**

## Task 2j: Semi-Supervised Symmetry Discovery

**Task 1**: Train VAE for rotated MNIST (1s and 2s)
**Task 2**: Supervised symmetry discovery using MLP on latent space
**Task 3**: Unsupervised symmetry discovery with latent dimensions 2 and 5

The notebook `task2-part1.ipynb` contains supervised symmetry and unsupervised symmetry discovery task (with latent dimension 2).
While `task2-part2.ipynb` contains unsupervised symmetry discovery task with latent dimension 5 and multiple generators were trained.

**Files**:
- `symmetry_discovery.ipynb`: Contains all three subtasks

**Tasks**:
1. Dataset preparation with 30° rotations of digits 1 and 2
2. Supervised symmetry discovery using MLP on latent space
3. Unsupervised symmetry discovery with latent dimensions 2 and 5
