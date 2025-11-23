# Sampling Methods

**<span style="font-size:1.5em;">Sampling Methods</span>**

Sampling is central to generative modeling. After a model approximates the data distribution, new samples are produced by drawing from the learned distribution. Different generative frameworks use different sampling strategies depending on how the model represents $p_{\theta}(x)$.

---

**Direct Sampling from Model Distribution**

If the model provides an explicit density $p_{\theta}(x)$ and sampling is easy, generation is straightforward:

$$
x_{\text{new}} \sim p_{\theta}(x)
$$

For models like Gaussian Mixture Models, sampling uses the mixture structure: choose a component and then draw from its Gaussian.

---

**Sampling from Latent Variable Models**

Latent variable models define:

$$
p_{\theta}(x,z) = p_{\theta}(z)\, p_{\theta}(x \mid z)
$$

Sampling proceeds by:

$$
z \sim p_{\theta}(z)
$$

$$
x_{\text{new}} \sim p_{\theta}(x \mid z)
$$

This applies to VAEs and many other latent-variable generative models.

---

**Generator-Based Sampling**

In models that learn a deterministic mapping from noise to data, sampling reduces to transforming noise:

$$
x_{\text{new}} = f_{\theta}(z), \qquad z \sim p(z)
$$

This is the core idea behind GANs and other direct generative samplers shown in the PDF.

---

**Monte-Carlo and MCMC Techniques**

When the distribution $p_{\theta}(x)$ is known but sampling is difficult, numerical methods like Monte-Carlo or Gibbs sampling can be used. These methods approximate samples by iteratively refining draws, but they can be slow or high-variance.

---

**Diffusion-Based Sampling**

Diffusion models generate samples through an iterative denoising process.  
A noisy sample is gradually refined toward a clean data sample by running a learned reverse diffusion:

$$
x_{t-1} = g_{\theta}(x_t, t)
$$

Starting from pure noise $x_T$, the model repeatedly applies the reverse process until it produces a final sample $x_0$.

---

Sampling methods vary in complexity, but all aim to produce synthetic data that follows the structure of the real data distribution learned by the model.
