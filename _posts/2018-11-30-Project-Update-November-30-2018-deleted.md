---
layout: post
title: Project Update - November 30, 2018
---

## COMP 4520 - Project Update - November 30, 2018

----
### Table of contents

#### 1. [Accomplished in the past 2 weeks](#accomplished_in_the_past_2_weeks)

#### 2. [Objectives for the next 2 weeks](#objectives_for_the_next_2_weeks)
----

### Accomplished in the past 2 weeks<a id='accomplished_in_the_past_2_weeks'></a>

> **1. Finished the research on Grover's Algorithm and initial implementations on IBM Q**

**Grover's Algorithm Implementation Summary :**

**a. Introduction**

The algorithm belong to a general class of Quantum Search Algorithms and can be used to speed up searching in a unstructured database quadratically. The applications can be generalized to more than just searching unstructured databases since the algorithm uses a trick known as Quantum Amplitude Amplification which serves as a general basis to obtain quantum run-time improvements.
        
**b. Time-Complexity Analysis**
   
Searching an unsorted and unstructured list of N items can be easily shown to have a classical average run time of N/2 and worst-case time-complexity of O(N).
        
Using Grover's Algorithm and the Quantum Amplitude Amplification trick, the quantum implementaion can be shown
to have a worst-case time-complexity of O(sqrt(N)).

The algorithm is generic in the sense that it does not use the internal structure of the list to do the search and is therefore generalizable to other data structures.

**c. Algorithm Details**

Let 1,2,...,w,..,N-1,N be the indices of an unstructured database where w corresponds to the index with the item being searched for.

1. In order to encode the list as an input to a Quantum circuit, we use a binary encoding such that an index x belongs to the set {0,1}^n, where x is unique for each index <= N i.e. generic binary encoding for N indices in n qubits, where N = 2^n.

2. We also consider the function, f such that 
                                         f(x) = 0 for all x in [0,N] when x != w 
                                         f(x) = 1 when x == w.
   We use the function described above to construct a unitary operator, U<sub>f</sub> such that U<sub>f</sub> negates the amplitude for the state \|w> and leaves the amplitude for \|x> unchanged when \|x> != |w>.
   
3. The initial state is constructed by applying a Hadamard transform (H⊗n) to the state \|0><sup>⊗n</sup> which gives us a uniform superposition \|ψ〉 with equal amplitude for each of the basis states.

4. If we perform a measurement on the state \|ψ〉, we have 1\N probability of retrieving the item currently being searched. However, the procedure of amplitude amplification allows us to significantly improve this probability by apply two operators, U<sub>f</sub> and U<sub>s</sub> on the initial state. By applying these two operators t times to the inital state, the procedure amplifies the amplitude of the \|w> state which due to the normalization property of the wavefunction \|ψ〉, reduces the probability of the rest of the states, \|x>.

5. It can be theoretically shown that sqrt(N) operations of the operators can amplify the amplitude such the state \|w> can obtained through measurement with near-certainity. Each application of the combined operator corresponds to 1 timestep which gives use the therotical worst-time complexity of O(sqrt(N)).

**d. Algorithm Implementation details**

**e. Algorithm Python implementation**

To be updated

### Objectives for the next 2 weeks

> **1. Implement complex variants of Grover's Algorithm**

This would include determining the adjacency matrix of a graph, and using that to construct an oracle function which could be used in a Quantum search circuit. Additionaly, would have to implement sub-routines to determine the item to be searched in the superposition states.

> **2. Determine the complexity of implementing Grover's search algorithm for a Graph spanning problem**

Currently working on implementing Grover's search in conjunction with Djikstra's Algorithm to determine the viability of implementing the Quantum search algorithm for the Shortest Path Problem.
