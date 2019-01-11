---
layout: post
title: Industrial Project Proposal
---
## COMP 4560 – Undergraduate Industrial Project Proposal

### Title : Quantum Perceptron on the IBM Q
### Abhishek ., 7803917

---
abstract: |
    In the recent years, neural network models have been successfully
    applied to various machine learning problems such as image recognition
    and natural language understanding. However, even the current best
    models suffer from limitations in terms of efficiency such as high
    training data volume requirements and long training times. Quantum
    information processing techniques have been shown to provide speedup to
    many classical machine learning algorithms and many different models of
    a quantum neural network have been proposed. However, due to the
    realizations of actual quantum computers currently being under
    development, the implementations of these models on quantum processors
    is an area that is yet to be fully explored. In this industrial project,
    we will first explore the proposed models for the quantum perceptron and
    then attempt to implement these models on one of the first quantum
    processing devices available today, the IBM Q. Through this development
    and testing process, we wish to build an intuitive understanding of the
    implementation methods of more complex models such as the quantum neural
    network on near-term quantum information processing devices.
author:
- |
    Abhishek .\
    Department of Computer Science, University of Manitoba\
    Email : abhishek\@myumanitoba.ca
- |
    Supervisor : Dr. Parimala Thulasiraman\
    Department of Computer Science, University of Manitoba\
    Email : thulasir\@cs.umanitoba.ca
bibliography:
- 'references.bib'
date: 'January 05, 2018'
title: |
    COMP 4560 - Undergraduate Industrial Project Registration Process\
    Quantum Perceptrons on the IBM Q\
---

Introduction
============

Quantum computing is use of quantum information processing devices in
order to perform sufficiently complex computations. Machine Learning
refers to the field of Computer Science in which data-driven and
statistical-based learning algorithms are used to improve the
performance of a model for a given artificial intelligence task such as
face recognition and natural language understanding.

Artificial Neural Networks (ANNs) are one of the primary models in the
connectionist approach to machine learning. The earliest known model of
an artificial neuron was introduced in [@McCulloch1943] which is now
known as the McCulloch-Pitts Neuron. This lead to the development of the
first model of an ANN Since then, a plethora of neural network models
such as Long-Short Term Memory Recurrent Neural Networks (LSTM-RNNs) and
Convulational Neural Networks (CNNs) which are made up of different
neural units have been successfully developed and applied in many
machine learning problems.

The operational parallelism that is inherent in the architecture of ANNs
is one of the main reasons of widespread interest in the research and
development of these models. In a similar way, Quantum parallelism is an
inherent property of quantum information processing devices in the
quantum model of computation. The ability and ingenuity to exploit this
massive parallelism forms the basis of many well-known quantum
algorithms such as Grover's Quantum Search [@Grover1996] and the Quantum
Fourier Transform [@Shor1999].

One of the earliest work on Quantum Neural Networks is given in
[@Kak1995] in which the author discusses the parallels between the
connectionist approach to machine learning, biological information
processing and quantum computing. Since then, many different proposals
have been developed for models of quantum neural networks. However, in
this industrial project, we will limit the scope of the research and
implementation to the fundamental units of a neural network i.e. a
perceptron.

Classical Perceptron
--------------------

The first model of a classical perceptron was published by Frank
Rosenblatt in 1958.[@Rosenblatt1958]. The original algorithm was a
binary classifier which used a threshold function to compute the output
value of the perceptron.

$$f(x) = 
        \begin{dcases}
            1 & \textbf{w}.\textbf{x} + \textbf{b} > 0 \\
            0 & otherwise
        \end{dcases}$$

where $\textbf{w}$ is the vector of real-values weights for the
connection between the input nodes and the output node, $\textbf{x}$ is
the vector of the input at the input nodes at the single-layer
perceptron and $\textbf{b}$ is the bias at the output node.

The output of the single-layer perceptron indicated whether the input
described by the input vector belongs to a binary class or the other.

The single-layer perceptron had the shortcoming that it cannot be used
to solve non-linear binary classification problems and hence a
multi-layer perceptron i.e. a feed-forward neural network was developed
which has the capability of solving non-linear classification problem.

Quantum Perceptron
------------------

Many different models and implementations have been proposed for the
quantum perceptron. In the circuit model of quantum computation, the
primary challenge is finding the appropriate sequences of
transformations and operators to implement non-linear activation
functions which form the basis of classical perceptrons. This is also
challenging due to the fact that transformations and evolution operators
in quantum mechanics are in general, linear therefore non-linear
operations such as measurement may have to be potentially used in order
to implement the non-linear activation functions.

The term 'Quantum Perceptron' refers to an implementation of the
perceptron which uses techniques from quantum information processing in
order to achieve speedup in learning or complexity over classical
perceptron algorithms.

Background Preparation
======================

