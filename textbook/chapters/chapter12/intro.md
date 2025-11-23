# Chapter 12: Generative Models

**<span style="font-size:1.5em;">Introduction</span>**

Generative models aim to learn how data is produced so they can create new samples that resemble the real world. Instead of predicting labels, these models focus on understanding the underlying distribution of a dataset and generating synthetic examples drawn from that learned distribution.

The central idea is to approximate the true data distribution with a model distribution and then sample from it. This requires learning how to capture structure, variability, and uncertainty in the data. Generative modeling also supports tasks such as synthesis, simulation, anomaly detection, and data augmentation.

Modern generative approaches include density-based models, latent-variable models, adversarial training, and diffusion frameworks. Each method provides a different way to represent and generate data.

This chapter introduces the foundations of generative modeling and prepares the reader for the detailed topics covered in the following sections:

12.1 Synthetic vs. Real-World Data  
12.2 Generative Models Overview  
12.3 Gaussian Mixture Models (GMMs)  
12.4 Variational Autoencoders (VAEs)  
12.5 Generative Adversarial Networks (GANs)  
12.6 Sampling Methods
