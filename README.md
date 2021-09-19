# Reinforcement Learning-based Path Planning for Autonomous Aerial Vehicles in Unknown Environments

## Intro 

This repository contains a collection of the files produced during the Master Thesis in Mechatronic Engineering we pursued in 2021 at Politecnico di Torino (Italy). The title of the thesis is "Reinforcement Learning-based Path Planning for Autonomous Aerial Vehicles in Unknown Environments". A good overview of the project can be found in the paper we presented at the 2021 AIAA forum. In the paper, the main idea behind the project is explained, along with some technical detail about the development and implementation of the algorithm. Moreover, all the relevant results are presented and discussed. The paper is available on ResearchGate at https://www.researchgate.net/publication/353530217_RL-based_Path_Planning_for_Autonomous_Aerial_Vehicles_in_Unknown_Environments. If you want a more in-depth analysis of the algorithm you can contact us and ask for a copy of the thesis, where the development and implementation of the algorithm is discussed in detail.

The files collected in this folder regard the simulation environment creation, the RL agents training and the simulation of the UAVs operations used to produce all the numeric results. Below, a brief description of each folder role inside the project can be found.

## Project description

The main goal of the project is to use Reinforcement Learning (RL) to implement an *exploration algorithm* capable of driving a small fleet of UAVs in the exploration of an unknown environment. This kind of task presents several different challenges. In fact, each drone must be capable of moving in space without hitting any obstacle or other drones. At the same time, it has to continue the exploration task - or any other task assigned to it. While performing these tasks, the drones must also communicate with each other in order to coordinate the exploration following a common strategy and share useful information to optimise the execution of the task. All these issues have to be solved and their solutions merged in an organic algorithm. The focus of the project is on the sections of algorithm regarding path planning, obstacle avoidance and exploration coordination. 

The case study scenario assumes that a number *n* of UAVs is placed in some given initial locations inside of an unknown region. The task of the UAV fleet is to explore (i.e. obesrve through the use of sensors and cameras) as much as possible of the environment in the least amount of time. The approach taken during the development of the exploration algorithm has been to split the exploration task in two parts. The first part is called *coverage* algorithm and has the task of coordinating the exploration process. A copy of this algorithm runs on each of the UAVs; each UAV is responsible for the decision of its own target location. Each UAV computes its own target point by taking into account the avaliable data about environment shape, obstacle position and other UAVs location. By accessing these info, each UAV computes its own target location by running the *coverage agent*, i.e. a properly RL-trained Neural Network (NN). The image below shows how a fleet of 4 UAVs exploit the coverage agent to generate 4 different target locations.

 ![Coverage NN output](/Media/coverage_output.png)
 

## Repository folders

This repository contains several folder, each one corresponding to a different development stage of the algorithm:
- models: the folder contains some trained models (i.e., trained RL agents). Currently, in the folder are uploaded only a few models, which are some of the best ones obtained during the training phase. These models are the ones that can be used during the simulations in the *main* folders;
- maps: the folder contains the map datasets used for the training and validation of the algorithm. The folder contains several training datasets, which have been built over time to try and find the optimal map type to obtain a faster and more reliable training process. A set of validation maps is also present. The folder also contains the MATLAB files used to generate the maps. They can be used to generate new training and validation/simulation maps;
- main:
- main [only coverage]:
- main [only path planning]:
- main [3D]:
- training coverage:
- training path planning:
- media: lastly, the *media* folder contains some images and videos that show the results obtained. Some more images and plots (which illustrate the performance quality of the algorithm) can be found in the aforementioned paper on ResearchGate.

It is worth mentioning that, during the training process, we used the website *wandb* (aka "Weight and Biases", https://wandb.ai/) to log some useful training information. Moreover, we used the HPC cluster of Politecnico di Torino (https://hpc.polito.it/) to perform the trainings. Therefore, it could be necessary to comment or modify some lines in the main files in order to be able to succesfully start the trainings. In the same way, it could be necessary to modify the path to some folder (e.g. the training maps folder) to match the actual location of the directories on your PC.

## Contacts

For any question or suggestion feel free to contact us at battocletti.gianpietro@gmail.com or riccardourban@hotmail.it. Here on GitHub you can also visit our personal profiles https://github.com/gbattocletti and https://github.com/RiccardoUrb.
