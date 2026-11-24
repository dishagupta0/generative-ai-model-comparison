# Generative Image Modeling on Fashion-MNIST

**Comparing VAEs, GANs, and diffusion models using PyTorch**

This project documents an experimental comparison of three generative modeling approaches on [Fashion-MNIST](https://github.com/zalandoresearch/fashion-mnist):

- **Variational Autoencoder (VAE)** — reconstructs inputs through a learned latent distribution.
- **Generative Adversarial Network (GAN)** — trains a generator and discriminator adversarially.
- **Denoising Diffusion Probabilistic Model (DDPM)** — learns to generate images by reversing a gradual noising process.

I explored model configurations, evaluated the quality of generated images, and examined how training choices affected results.

## Research question

How do VAE, GAN, and diffusion approaches compare in image quality and training behavior on the same small grayscale fashion dataset?

## Dataset and approach

- **Dataset:** Fashion-MNIST (28 × 28 grayscale images across 10 clothing categories)
- **Framework:** PyTorch
- **Experimentation:** Model training, hyperparameter comparisons, generation of sample image grids, and Fréchet Inception Distance (FID) evaluation
- **Evaluation:** Lower FID indicates a closer match between the feature distributions of real and generated images *under the same evaluation protocol*. I also visually inspected samples for recognizability and repetition.

## Selected experimental results

| Model | Training epochs | Selected configuration | FID ↓ |
| --- | ---: | --- | ---: |
| **DDPM** | 30 | 200 diffusion steps; learning rate 0.0001 | **64.44** |
| **VAE** | 30 | Latent dimension 40; β = 0.01; learning rate 0.0003 | 95.70 |
| **GAN** | 40 | Latent dimension 100; learning rate 0.0001 | 171.01 |

These are results from my Fashion-MNIST experiments, rather than claims about the general performance of these architectures. FID values depend on the implementation, sampling procedure, and feature extractor.

## What I learned

1. **Evaluation needs multiple perspectives.** A numerical score is helpful, but looking at generated image grids revealed repetition and uneven representation of clothing categories.
2. **Model settings matter.** I compared training configurations and selected checkpoints based on empirical results rather than relying on defaults.
3. **Model families behave differently.** In these runs, the DDPM achieved the lowest FID; the GAN remained more prone to repetitive, grainy outputs.

## Skills demonstrated

`Python` · `PyTorch` · `Deep Learning` · `Generative Modeling` · `VAE` · `GAN` · `Diffusion Models` · `Hyperparameter Tuning` · `Model Evaluation` · `Experimental Analysis`

## Project materials and code availability

This repository is a **public summary of work completed in academic coursework**. Graded assignment solutions, instructor-provided scaffolding, and private course files are **not published here**. Any future public implementation will be independently developed and checked against applicable course-sharing rules.

## About me

I'm a master's student in Computer Science at Georgia Tech, focusing on machine learning and applied AI. See my [GitHub profile](https://github.com/dishagupta0) for more about my interests and projects.
