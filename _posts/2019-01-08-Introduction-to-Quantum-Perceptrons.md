---
layout: post
title: Introduction to Quantum Perceptrons
---

## Introduction to Quantum Perceptrons

----
### Table of contents

#### [Introduction](#introduction)

#### [What is a Perceptron](#what_is_a_neural_network)

#### [Classical Perceptron](#classical_perceptron)

#### [Quantum Perceptron](#quantum_perceptron)

#### [Acknowledgements](#acknowledgements)

#### [Implementations and Examples](#implementations_and_examples)

#### [References](#references)
----

### Introduction<a id='introduction'></a>

This post is about Quantum Perceptrons. In particular, we will discuss several recent models which have presented by researchers around the world for implementing perceptrons on quantum information processing devices. We will start with a very brief history of the classical perceptron and the perceptron learning algorithm. Then, we will consider the mathematical foundation of the classical perceptron and the perceptron learning algorithm. From there, we will switch to the quantum variants of the perceptron and discuss the models and learning algorithms presented in the recent years.

The perceptron algorithm serves as a very good foundation for understanding the workings of more complex neural network models such as Multi-layer Perceptrons, Recurrent Neural Networks and Convolutional Neural Networks.

### What is a Perceptron ?<a id='what_is_a_neural_network'></a>

A perceptron is the simplest model of a neural network and is a binary classifier. It consists of :
- an input layer with **n** input nodes
- an output node with an output of either 1 or -1
- the weighted connections between the input nodes and the output node
- an activation threshold

The perceptron algorithm was invented by American Psychologist [Frank Rosenbaltt](https://en.wikipedia.org/wiki/Frank_Rosenblatt) in 1957. The diagram below shows the architecture of the original perceptron algorithm. 


![][single_layer_perceptron_link]

[single_layer_perceptron_link]:https://raw.githubusercontent.com/abhishekabhishek/abhishekabhishek.github.io/master/_posts/post_images/2019-01-08/single_layer_perceptron.PNG "Single Layer Perceptron"

### Classical Perceptron<a id='classical_perceptron'></a>

#### Equations

In the following, we will discuss the mathematics behind the classical perceptron and the perceptron learning algorithm.

The input is a real-valued n-dimensional vector, 

<img src="https://latex.codecogs.com/gif.latex?X&space;=&space;\begin{bmatrix}&space;x_1\\&space;x_2\\&space;.\\&space;.\\&space;x_n\\&space;\end{bmatrix}" title="X = \begin{bmatrix} x_1\\ x_2\\ .\\ .\\ x_n\\ \end{bmatrix}" />

The weights of the connection between the inputs and the output are given by a real-valued vectors with the same dimensions as the input vector.

<img src="https://latex.codecogs.com/gif.latex?W&space;=&space;\begin{bmatrix}&space;w_1\\&space;w_2\\&space;.\\&space;.\\&space;w_n\\&space;\end{bmatrix}" title="W = \begin{bmatrix} w_1\\ w_2\\ .\\ .\\ w_n\\ \end{bmatrix}" />

The output of the perceptron given an input vector X and weight vector W is given by :

<img src="https://latex.codecogs.com/gif.latex?O(X)&space;=&space;\begin{cases}&space;1,&space;W.X&space;&plus;&space;w_0&space;>&space;0\\&space;-1\:otherwise&space;\end{cases}" title="O(X) = \begin{cases} 1, W.X + w_0 > 0\\ -1\:otherwise \end{cases}" />

where <img src="https://latex.codecogs.com/gif.latex?W.X" title="W.X" /> denotes the dot-product of the input vector and the weight vector, <img src="https://latex.codecogs.com/gif.latex?\sum_{i=1}^n&space;w_ix_i" title="\sum_{i=1}^n w_ix_i" />.

<img src="https://latex.codecogs.com/gif.latex?w_0" title="w_0" /> therefore acts as a threshold for the perceptron to be fired if we consider the output value as an artificial neuron firing.

#### Learning Problem

The learning problem for a classical perceptron can then be reduced to finding a real-valued weight vector in the candidate hypothesis space such that the perceptron accurately classifies the input samples. The candidate hypothesis space for the set of all real-valued weight vectors is given by :

<img src="https://latex.codecogs.com/gif.latex?\textbf{H}&space;=&space;{\{W&space;|W\in&space;R^{(n&plus;1)}\}}" title="\textbf{H} = {\{W |W\in R^{(n+1)}\}}" />

#### Training Algorithm

- Perceptron Training Algorithm

    To be updated

- Gradient Descent Algorithm

    To be updated


### Quantum Perceptron<a id='quantum_perceptron'></a>

In the previous years, several models have been presented forward for the algorithm and the implementation of the quantum version of the perceptron. We will discuss a few of them in-detail and learn about the underlying principles of quantum algorithms which can be used to improve the classical perceptron algorithm.

- Quantum Perceptron using Hypergraph States Generation Subroutine (HPGS)



### Implementations and Examples<a id='implementations_and_examples'></a>

To be updated

### Acknowledgements<a id='acknowledgements'></a>

To be updated

### References<a id='references'></a>

1. Online Articles
- Perceptron - Wikipedia, https://en.wikipedia.org/wiki/Perceptron
2. Books
- Perceptrons: an introduction to computational geometry, Authors : Marvin Minsky and Seymour Papert
3. Research Articles
- D. G. D. B. Francesco Tacchino, Chiara Macchiavello, “An artificial neuron implemented on an actual quantum processor” 2018. arXiV : https://arxiv.org/abs/1811.02266
- E. Farhi, H. Neven, "Classification with Quantum Neural Networks on Near Term Processors" 2018. <br/>arXiV : https://arxiv.org/abs/1802.06002


