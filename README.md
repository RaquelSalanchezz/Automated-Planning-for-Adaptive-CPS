# Automated Planning for Adaptive Cyber-Physical Systems under Uncertainty in Temporal Availability Constraints

## Abstract
In smart Cyber-Physical Systems (sCPS), a critical challenge lies in task planning under uncertainty. 
There is a broad body of work in the area with approaches able to deal with different classes of constraints (e.g., ordering, structural) and uncertainties (e.g., in sensing, actuation, latencies). 

However, planning under temporal availability constraints, i.e., when a given resource or other element of the system required to perform a task is available only during a limited and variable time window, is a challenge that remains largely unexplored. 

This repository contains the replication package of the code for the article Automated Planning for Adaptive Cyber-Physical Systems under Uncertainty in Temporal Availability Constraints. This paper presents an approach to address this challenge, employing genetic algorithms to incorporate temporal uncertainties effectively. Our method demonstrates enhanced robustness and efficiency in task-based sCPS scenarios with variable time windows, such as electric vehicle charging and healthcare robotics.  

Our evaluation shows that our approach significantly reduces computational cost and maintains solution feasibility under prescribed levels of uncertainty, outperforming MILP-based optimization.

## Dependencies 
This project addresses the challenge of planning tasks under conditions of uncertainty, specifically focusing on planning under temporal availability constraints, where necessary resources are only available during limited time windows. We present an approach that utilizes genetic algorithms to tackle this issue, enhancing robustness and efficiency in sCPS scenarios such as electric vehicle charging and healthcare robotics.

Specifically, two types of strategies are employed to address the problem: the first utilizes linear programming techniques with constraints (MILP algorithm), and the second employs a multi-objective genetic algorithm. In the case of the MILP algorithm, uncertainty is not considered, and its results will serve as a baseline for comparisons in terms of quality, effectiveness, and efficiency with respect to the results achieved by the genetic algorithm, which does consider uncertainty.

The project is implemented in the latest version of Python (3.12.1) and requires the installation of the following libraries for its development and execution:

* Pulp 2.7.0
* NumPy 1.26.2
* Matplotlib 3.8.2
  
## Repository structure
This repository contains the following items:
* `Readme.md`: this file explaning the code of the project
* `Vehicles_algorithms`: this folder contains two files
  * `vehicles_without_uncertainty.ypinb`: this file contains the differente versions of the algorithms that solve the vehicle charging planning problem without considering uncertainty. This is where the implementation of the MILP algorithm used as the basis for the experiments is located.
  * `vehicles_under_uncertainty.ypinb`: this file contains the differente the algorithms that solve the vehicle charging planning problem considering uncertainty. This is where the implementation of the genetic algorithm used in experiments is located.
* `Robots_algorithms`: this folder contains the file `Robots_algorithms.ypinb`. In this file, we can find the two algorithms implemented to solve the problem of robots in the healthcare domain (The MILP algorithm that does not consider uncertainty and the genetic algorithm that does).
* * `Data`: in this folder we can find the data files used to run the experiments.
  * `example_vehicle_objects.txt`: code that contains the data you can modify and add to the algoritms code to conduct experiments. You can copy and paste all the content or part of it directly in the code.
  * `vehicles.txt` and `patients.txt`: data files used to run the algorithms in some experiments. These are files external to the code.
  * `evaluation_charts.ypinb`: code used to generate the evaluation charts included in the paper.

## Running the Experiments
To run the code, you need to do it within the Google Colab, Jupyter Notebook, or a similar environment. The following explains how to run algorithms in Google Colab:

### Importing an IPython Notebook File:

1. **Upload the File:**
   - Open Google Colab and create a new notebook.
   - Click on the folder icon on the left to open the file panel.
   - Click the "Upload" button and select your `.ipynb` file from your computer.

2. **From GitHub:**
   - If the file is on GitHub, provide the link to the file directly in Colab. Use the following syntax:
     ```python
     !wget https://raw.githubusercontent.com/user/repository/file.ipynb
     ```

