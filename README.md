Modular Forward-Forward Learning: Biologically Plausible Neuron
Models, Attention-Weighted Goodness, and Gradient-Free Perceptron
Training

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
