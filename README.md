# Automated Planning for Adaptive Cyber-Physical Systems under Uncertainty in Temporal Availability Constraints


## Sumary 
This repository contains the replication package of the article Automated Planning for Adaptive Cyber-Physical Systems
under Uncertainty in Temporal Availability Constraints- This project addresses the challenge of planning tasks under conditions of uncertainty, specifically focusing on planning under temporal availability constraints, where necessary resources are only available during limited time windows. We present an approach that utilizes genetic algorithms to tackle this issue, enhancing robustness and efficiency in sCPS scenarios such as electric vehicle charging and healthcare robotics.

Specifically, two types of strategies are employed to address the problem: the first utilizes linear programming techniques with constraints (MILP algorithm), and the second employs a multi-objective genetic algorithm. In the case of the MILP algorithm, uncertainty is not considered, and its results will serve as a baseline for comparisons in terms of quality, effectiveness, and efficiency with respect to the results achieved by the genetic algorithm, which does consider uncertainty.

The project is implemented in Python and uses libraries like Pulp, NumPy, and Matplotlib. All the details of the project are described in the final paper.

## Artifact structure
This repository contains the following items:
* Readme.md: this file explaning the code of the project
* Vehicles_algorithms: this folder contains two files
  * vehicles_without_uncertainty.ypinb: this file contains the differente versions of the algorithms that solve the vehicle charging planning problem without considering uncertainty. This is where the implementation of the MILP algorithm used as the basis for the experiments is located.
  * vehicles_under_uncertainty.ypinb: this file contains the differente the algorithms that solve the vehicle charging planning problem considering uncertainty. This is where the implementation of the genetic algorithm used in experiments is located.
* Robots_algorithms.ypinb: in this file, we can find the two algorithms implemented to solve the problem of robots in the healthcare domain (The MILP algorithm that does not consider uncertainty and the genetic algorithm that does).
* data.txt: code that contains the data you can modify and add to the algoritms code to conduct experiments.
* vehicles.txt and pacientes.txt: data files used to run the algorithms in some experiments.
* evaluation_charts.ypinb: code used to generate the evaluation charts included in the paper.

## Development requirements
To run the code, you need to do it within the Google Colab, Jupyter Notebook, or a similar environment. Simply download it from this repository and paste it into the chosen environment.

## Running the Algorithms
After adding the files to the environment, simply execute the desired sections. For the case of electric vehicles, the final version of the genetic algorithm is in file 'vehicles_under_uncertainty.ypinb' while the MILP algorithm is in file 'vehicles_without_uncertainty.ypinb'. The algorithms solving the robot problem are both in file 'Robots_algorithms.ypinb'. Yo can execute the algorithms using the data files or create them directly in the code using the content of 'data.txt'.

You can also generate the evaluation charts using the code using the code found in evaluation_charts.ypinb.



