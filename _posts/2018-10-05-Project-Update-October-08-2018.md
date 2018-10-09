---
layout: post
title: Project Update - October 08, 2018
---

## COMP 4520 - Project Update - October 08, 2018

----

### Table of contents

#### 1. [Objectives for the past 2 weeks](#objectives_for_the_past_2_weeks)

#### 2. [Current Status](#current_status)

----

### Objectives for the past 2 weeks<a id='objectives_for_the_past_2_weeks'></a>

> **1. Gain a deeper understanding of Grover's algorithm and its applications to Graph Algorithms**

Originally introduced in the following research paper - A fast quantum mechanical algorithm for database search by Lov K. Grover (1996), [https://arxiv.org/abs/quant-ph/9605043](https://arxiv.org/abs/quant-ph/9605043). Grover's algorithm is a quantum search algorithm which offers a polynomial speedup with exponential runtime limit of O(sqrt(n)) over the best known classical search algorithm, exploiting quantum properties such as entanglement and superposition for searching an item in an unstructured database with probability > 50%.

Many quantum graph algorithms researched so far either directly use Grover's algorithm or use some variation of it specifically for the purpose of spanning or walking graphs to search for some properties, which allow a speed up over the best classical algorithms while searching for graph properties.

The initial state is constructed applying a Hadamard transform (H⊗n) on|x〉 and applying a Pauli X transform followed by a Hadamard transform (HX) to q, where q is the ancillary qubit.

The algorithm uses a Quantum oracle which can be developed classically before apply the algorithm. For applying Grover's algorithm to grpahs, we use an adjacency matrix model for graphs and construct a oracle using the adjacency matrix.

Once the oracle is constructed, the Grover's operator, G = (2|ψ〉〈ψ|−I)O where I is the Identity Operator and O is the Oracle Operator is applied to the initial state.

This allows to increase the amplitude of|x∗〉 while decreasing the amplitude of the other states, where |x*> corresponds to the qubit string of the item being search for in the database.

The algorithm has far more applications than just unstructured database querying and belongs to a class of Quantum Search Algorithms which we will explore as a part of the research effort.


> **2. Build up on knowledge on Quantum Parallelism theory**

The Deutsch's Algorithm and the Deustch-Josza Algorithm were researched in order to explore another class of Quantum Algorithms based on the Quantum Fourier Transform, since the concepts are necessary in order to develop an understanding of the underlying mechanics of some of the most widely known Quantum Algorithms ( Shor's Factoring Algorithm, Amplitude Amplification ) and their applications to quantum algorithms for searching graphs properties.

Deustch's Algorithm : [IBM Q : Deutsch-Josza Algorithm](https://quantumexperience.ng.bluemix.net/proxy/tutorial/full-user-guide/004-Quantum_Algorithms/080-Deutsch-Jozsa_Algorithm.html)


>  **3. Researching classical theories of Graph Algorithms**

Since many of the quantum algorithms are based on classical analogues, research was carried out on exploring classical algorithms for searching graph properties such as Classical Random Walks and Markov Chains.

In addition, began research on Quantum Random Walks to understand the underlying principles of using randomization in Quantum Algorithms.
  
----

### Current Status<a id='current_status'></a>

> **1.. Current short-term research focus**

- Current focus will be to complete the research on Grover's Algorithm and prepare a presentation on some fundamental algorithms for the Project supervisor and any interested candidates in the research group and develop executable Python programs which construct the circuit and execute on local QASM simulators and remote Quantum machines, as well as continue research on classical graph searching algorithms which use randomization to find overlap between Quantum randomized algorithms and Classical randomized algorithms to determine any improvements over classical methods.

> **2. Current challenges and their foreseeable solutions**

- N/A

