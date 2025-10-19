# Parameter Sharing in Convolutional Layers

Convolutional layers apply the same filter (weights) across different input locations.  
This concept is called **parameter sharing**.

---

**<span style="font-size:1.5em;">What It Means</span>**

The same set of weights (a filter) is used across the entire input.  
For example, a $3 \times 3$ edge detector is applied at every location to detect edges.

<div style="text-align: center; background-color:white; padding:10px;">
  <img src="../../_static/cnn3.png" alt="CNN filter" width="500"/>
</div>
---

**<span style="font-size:1.5em;">Why It Matters</span>**

- Reduces number of parameters significantly  
- Allows detection of the same pattern anywhere in the input  
- Supports **translation invariance**

