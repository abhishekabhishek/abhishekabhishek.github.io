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
