---
layout: post
title: Project Proposal
---
## COMP 4520 – Undergraduate Honours Project Proposal

### Title : An analysis of computational complexity and implementation requirements of quantum graph algorithms on an Universal Quantum Computer.
### Abhishek ., 7803917

**1. Abstract**

Recent breakthroughs in Quantum Computing has enabled public access to a wide array of actual quantum hardware and simulators. With the progress to achieving "quantum supremacy" **(1)(4)** being accelerated by tech giants such as Google, IBM and Microsoft, the need for algorithms to exploit the "quantum effects" of the hardware has emerged rapidly. In this research effort, we explore and evaluate the implementations of graph algorithms such as TSP and Dijkstra’s Shortest Path on simulated and actual universal quantum computers, as well as determine changes to the computational complexity and runtime speedup provided by such implementations. We use IBM's Q Platform as a base for development and execution with the help of Qiskit, an open-source quantum computing framework in Python. 


**2. Introduction to the topic**

The basis of information processing in Quantum Computing lies in qubits. A qubit is two-state quantum mechanical system often described in Quantum Computing literature as a superposition in the standard basis {0,1}. The following is a representation of the state of the qubit in the standard basis:


|Ψ> = α|0> + β|1>,
where α,β are probability amplitudes with |α|² + |β|² = 1.


When measured in the standard basis, the probability of the outcome |0> with the measured value 0 is |α|², and of the outcome |1> with the measured value 1 is |β|².

While the vector spaces of classical objects combine through a direct sum (⊕), the vector spaces associated with quantum systems combine through the tensor product (⨂). For example, consider n classical objects with m-dimensional vector space, the joint state space of these n objects has m.n dimensions whereas for n quantum systems associated with m-dimensional vector space, the joint state space has mn dimensions, the state space of a quantum system grows exponentially. This means there are vastly more states available to encode the information in. This behaviour of large state spaces corresponding to small physical quantum systems is at the center of the computational speedup exploited by quantum hardware, and therefore quantum algorithms.

A basic operation on the state of a qubit is implemented through a series of unitary transformation, where a unitary transformation is described by a matrix U with complex entries, which satisfies the following condition:
UU^ = U^U = I, where U^ denotes the transposed complex conjugate matrix of U, and I denotes the identity matrix.

Such basic operations are referred to as gates, of which {H,T,CNOT} i.e. {Hadamard, Toffoli, Controlled Not} form a universal gate set.
As described in **(2)**, a quantum algorithm comprises of 3 important steps - 1. encoding of the data, 2. sequence of quantum gates applied to the set of input qubits, and 3. measurements of one or more of the qubits at the end to obtain a classically interpretable result.

From a classical computing point of view,  graph problems such as TSP are NP-hard combinatorial optimization problems with various classical approaches such as branch-and-bound algorithms as well as heuristics and approximation algorithms being used to yield good solutions **(3)**. We will look at several of such optimization problems and try to determine and analyse the  computational complexity of the quantum implementation of such algorithms and check whether if any such implementations would belong to the BQP ( bounded-error quantum polynomial time ) complexity class.



