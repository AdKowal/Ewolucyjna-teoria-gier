# Introduction
The goal of the project was to create a simulator to test evolutionary game theory. Evolutionary games are a combination of game theory and biology aimed at studying the evolutionary processes between individuals. The most important difference 
between classical and evolutionary games is iteration. This program runs a simulation based on an iterated prisoner's dilemma. 

A more detailed description follows.
# Inspiration
The project is inspired by the research of **Robert Axelrod** , who used the iterated prisoner's dilemma to study the occurrence of altruistic behavior. The result of his study was that the most effective strategy in for this simulation was 
"tit for tat." An agent using this strategy will first cooperate, then subsequently replicate an opponent's previous action. If the opponent previously was cooperative, the agent is cooperative. If not, the agent is not.
# Files
#### Main files
Test teorii gier 3.6.ipynb - A program that runs a simulation in evolutionary game theory.

Wyniki_badania.xlsx - Example simulation result.

Całościowa analiza wyników.ipynb - A file used to analyze and visualisation simulation results.
#### Support files
Macierz sąsiedztwa.xlsx - A file to help design location neighborhood matrices.

Testy.ipynb and Test wydajności.ipynb - Files in which the computational efficiency of different solutions was compared (e.g., the speedup resulting from storing data in np.array instead of pd.DataFrame).
# Technology
Python 3.9.13

Pandas 1.4.4

Matplotlib 3.5.2

Numpy 1.21.5
# Description
The original Prisoner's Dilemma is a game in which there are two agents who can choose to cooperate or betray. If both cooperate they receive a lower sentence. If one betrays and the other keeps his allegiance, the former receives a lower 
sentence and the latter a higher sentence than if they both cooperated. If, on the other hand, they both betray, they both receive higher sentences than if they had cooperated.

The program runs a simulation based on the prisoner's dilemma, where individual agents gain points or lose them depending on the configuration in which they choose to cooperate or betray. The number of points agents receive or lose also depends
on the population density - the higher it is, the fewer points players gain or the greater number they lose. The scoring of each configuration:
1. Mutual cooperation: both agents receive F points.
2. Mutual betrayal: both agents receive F-11 points.
3. Unilateral betrayal: the traitor receives F+10 points, and the betrayed receives F-20 points.

The formula for the function of points:

F(Pop) = 10.05 - 0.0043Pop - 0.00000868Pop^2 - 0.000004Pop^3

The value of the function is rounded to 2 decimal places. The number of points determines the reproductive capacity of an individual.

In its current status, the program is able to test the performance of 24 strategies. Agents can plan their decision in advance, based on phenotype, close kinship, the number of points they have or the previous result of a previous game with 
a given agent. The game also features different locations and players can migrate between the 4 locations that appear. These are locations with "closed" borders, which simulates a situation where an area is isolated from others by natural 
barriers (such as mountains or deserts).
# Status of project
The project works and evolutionary game theory simulations can be performed with it. In the future I intend to improve it so that even more advanced simulations can be performed with it. In addition, I want to investigate the factors that 
contribute to the fact that existing simulation results mostly do not match the literature.In addition, I plan to test the possibility of creating a second version with a "fluid" location based on x, y coordinates instead of a location with 
"closed borders".
