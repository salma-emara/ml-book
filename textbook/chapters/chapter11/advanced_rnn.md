# 10.4. Advanced Sequence Models

**<span style="font-size:1.5em;">Advanced Sequence Models</span>**

Advanced sequence models extend basic RNNs by improving memory handling, stabilizing long-term learning, and enabling flexible transformations between sequences of different lengths. Gated units, encoder–decoder models, and Transformers address limitations of simple recurrent networks.

**GRU and LSTM Recap**

GRUs simplify gating while LSTMs introduce a dedicated cell state for long-term memory.

GRU hidden state update:

$$
h[t] = (1 - z[t]) \odot h[t-1] + z[t] \odot \tilde{h}[t]
$$

LSTM cell state:

$$
c[t] = f[t] \odot c[t-1] + i[t] \odot \tilde{c}[t]
$$

LSTM hidden state:

$$
h[t] = o[t] \odot \tanh(c[t])
$$

These gated updates reduce vanishing gradients and help maintain useful information across long sequences.

---

**<span style="font-size:1.5em;">Encoder–Decoder Models</span>**

Encoder–decoder architectures handle tasks where input and output sequences differ in length or structure.

Given an input sequence $x = (x[1], \dots, x[T_x])$, the encoder produces hidden states:

$$
h_e[t] = f_e(W_{ex} x[t] + W_{eh} h_e[t-1])
$$

The final encoder hidden state serves as a context vector:

$$
c = h_e[T_x]
$$

The decoder generates an output sequence $y = (y[1], \dots, y[T_y])$.  
At each decoding step:

$$
h_d[t] = f_d(W_{dy} y[t-1] + W_{dh} h_d[t-1] + W_{dc} c)
$$

Decoder output:

$$
y[t] = g(W_o h_d[t])
$$

Training maximizes:

$$
\prod_{t=1}^{T_y} p(y[t] \mid y[1:t-1], c)
$$

This architecture separates “understanding” the input (encoding) from “generating” the output (decoding), supporting tasks such as translation and sequence transformation.

---

**<span style="font-size:1.5em;">Transformers</span>**

Transformers remove recurrence and use self-attention to directly model dependencies between all positions in a sequence.

Scaled dot-product attention:

$$
\text{Attention}(Q, K, V) =
\text{softmax}\left(\frac{QK^\top}{\sqrt{d_k}}\right) V
$$

Query, key, and value matrices:

$$
Q = X W_Q, \qquad K = X W_K, \qquad V = X W_V
$$

Multi-head attention:

$$
\text{MHA}(X) = \text{Concat}(\text{head}_1, \dots, \text{head}_H) W_O
$$

with each head:

$$
\text{head}_i = \text{Attention}(X W_Q^{(i)}, X W_K^{(i)}, X W_V^{(i)})
$$

**Encoder layer**

Multi-head attention followed by a feedforward network:

$$
Z = \text{MHA}(X) + X
$$

$$
H = \text{FFN}(Z) + Z
$$

**Decoder layer**

Masked self-attention, cross-attention over encoder output, and a feedforward network:

Masked self-attention:

$$
Z_1 = \text{MHA}_{\text{masked}}(Y) + Y
$$

Cross-attention (decoder attends to encoder output):

$$
Z_2 = \text{MHA}(Z_1, H, H) + Z_1
$$

Final decoder state:

$$
S = \text{FFN}(Z_2) + Z_2
$$

Output probability for each step:

$$
p(y[t] \mid y[1:t-1], X) = \text{softmax}(W_o S[t])
$$

Transformers efficiently capture long-range dependencies, enable full parallelism, and form the basis of modern large-scale sequence models.
