[//]: # (Image References)

[image1]: https://user-images.githubusercontent.com/10624937/42135619-d90f2f28-7d12-11e8-8823-82b970a54d7e.gif "Trained Agent"

# Project 1: Navigation

### Introduction

For this project, you will train an agent to navigate (and collect bananas!) in a large, square world.  

![Trained Agent][image1]


# Deep Q-Network's architecture and its hyperparameters

DQN overcomes unstable learning by mainly 4 techniques.

- **1** Experience Replay
- **2** Target Network

## 1. Experience Replay
Experience Replay is originally proposed in Reinforcement Learning for Robots Using Neural Networks in 1993. DNN is easily overfitting current episodes. Once DNN is overfitted, it’s hard to produce various experiences. To solve this problem, Experience Replay stores experiences including state transitions, rewards and actions, which are necessary data to perform Q learning, and makes mini-batches to update neural networks. This technique expects the following merits.

- reduces correlation between experiences in updating DNN
- increases learning speed with mini-batches
- reuses past transitions to avoid catastrophic forgetting




### Solution and Result by Bongsang

You can use DQN to solve the problem.
After around 450 episodes DQN can be smart enough to avoid blue banana and to get yellow banana.
Below is a capture GIF traing algorithm:

#### Training
[train_image]: result/navigation_solution_bongsang.gif
![][train_image]


#### Scores Graph
[scores_graph]: result/scores_graph.png
![][scores_graph]

#### You can see full source code and run by yourself. The source is located in this folder.
#### Source code: p1_navigation/Navigation_Solution_Bongsang.ipynb

### Thank you
