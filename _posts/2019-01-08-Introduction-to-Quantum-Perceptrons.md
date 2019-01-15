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

#### [References](#references)
----

### Introduction<a id='introduction'></a>

This post is about Quantum Perceptrons. In particular, we will discuss several recent models which have presented by researchers around the world for implementing perceptrons on quantum information processing devices. We will start with a very brief history of the classical perceptron and the perceptron learning algorithm. Then, we will consider the mathematical foundation of the classical perceptron and the perceptron learning algorithm. From there, we will switch to the quantum variants of the perceptron and discuss the models and learning algorithms presented in the recent years.

### What is a Perceptron ?<a id='what_is_a_neural_network'></a>

A perceptron is the simplest model of a neural network which is a binary classifier. It consists of an input layer with n inputs, an output neuron, the weighted connections between the inputs and the output neuron and a weighted bias connection to the output neuron. The perceptron algorithm was invented by American Psychologist [Frank Rosenbaltt](https://en.wikipedia.org/wiki/Frank_Rosenblatt) in 1957. The diagram below shows the architecture of the original perceptron.


![][single_layer_perceptron_link]

[single_layer_perceptron_link]:https://raw.githubusercontent.com/abhishekabhishek/abhishekabhishek.github.io/master/_posts/post_images/2019-01-08/single_layer_perceptron.PNG "Single Layer Perceptron"

### Classical Perceptron<a id='classical_perceptron'></a>

In the following, we will discuss the mathematics behind the classical perceptron and the perceptron learning algorithm.

The input is a real-valued n-dimensional vector, 

<img src="https://latex.codecogs.com/gif.latex?X&space;=&space;\begin{bmatrix}&space;x_1\\&space;x_2\\&space;.\\&space;.\\&space;x_n\\&space;\end{bmatrix}" title="X = \begin{bmatrix} x_1\\ x_2\\ .\\ .\\ x_n\\ \end{bmatrix}" />

The weights of the connection between the inputs and the output are given by a real-valued vectors with the same dimensions as the input vector.

<img src="https://latex.codecogs.com/gif.latex?W&space;=&space;\begin{bmatrix}&space;w_1\\&space;w_2\\&space;.\\&space;.\\&space;w_n\\&space;\end{bmatrix}" title="W = \begin{bmatrix} w_1\\ w_2\\ .\\ .\\ w_n\\ \end{bmatrix}" />


### Quantum Perceptron<a id='quantum_perceptron'></a>

To be updated

### Acknowledgements<a id='acknowledgements'></a>

### References<a id='references'></a>


