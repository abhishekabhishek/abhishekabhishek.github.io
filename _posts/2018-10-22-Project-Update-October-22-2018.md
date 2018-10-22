---
layout: post
title: Project Update - October 22, 2018
---


## COMP 4520 - Project Update - October 22, 2018

----
### Table of contents

#### 1. [Accomplished in the past 2 weeks](#accomplished_in_the_past_2_weeks)

#### 2. [Objectives for the next 2 weeks](#objectives_for_the_next_2_weeks)
----

### Accomplished in the past 2 weeks<a id='accomplished_in_the_past_2_weeks'></a>

> **1. Finished the research on Grover's Algorithm and implementations on IBM Q**

**Grover's Algorithm Implementation Summary :**

**a. Introduction**

The algorithm belong to a general class of Quantum Search Algorithms and can be used to speed up searching in a unstructured database quadratically. The applications can be generalized to more than just searching unstructured databases since the algorithm uses a trick known as Quantum Amplitude Amplification which serves as a general basis to obtain quantum run-time improvements.
        
**b. Time-Complexity Analysis**
   
Searching an unsorted and unstructured list of N items can be easily shown to have a classical average run time of N/2 and worst-case time-complexity of O(N).
        
Using Grover's Algorithm and the Quantum Amplitude Amplification trick, the quantum implementaion can be shown
to have a worst-case time-complexity of O(sqrt(N)).

The algorithm is generic in the sense that it does not use the internal structure of the list to do the search and is therefore generalizable to other data structures.

**c. Algorithm Implementaion**

...

