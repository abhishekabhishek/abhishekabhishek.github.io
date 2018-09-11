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


**3. Background preparation**


For the past 8 months, I have carried out independent research into the building blocks of Quantum Computing through textbooks and online resources ( theoretical ) and the frameworks and libraries available for the implementation of generic quantum algorithms ( e.g. Grover’s Database Search, Shor’s Factoring Algorithm ) on both actual quantum hardware, and simulators running on local and remote machines ( experimental ).
Courses taken for building a background for the project are following:

PHYS 2390: Theoretical Physics 1
Relevant learnings - Mathematical methods used for understanding and explaining the interaction between physical systems.

COMP 2140: Data Structures and Algorithms
Relevant learnings - Common combinatorial graph optimization algorithms and introductory algorithm analysis.

COMP 2380: Quantum Physics 
Relevant learnings - Mathematical methods associated with quantum systems. Proofs related to observations from quantum systems with no classical counterpart. 

PHYS 2490: Theoretical Physics 2
Relevant learnings - Solutions to ordinary and partial differential equations in classical and quantum physics,  introductory probability theorems and common distributions.

COMP 2080: Analysis of Algorithms
Relevant learnings - Advanced algorithm analysis using methods for analyzing the time and space requirements of the algorithms, exploring different models of computation, algorithm design using different strategies ( e.g. greedy, randomized algorithms )

PHYS 3380: Quantum Mechanics 2
Relevant learnings – Developing abstract linear algebraic formalism for quantum mechanical states and operators with classical measurements, solutions to 1-dimensional and 3-dimensional Schrodinger’s equations for the hydrogen atom, degeneracy in quantum states.

**4. Related work**


Most of the initial progress in the implementation of quantum algorithms for combinatorial optimization problems was based on an adiabatic quantum computing model and the algorithms were implemented and tested on quantum annealers ( actual and simulated ) **(5) (6) (7)**. However, the quantum annealer is the least powerful and most restrictive form of quantum computers with no known advantages over conventional computing with the only known application being to optimization problems.
To the best of my knowledge, the research into the development of optimization algorithms for universal quantum computer hardware is still in very early stages, particularly due to the impeding restriction on the number of qubits being available of both the simulators and the developed quantum hardware.
The groundwork for building such algorithms have been laid by the development of quantum algorithms that are quadratically or exponentially faster than the theoretical limit for classical algorithms such as Grover’s search algorithm **(8)** and Shor’s factoring algorithm **(9)**. Many optimization and quantum machine learning algorithms rely on Grover’s search or one of its variants. We would use the corresponding pre-defined operators and call oracles if necessary for the development and implementation of the quantum graph algorithms.


**5. Problem Statement**

Problem: What is the feasibility and computational complexity of quantum graph algorithms, and how much resources are required to develop, implement, and execute such algorithms on actual and simulated universal quantum computers ?


Goal: Thorough analysis of the implementation, deployment and execution of the developed algorithms.


**6. Methodology**

The methodology used will be adapted from my first co-op term at Online Business Systems which I have found to be very useful to stay on track as well as quantify any progress made. The first step will be to organize an HMW ( How Might We? ) session with any individuals involved in this research effort to determine the major stages and checkpoints in the project as well as identify any foreseeable challenges and raise objections to the deliverables set forward.


The project vision will be divided into a series of iterative step-projects, one building upon the other. The series is dynamic and will evolve as any unforeseen challenges emerge. Here is an initial overview of what the step-projects will look like :









