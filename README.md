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

/////////////////////////////////////////////////////////////////
The Forward-Forward (FF) algorithm offers a biologically plausible alternative to back
propagation, but restricts neuron models to ReLU and requires class labels to be embed
ded directly into the input. This paper introduces ModularFF, which eliminates label
embedding by training K independent specialist networks , one per class, and presents
the first systematic study of alternative neuron models for FF learning. Most strikingly,
combining ModularFF with a gradient-free Perceptron achieves 91.4% on MNIST and
83.6% on FashionMNIST with no gradient computation at any stage, while the same
Perceptron inside standard FF collapses to near-chance. A novel Attentive Goodness
mechanism is further introduced, replacing uniform neuron weighting in the goodness
computation with a learned attention vector that consistently rescues a previously un
reported catastrophic failure mode in Tanh-based FF networks. Within the MLP-based
FF literature, ModularFF with ReLU achieves 88.3% on FashionMNIST, surpassing all
prior MLP-only methods including SymBa and the best reported goodness function
benchmark by 5–6 percentage points.
Keywords: Forward-Forward algorithm; biologically plausible learning; modular neural
networks; gradient-free learning; attentive goodness; local learning rules.
