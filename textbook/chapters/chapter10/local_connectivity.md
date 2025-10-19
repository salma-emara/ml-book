# Local Connectivity and Sparse Weights

Convolutional layers are based on the principle of **local connectivity**.  
Instead of connecting every input to every neuron, each neuron only connects to a **local region**.

---

**<span style="font-size:1.5em;">Receptive Field</span>**

The **receptive field** is the subset of input that a neuron processes.  
For example, with a $5 \times 5$ kernel, each output neuron sees only $25$ spatial locations (per channel).

---

**<span style="font-size:1.5em;">Sparse Connections</span>**

Unlike fully connected layers, convolutional layers learn fewer parameters:

- Only the filter weights are learned  
- Each output unit is connected to a small patch

This sparsity reduces overfitting and improves efficiency.