### Executing an IPython Notebook File:

1. **Code Cells:**
   - Open the `.ipynb` file in Colab, and you'll see code cells. You can execute each cell individually.

2. **Running Cells:**
   - Run a cell by clicking the play button next to the cell or using the keyboard shortcut Shift + Enter.

3. **Execution Order:**
   - Ensure you run the cells in the correct order as the state of variables and functions is maintained between cells.

4. **Installing Dependencies:**
   - If the code depends on external libraries, install them in a code cell. For example:
     ```python
     !pip install library-name
     ```

5. **Restarting the Runtime:**
   - In some cases, restart the runtime environment. Do this from the "Runtime" menu > "Restart runtime."

6. **Saving Changes:**
   - If you modify the code and want to save to the original file, download the notebook after making changes.

Remember that any changes you make in Colab won't affect the original file on your computer. If you want to save changes, download the notebook from Colab and replace the original file with the modified version locally.

### Execution of algorithms for the vehicles context. 
For the case of electric vehicles, the final version of the genetic algorithm is in file 'vehicles_under_uncertainty.ypinb' while the MILP algorithm is in file 'vehicles_without_uncertainty.ypinb'. To run the code, you must follow the detailed steps in the previous section. You can execute the algorithms using the data files or create them directly in the code using the content of 'data.txt'. The general steps you should follow to test the algorithms are as follows:

1. Import the data files into the environment if you wish to use them, or modify the code snippet where vehicles and chargers are declared by adding or removing them and editing their characteristics. You can use the file data.txt for this purpose.
2. Execute the cells where libraries are installed, classes are declared, and basic functions required by the algorithms are defined.
3. Run the cell containing the main program. The output of this cell displays the planning, the total cost of the solution, and the timespan.

### Execution of algorithms for the robots context.
The algorithms solving the robot problem are both in file 'Robots_algorithms.ypinb'. Similarly, for the vehicles case, you have the option to run the algorithms by utilizing existing data files or generating them directly in the code using the contents of 'data.txt'.

1. Import the data files into the environment if you intend to utilize them. Alternatively, you can modify the code snippet where robots and patients are declared by adding or removing them and adjusting their characteristics. The file data.txt can be employed for this task.
2. Execute the cells where libraries are installed, classes are declared, and basic functions required by the algorithms are defined.
3. Run the cell containing the main program. The output of this cell displays the planning, the timespan of the solution.

### Execution of the code to generate the charts
You can also generate the evaluation charts using the code found in evaluation_charts.ypinb. To achieve this, simply run the cells in order, and various graphs will be displayed as output. If you wish to modify the data to create new graphs, you can do so by editing the data matrices at the beginning of the code that generates each graph.

## Using the data files and generate your own input data
As already shown, there are three files within the 'Data' folder containing sample data for running the algorithms.
* The file `example_vehicle_object.txt` contains example code for creating different objects of the 'Vehicle' class. You can copy and paste its entire content or parts of it to directly create vehicles within the algorithm code without using external files. The file includes up to 150 vehicles and has been used to run various experiments. Each vehicle is initialized with a set of parameters: the vehicle identifier, the distance it has to travel, the approximate arrival and departure times, current load, battery capacity, charging speed, and discharge rate. The parameters are set in that order. Following this structure, we can create new vehicles with new data.
* On its part, the files `vehicles.txt` and `patients.txt`. These constitute external data files that you can add to the runtime environment to execute the algorithms. In the case of 'vehicles.txt', each line represents a vehicle, and each parameter is separated from another by a comma (,). The parameters are defined in the order explained in the previous section. In the case of 'patients.txt', each line represents a patient consisting of the following parameters: identifier, distance to the room, availability schedule of the companion, and an indicator of whether the meal has been delivered or not. You can create new files following this structure or add new lines to the existing ones to test the algorithms