As a preparation for this project, an Undergraduate Honours Project has
been completed in the previous term of Fall 2018 with the thesis
\"Introduction to Quantum Computing and the Single Pair Shortest Path
Problem\". In the honours project, we discussed how fundamental concepts
and algorithms from Quantum Computing have been applied to graph
optimization problems in order to achieve a quantum speedup i.e. a
speedup in terms of the query complexity over the classical graph
optimization algorithms.

In addition to the Undergraduate Honours Project, the following academic
courses also allow for background preparation to complete a project in
this subject area,

1.  **PHYS 3380 : Quantum Physics 2**\
    Developed the abstract linear algebraic formalism for quantum
    mechanical states and operators with classical measurements, found
    solutions to 1-dimensional and 3-dimensional Schrodinger's equations
    for the hydrogen atom using mathematical and linear algebraic tools,
    explored degeneracy in quantum states using quantum mechanical
    operators.

2.  **PHYS 2380 : Quantum Physics 1**\
    Learned mathematical methods to derive solutions to differential
    equations associated with quantum systems. Studied proofs related to
    observations from quantum systems with no classical counterparts
    such as quantum entanglement and superposition.

3.  **COMP 2080 : Analysis of Algorithms**\
    Studied asymptotic algorithm analysis using methods for analyzing
    the time and space requirements of the algorithms, explored
    different models of computation and algorithm design using different
    strategies ( e.g. greedy, divide-and-conquer )

Related works
=============

In this this industrial project, we first would like to reproduce
implementations from the recent work by Tacchino et al.in
[@Tacchino2018] in which the authors first

Problem statement
=================

The goal of the industrial project is to explore how can we implement
the quantum perceptron on near-term quantum information devices that use
the circuit model of quantum computation.

Methodology
===========

The industrial project will be divided into a series of smaller
iterative step-projects each of which would have a defined timeline and
associated sub-tasks. The table below shows the overview of the
step-projects and the expected timeline. The dates may be adjusted in
order to allow for a successful completion of the project.

[\[table:1\]]{#table:1 label="table:1"}

  ----------------- ---------------------------------------------------- ---------------------------------------
  Step project \#   Step project overview                                Expected dates
  \[0.5ex\] 1       Thorough research and evaluation of the              January 11, 2019 - January 31, 2019
                    proposed models of the quantum perceptron.           
                    Determination of the best model to be                
                    implemented on the quantum processors.               
  2                 Setup of the development and execution               February 01, 2019 - February 28, 2019
                    environment for the quantum simulators and           
                    quantum processors. Learning of essential            
                    programming fundamentals to successfully             
                    implement the determined model on the                
                    IBMQ5 and IBMQ20 machine.                            
  3                 Implementation of the models on the quantum          March 01, 2019 - March 31, 2019
                    simulators and processors available for execution.   
                    A theoretical analysis to determine the gate and     
                    query complexity of the implemented models.          
  4                 Retrospective and compilation of the results from    April 01, 2019 - April 26, 2019
                    the implementations and the executions of the        
                    Quantum Perceptron models.                           
  ----------------- ---------------------------------------------------- ---------------------------------------

Requirements
============

Computing Resources
-------------------

In order to successfully implement and execute the quantum perceptron
models on a quantum processors, access to a quantum information
processing device is a must. If such an access is not available, we will
implement and execute the models on quantum simulators which serve the
purpose of simulating actual quantum processors.

IBM Q offers public access to the 5-qubit and 16-qubit quantum computers
known as IBMQ5 and IBMQ16. We will be using the cloud access in order to
execute the developed programs on the processors.

Academic Resources
------------------

Access to academic articles and journals actively covering the most
recent advancements in the field of Quantum Computing and Algorithms is
required. This is partially fulfilled through the University of Manitoba
Library Resources. In addition, if needed active correspondence to the
expert academic resources at the University of Manitoba and experts in
the field of Quantum Algorithms and Computation can be achieved through
e-mail and other modes of communication.

Outcomes and Deliverables
=========================

Outcomes
--------

Through this industrial project, we primarily attempt to accomplish the
following :

1.  Gain a thorough understanding of the programming principles and
    fundamental pre-requisites for the development and implementation of
    complex quantum algorithms on near-term quantum processors such as
    the IBM Q.

2.  Explore in detail the current best models for the Quantum Perceptron
    and through the implementation and testing process, learn about the
    previously unforeseen challenges in developing scalable quantum
    algorithms for the Quantum Perceptron.

Deliverables
------------

At the completion of this industrial project, we wish to deliver the
following:

1.  Implementation details and results for the execution of the proposed
    Quantum Perceptron algorithms on the IBM Q Platform's available
    backends such as the IBMQ5.

2.  In-depth analysis and potential solutions to the scalability issues
    of Quantum Perceptron models for near-term quantum information
    processing devices.
