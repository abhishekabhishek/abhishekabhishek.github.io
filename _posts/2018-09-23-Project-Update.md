---
layout: post
title: Project Update - Sept 26, 2018
---

## COMP 4520 - Project Update - Sept 26, 2018

----

### Table of contents

#### 1. [Objectives for the past 2 weeks](#objectives_for_the_past_2_weeks)

#### 2. [Current Status](#current_status)

#### 3. [Objectives for the next 2 weeks](#objectives_for_the_next_2_weeks)

----

### Objectives for the past 2 weeks<a id='objectives_for_the_past_2_weeks'></a>

1. **Detemine the background research conducted in the field of exploring graph properties on Quantum Computers**

2. **Setup the experimentation environment for testing algorithm implementations**

```python
#!/home/q/.conda/envs/qdev/bin/python3
# -*- coding: utf-8 -*-

# System libraries required for execution
import os

# Configuration file parser
from configparser import ConfigParser

# Basic qiskit modules
from qiskit import available_backends, execute, register, least_busy

#-----------------------------------------------------------------------
#  Class - getBackends
#  Purpose - Read in the API tokens and configuration for setting up an
#  access points to the IBM Q backends
#-----------------------------------------------------------------------

class BackendManager:
    
    # Initializer method for the backendManager class
    # Reads in the API token and URL from the configuration file and registers
    # for access
    def __init__(self, config_path):
        
        # Get the correct POSIX path of the configuration file
        configFilePath = os.path.join(str(os.path.expanduser('~')), config_path)
        print("The configuration file currently being read " + str(configFilePath))
        
        # Setup the configuration reader file buffer
        configReader = ConfigParser()
        configReader.read(configFilePath)
        
        # Get the APItoken and the URL from the configuration file and list all
        # the available backends from IBM Q
        try:
            # Read in the API token and the URL, and register
            register(configReader.get('API', 'APItoken'), configReader.get('API', 'URL'))
        except: 
            print('Error. Invalid token or URL entered')
        
    # Class method to read in the configuration file and get a list of
    # available backends
    def list_all_backends(self):
        
        # List the available actual Q backends
        print('The list of available Q backends for this API token', available_backends({'local': False, 'simulator': False}))

        # List the remote simulator backends
        print('The list of available remote simulator backends for this API token', available_backends({'local': False, 'simulator': True}))
            
        # List the available local backends
        print('The list of available local Q backends for this API token', available_backends({'local': True, 'simulator': False}))
        
        # List the available local simulation backends
        print('The list of available local simulation backends for this API token', available_backends({'local': True, 'simulator': True}))
        
        
    # Class method to get and return the least busy backend available for usage
    def get_least_busy_backend(self):
        
        least_busy_backend = least_busy(available_backends({'simulator': True, 'local': True}))
        print('The least busy available Q backend is', least_busy_backend)
        
        return least_busy_backend
```

```python
#!/home/q/.conda/envs/qdev/bin/python3
# -*- coding: utf-8 -*-

# Basic OS modules
import time

# Basic qiskit modules
from qiskit import ClassicalRegister, QuantumRegister, QuantumCircuit, execute

# Basic visualiztion tools
from qiskit.tools.visualization import plot_histogram, circuit_drawer

# Class - entanglement
# Purpose - Create a quantum circuit to test entanglement on local simulator 
# and remote Q machines

class Entanglement:
    
    # Initialize the class with the skeleton circuit for the operations defined
    # by the number of Quantum and Classical registers
    def __init__(self, qreg=2, creg=2):
        
        # Initialize the Quantum Circuit
    
        # Create a quantum register "qr" with qreg qubits
        qr = QuantumRegister(qreg)
        
        # Create a classical register called "cr" with creg bits
        cr = ClassicalRegister(creg)
        
        # Create a Quantum Circuit involving "qr" and "cr"
        self.circuit = QuantumCircuit(qr, cr)
        
        # Add the operations to the Quantum circuit 
        
        # Add a Hadamard gate on qubit 0, putting this state in a superposition
        self.circuit.h(qr[0])
        
        # Add a CX (CNOT) gate on control qubit 0 and target qubit 1, putting
        # the two qubits in a Bell state.
        self.circuit.cx(qr[0], qr[1])
        
        # Add a Measure gate to see the state
        self.circuit.measure(qr, cr)
        
    # Create a job on the backend specified in the parameter, execute the job 
    # and plot the results
    def create_execute_circuit(self, backend_to_use):
        
        # Create a new job on the backend to use
        job_exp = execute(self.circuit, backend=backend_to_use, shots=1024, max_credits=3)

        # Determine the time constraints for the execution
        lapse = 0
        interval = 30
    
        # While loop to run until the job is executed
        while not job_exp.done:
            print('Status @ {} seconds'.format(interval * lapse))
            print(job_exp.status)
            time.sleep(interval)
            lapse += 1
        
        print(job_exp.status)
        plot_histogram(job_exp.result().get_counts(self.circuit))

    # Plot the quantum entanglement circuit
    # Parameters - Pointer to the self object to access the circuit object to 
    # plot
    def plot_circuit(self):
        circuit_drawer(self.circuit)
```

3. **Build up on background knowledge on quantum algorithm development**

4. **Determine the short-term focus of the project**
  
----

### Current Status<a id='current_status'></a>

1. **Current short-term research focus**

2. **Current challenges and their foreseeable solutions**

----

### Objectives for the next 2 weeks<a id='objectives_for_the_next_2_weeks'></a>

1. **Project topics to research**

2. **Expected challenges**

3. **Research plan**

----
