# malaria-classification
# DenseNet for Malaria Life-Cycle Stage Classification

This repository demonstrates how to train and evaluate a DenseNet121 model to recognize malaria life-cycle stages in thin blood smear images.

## DenseNet Architecture

DenseNet (Densely Connected Convolutional Network) introduces direct connections between any two layers with the same feature-map size. Each layer receives the feature maps of all preceding layers as inputs, and its own output is passed to all subsequent layers. This design encourages feature reuse and improves gradient flow during training.

The core components of DenseNet are:

- **Dense Blocks** – groups of convolutional layers where each layer's output is concatenated to the inputs of subsequent layers.
- **Transition Layers** – 1x1 convolutions followed by pooling layers used to change the feature-map size between dense blocks.
- **Growth Rate** – controls how many filters each layer adds to the concatenated output.

Using DenseNet121 as the backbone provides a good balance of depth and parameter efficiency while benefiting from ImageNet pretraining.

## Strengths

- **Efficient gradient propagation** thanks to dense connections, which can ease training of deep networks.
- **Parameter efficiency** – fewer parameters compared to many other deep architectures with similar accuracy.
- **Feature reuse** across dense blocks often leads to improved generalization.

## Weaknesses

- **Higher memory consumption** during training because feature maps from all preceding layers are concatenated and stored.
- **Longer training times** compared to simpler architectures if not carefully optimized.
- **Complexity** of dense connectivity can be harder to modify when adapting the architecture.