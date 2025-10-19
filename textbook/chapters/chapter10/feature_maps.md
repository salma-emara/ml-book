# Feature Maps and Stacked Filters

In a convolutional layer, each **filter** learns to detect a specific pattern (e.g., edge, curve, texture).  
When a filter is applied across the input, the output is a **feature map** — a 2D map showing where and how strongly that pattern appears.

---

**<span style="font-size:1.5em;">From Filter to Feature Map</span>**

Each filter $W^{[l]}$ in layer $l$ produces a feature map $Z^{[l]}$:

$$
Z^{[l]} = X^{[l-1]} * W^{[l]} + b^{[l]}
$$

- $X^{[l-1]}$ is the input to the layer  
- $*$ denotes convolution  
- $b^{[l]}$ is the bias term added after convolution

The result is a new activation map that highlights specific local patterns.

---

**<span style="font-size:1.5em;">Stacking Multiple Filters</span>**

Instead of using just one filter, CNNs use **multiple filters in parallel** to capture different features.  
If a convolutional layer has $M$ filters, it outputs $M$ feature maps:

- Low-level filters detect simple patterns (e.g., edges, colors, gradients)  
- Deeper filters learn higher-level patterns (e.g., shapes, objects)

The result is a 3D volume of shape $(H', W', M)$ where each channel corresponds to a different feature map.

---

**<span style="font-size:1.5em;">Channel Dimension Grows</span>**

As we go deeper in the network:

- Spatial dimensions $(H, W)$ tend to shrink due to pooling or stride  
- The **number of channels** (depth) increases — capturing more complex, abstract features

This shift from wide to deep helps compress spatial information and build hierarchical understanding.

---

**<span style="font-size:1.5em;">Visual Interpretation</span>**

Feature maps help us visualize:

- Where specific patterns appear  
- Which filters activate most strongly for certain inputs  
- How deep layers learn to represent meaningful structure

Feature maps can be visualized during debugging or for model interpretability.

