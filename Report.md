# Project 1: Navigation
<p align="center">
<img src ="https://github.com/championballer/RL/raw/master/P1_Navigation/Navigation.gif">
<br>
<b> Solved Environment <b>
</p>

This report details the algorithm and implementation for the Navigation project of the Deep Reinforcement Learning Nanodegree on Udacity.

The environment was solved using the double DQN algorithm which involves the use of two networks namely target and local to map states to action values to improve reward using fixed targets methadology, while operating on a memory buffer to be able to sample different uncorrelated episodes to remove the bias that can get introduced in the agent's behaviour due to the correlation. The neural network takes place of the Q table which was handy in discrete state space in mapping states to action values. Double DQN is used here; which is an improvement over the normal DQN where the local network was used to select actions for future states, and those actions were used in the target network to estimate rewards. This is done to avoid over estimation. The rewards are high only if both networks of the agent agree on the actions being used. Else the rewards will be less. In the long run, the algorithm prevents the agent from propogating incidental high rewards that may be obtained by chance and do not reflect long term returns. 

On implementation side of things, Double DQN turned out to be more stable than classic DQN. The architecture for the neural networks is that of containing two hidden layers containing 128 and 64 units each. The activation function employed on each hidden layer is Exponential Linear Unit or ELU which was observed to give minutely better and more stable performance than ReLU. The output layer of the networks was normal output function to obtain action values corresponding to each possible action in the action space. 

<p align="center">
<img src ="https://github.com/championballer/P1_Navigation/raw/master/Images/SS1.png">
</p>