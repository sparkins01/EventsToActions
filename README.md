
This repository provides the code and experimental works for a project undertaken by the University of Huddersfield funded through the Autonomous Resilient Cyber Defence (ARCD) programme. An overview and report can be found [here](https://github.com/sparkins01/ARCD/blob/main/Project%20Overview%20and%20Report.pdf)


**[1. Data Generator](https://github.com/sparkins01/ARCD/tree/main/1.%20Data%20Generator)** 
This C# application provides a parameterised event dataset generation with the inclusion of synthetic event chains. An event chain is a group of events sharing common object occurrence.

Once compiled, the application takes the following 7 command line inputs:

1. Number of chains
2. Number of events in each chain
3. Number of objects in each event
4. Similarity between objects in events (0-100%)
5. Total events available to the generation process
6. Total unique objects available to the generation process
7. Number of times to repeat a chain

A full description of the parameters is available in Paper 2 in the 'Research Papers' folder.

In the Debug\netcoreapp3.1 folder, there is the ‘EvtGenScript.BAT’ which will generate all the datafiles used for benchmarking purposes in Paper 2.


**[2. Clustering Python](https://github.com/sparkins01/ARCD/tree/main/2.%20Clustering%20Python)**
This Python code was used during the experimental part of this project. 

The first file 'All Algorithms.py' was used to benchmark 5 algorithms (Optics_RI, DBSCAN_RI, Mean Shift_RI, Affinity_RI, Agglomerative_RI) against a small subset of data generated using the '1.Data Generator' code.

The second file 'DBScan.py' uses only the DBScan algorithm on the full set of benchmarking data (generated using 'EvtGenScript.BAT' in '1.Data Generator') to establish how well it can detect event-chains. The Adjusted Rand Index (ARI) is used to calculate the match and the full results are available in Paper 2.


**[3. Prototype](https://github.com/sparkins01/ARCD/tree/main/3.%20Prototype)**
This C# project has been created to demonstrate how event generation, event-chain identification, conversion to an action model, to exploitation using model-based reasoning can be achieved. The purpose of the prototype is to demonstrate how this can work and to serve as a starting point for anyone wanting to build on the research of implement a specific use case.

The application is driven by a primitive user interface consisting of four tabs. The four tabs providing the following features:
 
1. Dataset Generator: a user interface version of the '1. Data Generator' application
2. Cluster -> Event Chains: utilises a C# implementation of DBSCAN to identify event chains through clustering.
3. Event Chains -> Actions: Enables the user to select which parts of the event chain form an action's precondition.
4. Planner: Uses the Local Planning Graph tool to deliberate over which actions can be applied to the event dataset.



**[Research Papers](https://github.com/sparkins01/ARCD/tree/main/Research%20Paperse)**
The two research articles were produced during this project. Please cite accordingly:


1.	[Khan, S., Parkinson, S., & Murphy, C. (2023). Context-based irregular activity detection in event logs for forensic investigations: An itemset mining approach. Expert Systems with Applications, 233](https://github.com/sparkins01/ARCD/blob/main/Research%20Papers/Paper%201.pdf) 
2.	[Khan, S., Parkinson, S., Roopak, M. & Murphy, C. (2023) Benchmarking a Parameterised Approach to Generating and Detecting Event Chains in Security Dataset, Submitted to Journal of Information Security and Applications](https://github.com/sparkins01/ARCD/blob/main/Research%20Papers/Paper%202.pdf)



For any queries, please contact s.parkinson@hud.ac.uk
