Hinton’s Forward-Forward (FF) algorithm offers a
biologically plausible alternative to backpropagation by replacing
the global backward pass with layer-local goodness objectives.
However, the original FF architecture suffers from two fundamental limitations: class labels must be embedded into the
input via one-hot overlay, corrupting the data representation,
and the neuron model is restricted to ReLU activations that
lack biological realism. We propose ModularFF, a modular
architecture that eliminates label overlay entirely by training
K independent specialist networks, one per class, each solving a
binary goodness discrimination task. We identify and resolve a
critical scaling issue where sum-based goodness causes sigmoid
saturation on layers exceeding approximately 50 neurons, and
introduce a hybrid layer–neuron loss for principled interpolation
between layer-level and per-neuron goodness objectives.
Beyond the architectural contribution, we present the first
systematic study of biologically plausible neuron models for
forward-forward learning. We formulate activation-aware goodness functions and learning rules for four neuron configurations
spanning a biological plausibility spectrum: ReLU and GELU
with energy-based goodness, Tanh with directional goodness, and
a fully gradient-free Perceptron using classical error-correction.
Each configuration is paired with a tailored goodness measure
and optionally learnable thresholds that adapt to each activation’s
operating regime.
Through comprehensive experiments on five datasets, we
demonstrate that: (1) ModularFF with GELU matches or exceeds
backpropagation, achieving 88.2% on FashionMNIST versus
87.6% for backpropagation; (2) layer-level goodness (α = 0.0)
produces superior representations for gradient-based activations;
(3) the gradient-free Perceptron within ModularFF achieves
91.4% on MNIST and 83.6% on FashionMNIST while Classic FF
collapses to near-chance levels, yielding ModularFF advantages of
+51 to +73 percentage points — the largest reported performance
gaps in the FF literature; (4) the Perceptron exhibits a unique alpha inversion: per-neuron goodness (α = 1.0) outperforms layerlevel on high-dimensional data, reversing the pattern observed
with all gradient-based activations; and (5) Tanh is fundamentally incompatible with per-neuron goodness, with directional
goodness inversion causing catastrophic failure at α = 1.0.
