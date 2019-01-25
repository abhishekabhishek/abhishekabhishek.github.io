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

The perceptron algorithm serves as a very good foundation for understanding the workings of more complex neural network models such as Multi-layer Neural Networks, Recurrent Neural Networks and Convolutional Neural Networks. This is since the perceptron algorithm is a specialization of the artificial neuron, it uses the heaviside function ()

### What is a Perceptron ?<a id='what_is_a_neural_network'></a>

A perceptron is the simplest model of a neural network and is a binary classifier. It consists of :
- an input layer with **n** input nodes
- an output node with an output of either 1 or -1
- the weighted connections between the input nodes and the output node
- an activation threshold

The perceptron algorithm was invented by American Psychologist [Frank Rosenblatt](https://en.wikipedia.org/wiki/Frank_Rosenblatt) in 1957. The diagram below shows the architecture of the original perceptron algorithm. 


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

where <img src="https://latex.codecogs.com/gif.latex?W.X" title="W.X" /> denotes the dot-product of the input vector and the weight vector, <img src="https://latex.codecogs.com/gif.latex?\sum_{i=1}^n&space;w_ix_i" title="\sum_{i=1}^n w_ix_i" />. Note that different resources present different values for the output in the second case of the equation above. This depends on the choice and the range of the activation function. The choice of the activation function is closely related to the classification task at hand and range of target labels.

Also note that <img src="https://latex.codecogs.com/gif.latex?w_0" title="w_0" /> acts as a threshold for the perceptron to be fired if we consider the output value as an artificial neuron firing. This is an important concept which is carried onto multi-layer neural networks used for classification and pattern recognition.

#### Learning Problem

The learning problem for a classical perceptron can then be reduced to finding a real-valued weight vector in the candidate hypothesis space such that the perceptron accurately classifies the input samples. The candidate hypothesis space for the set of all real-valued weight vectors is given by :

<img src="https://latex.codecogs.com/gif.latex?\textbf{H}&space;=&space;{\{W&space;|W\in&space;R^{(n&plus;1)}\}}" title="\textbf{H} = {\{W |W\in R^{(n+1)}\}}" />

#### Training Algorithm

- Perceptron Training Algorithm

    To be updated

- Gradient Descent Algorithm

    To be updated

#### Complexity Analysis

We can use the forward procedure and training rules to obtain a complexity for the perceptron algorithm. In this section, we will go through the process to obtain the computational complexity for the algorithm.

#### Limitations

The classical perceptron algorithm suffers from many limitations, most notably the inability to perform non-linear classification tasks. We will discuss the limitations of the classical perceptron algorithm in detail here.

### Quantum Perceptron<a id='quantum_perceptron'></a>

In the previous years, several models have been presented forward for the algorithm and the implementation of the quantum version of the perceptron. We will discuss a few of them in-detail and learn about the underlying principles of quantum algorithms which can be used to improve the classical perceptron algorithm.

- Encoding the Input and the Weight Vector in Quantum States
<br/><br/>This is one of the most important step in the quantum algorithm for the perceptron since the encoding would determine which general techniques from quantum computation such as entanglement and interference can be used to improve the classical algorithm.
<br/><br/>For simplicity, consider the weight vector W to also include W_0 ( threshold ) and the input vector X to include X_0 = 1 i.e.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img src="https://latex.codecogs.com/gif.latex?W&space;=&space;\begin{bmatrix}&space;w_0&space;\\w_1\\&space;w_2\\&space;.\\&space;.\\&space;w_n\\&space;\end{bmatrix}" title="W = \begin{bmatrix} w_0 \\w_1\\ w_2\\ .\\ .\\ w_n\\ \end{bmatrix}" />
, <img src="https://latex.codecogs.com/gif.latex?X&space;=&space;\begin{bmatrix}&space;1\\x_1\\&space;x_2\\&space;.\\&space;.\\&space;x_n\\&space;\end{bmatrix}" title="X = \begin{bmatrix} 1\\x_1\\ x_2\\ .\\ .\\ x_n\\ \end{bmatrix}" />
<br/>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;For a **n**-dimensional input feature vector, we would need at least **m** qubits to encode the vector in a quantum state,

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://latex.codecogs.com/gif.latex?m&space;=&space;\lceil&space;log_2(n&plus;1)\rceil" title="m = \lceil log_2(n+1)\rceil" />

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; A simple approach to constructing the input and weight states is discussed in [Tacchino2018]. The encoding problem in the &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; circuit model of the quantum computation such as the one used for the [IBM Q](https://quantumexperience.ng.bluemix.net/qx/experience) can be described as finding the gate sequence &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; to construct unitary transformations, <img src="https://latex.codecogs.com/gif.latex?U_i" title="U_i" /> and <img src="https://latex.codecogs.com/gif.latex?U_w" title="U_w" /> such that :

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <img src="https://latex.codecogs.com/gif.latex?U_i|\psi_0\rangle&space;=&space;|\psi_i\rangle&space;=&space;\frac{1}{\sqrt{2^m}-1}\sum_{i=0}^{2^m-1}X_i|i\rangle" title="U_i|\psi_0\rangle = |\psi_i\rangle = \frac{1}{\sqrt{2^m}-1}\sum_{i=0}^{2^m-1}X_i|i\rangle" /> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <img src="https://latex.codecogs.com/gif.latex?U_w|\psi_1\rangle&space;=&space;|\psi_w\rangle&space;=&space;\frac{1}{\sqrt{2^m-1}}\sum_{i=0}^{2^m-1}W_i|i\rangle" title="U_w|\psi_1\rangle = |\psi_w\rangle = \frac{1}{\sqrt{2^m-1}}\sum_{i=0}^{2m-1}W_i|i\rangle" />

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; The transformation <img src="https://latex.codecogs.com/gif.latex?U_i" title="U_i" />  corresponding to the input vector <img src="https://latex.codecogs.com/gif.latex?X" title="X" /> can be constructed as following :

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Consider the initial state,<br/> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <img src="https://latex.codecogs.com/gif.latex?|\psi_0\rangle&space;=&space;|0\rangle^{\otimes&space;n}&space;=&space;\begin{bmatrix}&space;1\\&space;0\\&space;.\\&space;.\\&space;.\\&space;0\\&space;\end{bmatrix}" title="|\psi_0\rangle = |0\rangle^{\otimes n} = \begin{bmatrix} 1\\ 0\\ .\\ .\\ .\\ 0\\ \end{bmatrix}" />

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; The input vector can then be used as the first column of the transformation matrix for <img src="https://latex.codecogs.com/gif.latex?U_i" title="U_i" /> with all the other elements set to 0 : 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <img src="https://latex.codecogs.com/gif.latex?U_i&space;=&space;\begin{bmatrix}&space;X_0&space;&&space;.&space;&&space;.&space;&&space;.&space;&&space;.&space;\\&space;X_1&space;&&space;.&space;&&space;.&space;&&space;.&space;&&space;.&space;\\&space;X_2&space;&&space;.&space;&&space;.&space;&&space;.&&space;.&space;\\&space;.&space;&&space;.&space;&&space;.&space;&&space;.&&space;.&space;\\&space;.&space;&&space;.&space;&&space;.&&space;.&space;&&space;.&space;\end{bmatrix}" title="U_i = \begin{bmatrix} X_0 & . & . & . & . \\ X_1 & . & . & . & . \\ X_2 & . & . & .& . \\ . & . & . & .& . \\ . & . & .& . & . \end{bmatrix}" />

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Another way of constructing the transformation matrix would be by first apply the Hadamard gate, <img src="https://latex.codecogs.com/gif.latex?H^{\otimes&space;n}" title="H^{\otimes n}" /> to the initial state &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <img src="https://latex.codecogs.com/gif.latex?|\psi_0\rangle" title="|\psi_0\rangle" /> and then using the input vector <img src="https://latex.codecogs.com/gif.latex?X" title="X" /> as the diagonal for the transformation matrix for <img src="https://latex.codecogs.com/gif.latex?U_i" title="U_i" /> :

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <img src="https://latex.codecogs.com/gif.latex?U_i&space;=&space;\begin{bmatrix}&space;X_0&space;&&space;.&space;&&space;.&space;&&space;.&space;&&space;.&space;\\&space;.&space;&&space;X_1&space;&&space;.&space;&&space;.&space;&&space;.&space;\\&space;.&space;&&space;.&space;&&space;X_2&space;&&space;.&&space;.&space;\\&space;.&space;&&space;.&space;&&space;.&space;&&space;.&&space;.&space;\\&space;.&space;&&space;.&space;&&space;.&&space;.&space;&&space;.&space;\end{bmatrix}" title="U_i = \begin{bmatrix} X_0 & . & . & . & . \\ . & X_1 & . & . & . \\ . & . & X_2 & .& . \\ . & . & . & .& . \\ . & . & .& . & . \end{bmatrix}" />

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; The construction of the unitary transformation corresponding to the weight vector is not as trivial.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; To be updated.
- Quantum Perceptron using Sign Flip Blocks
<br/> 

- Quantum Perceptron using Hypergraph States Generation Subroutine (HPGS)
<br/> 





### Implementations and Examples<a id='implementations_and_examples'></a>

In this section, we will discuss the implementations of both the classical perceptron with several learning rules and the quantum perceptron using the methods discussed above.

To be updated

### Acknowledgements<a id='acknowledgements'></a>

To be updated

### References<a id='references'></a>

1. Online Articles
- Perceptron - Wikipedia, https://en.wikipedia.org/wiki/Perceptron
2. Textbooks
- M. Minsky, S. Papert, "Perceptrons: an introduction to computational geometry", 1969.
- C. Issac and Nielsen M., "Quantum Computation and Quantum Information, 10th edition", 2010.
3. Research Articles
- [Tacchino2018] D. G. D. B. Francesco Tacchino, Chiara Macchiavello, “An artificial neuron implemented on an actual quantum processor” 2018. arXiV : https://arxiv.org/abs/1811.02266
- [Farhi2018] E. Farhi, H. Neven, "Classification with Quantum Neural Networks on Near Term Processors" 2018. <br/>arXiV : https://arxiv.org/abs/1802.06002


