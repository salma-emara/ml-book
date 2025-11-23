# Generative Models Overview

**<span style="font-size:1.5em;">Generative Models Overview</span>**

Generative models aim to learn how data is produced so they can generate new samples that follow the same statistical structure.  
The central objective is to approximate the true data distribution $p_{\text{data}}(x)$ with a model distribution $p_{\theta}(x)$.

A common learning strategy is maximum likelihood:

$$
\theta^{*} = \arg\max_{\theta} \sum_{i=1}^{N} \log p_{\theta}(x^{(i)})
$$

If the model can compute $p_{\theta}(x)$ and sample from it, then new data can be generated simply by:

$$
x_{\text{new}} \sim p_{\theta}(x)
$$

Many generative models introduce latent variables $z$ to capture hidden structure.  
The model defines a joint distribution:

$$
p_{\theta}(x,z) = p_{\theta}(z) \, p_{\theta}(x \mid z)
$$

Generation proceeds by sampling:

$$
z \sim p_{\theta}(z), \qquad x \sim p_{\theta}(x \mid z)
$$

Different families of generative models implement this process in different ways:

- **Explicit density models**, which directly compute $p_{\theta}(x)$  
- **Latent-variable models**, which use hidden variables to explain variation  
- **Adversarial models**, which train a generator to fool a discriminator  
- **Iterative refinement models**, which gradually transform noise into data  

Generative models enable synthetic data generation, simulation, data augmentation, anomaly detection, and learning rich representations of complex distributions.
