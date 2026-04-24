# Representation Learning with Autoencoders (AE & VAE)

## Overview

This project investigates representation learning using Autoencoders (AE) and Variational Autoencoders (VAE). The objective is to learn compact latent representations of image data and analyze their effectiveness in reconstruction, generation, and denoising tasks.

The implementation is built using TensorFlow and Keras, with a focus on understanding how latent spaces are structured and utilized in both deterministic and probabilistic models.

---

## Objectives

* Develop and train an Autoencoder (AE) for data reconstruction
* Implement a Variational Autoencoder (VAE) with probabilistic latent space
* Visualize latent representations in two dimensions
* Compare AE and VAE performance in reconstruction and generation
* Explore denoising and sample generation capabilities

---

## Project Structure

AE_VAE_Assignment/
│
├── notebooks/
│   └── AE_VAE_Assignment.ipynb
│
├── models/
│   ├── ae_model.keras
│   ├── vae_weights.weights.h5
│
├── report/
│   └── AE_VAE_Technical_Report.pdf
│
├── README.md

---

## Dataset

The project uses the MNIST dataset, which consists of 28x28 grayscale images of handwritten digits. The dataset is normalized to the range [0, 1] and processed using a tf.data pipeline for efficient training.

---

## Methodology

### Autoencoder (AE)

The Autoencoder consists of an encoder and a decoder. The encoder compresses the input image into a lower-dimensional latent vector, while the decoder reconstructs the image from this representation. The model is trained using Mean Squared Error (MSE) as the reconstruction loss.

### Variational Autoencoder (VAE)

The Variational Autoencoder extends the AE by learning a probabilistic latent space. The encoder outputs the mean and log variance, and latent vectors are sampled using the reparameterization trick. The loss function combines reconstruction loss with KL divergence to enforce a structured latent distribution.

---

## Results and Analysis

### Reconstruction

The Autoencoder produces sharp and accurate reconstructions of input images. The Variational Autoencoder produces slightly blurred outputs due to the regularization imposed by the KL divergence term.

### Latent Space

The latent space learned by the Autoencoder is unstructured and scattered. In contrast, the VAE latent space is organized and approximately follows a Gaussian distribution centered around zero, enabling smoother transitions and better generalization.

### Image Generation

The VAE is capable of generating new samples by sampling from the latent space. The generated images resemble handwritten digits but are slightly blurred, which is expected behavior for VAEs.

### Denoising

A denoising Autoencoder is trained by introducing noise to input images and learning to reconstruct clean versions. The model successfully removes noise while preserving the underlying digit structure.

### Loss Behavior

During VAE training, the reconstruction loss decreases steadily, while the KL divergence term stabilizes. This indicates a balance between accurate reconstruction and maintaining a meaningful latent distribution.

---

## AE vs VAE Comparison

| Feature        | Autoencoder (AE) | Variational Autoencoder (VAE) |
| -------------- | ---------------- | ----------------------------- |
| Latent Space   | Deterministic    | Probabilistic                 |
| Reconstruction | Sharp            | Smooth                        |
| Generation     | Limited          | Effective                     |
| Sampling       | Not supported    | Supported                     |
| Structure      | Unstructured     | Gaussian                      |

---

## How to Run

1. Open the notebook located in the notebooks directory:
   notebooks/AE_VAE_Assignment.ipynb

2. Run all cells in Google Colab

3. Ensure that:

   * GPU is enabled
   * Dataset is properly loaded

---

## Saved Models

* ae_model.keras: trained Autoencoder model
* vae_weights.weights.h5: trained VAE weights

---

## Report

A detailed technical report is available in:
report/AE_VAE_Technical_Report.pdf

---

## Conclusion

This project demonstrates the differences between deterministic and probabilistic representation learning. Autoencoders are effective for reconstruction and compression tasks, while Variational Autoencoders provide a structured latent space that enables meaningful data generation and exploration.
