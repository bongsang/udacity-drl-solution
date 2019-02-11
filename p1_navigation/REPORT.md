[image1]: https://cdn-images-1.medium.com/max/2000/1*Zplt-1wTWu_7BGmZCBFjbQ.png
[image2]: https://cdn-images-1.medium.com/max/2000/1*D9i0I2EO7LKL2aAb2HLfTg.png
[image3]: result/scores_graph.png
[image4]: result/navigation_solution_bongsang.gif


# [Description] Deep Q-Network's architecture and its hyperparameters

## DQN description: DQN overcomes unstable learning by mainly 2 techniques.
- Experience Replay
- Target Network

### Experience Replay
Experience Replay is originally proposed in Reinforcement Learning for Robots Using Neural Networks in 1993. DNN is easily overfitting current episodes. Once DNN is overfitted, it’s hard to produce various experiences. To solve this problem, Experience Replay stores experiences including state transitions, rewards and actions, which are necessary data to perform Q learning, and makes mini-batches to update neural networks. This technique expects the following merits:
- reduces correlation between experiences in updating DNN
- increases learning speed with mini-batches
- reuses past transitions to avoid catastrophic forgetting

### Target Network
In TD error calculation, target function is changed frequently with DNN. Unstable target function makes training difficult. So Target Network technique fixes parameters of target function and replaces them with the latest network every thousands steps.
![][image1]

Using the Bellman equation,the TD target is just the reward of taking that action at that state plus the discounted highest Q value for the next state.

At every Tau step, the parameters are copied from our DQN network to update the target network.
![][image2]


## DQN Hyperparameters Description
- Number of Episodes: Total episodes in Training

- Number of Steps: Total time steps in each episode

- Start value of Epsilon: Starting epsilon greedy, 1.0 means full random search

- Start value of Epsilon: Minimum epsilon greedy

- Epsilon Decay: Decaying rate for episodes


# [SOLUTION] Bongsang's solution
## Hyperparameter tuned results
- n_episodes=10000
- n_steps=1000
- eps_start=1.0
- eps_end=0.1
- eps_decay=0.993

## Training logs result
- episode = 50, average score =  0.36
- episode = 100, average score =  1.18
- episode = 150, average score =  3.34
- episode = 200, average score =  5.26
- episode = 250, average score =  6.69
- episode = 300, average score =  8.13
- episode = 350, average score =  9.42
- episode = 400, average score =  11.02
- episode = 450, average score =  12.35
- Navigation banana project is solved successfully. Episodes = 481, Average =  13.07


## Training Scores Graph result
![][image3]

## Realtime training visualization result
![][image4]

# [Next] Next Study Plan
- Playing Atari with Deep Reinforcement Learning, Mnih et al, 2013. Algorithm: DQN.
- Deep Recurrent Q-Learning for Partially Observable MDPs, Hausknecht and Stone, 2015. Algorithm: Deep Recurrent Q-Learning.
- Dueling Network Architectures for Deep Reinforcement Learning, Wang et al, 2015. Algorithm: Dueling DQN.
- Deep Reinforcement Learning with Double Q-learning, Hasselt et al 2015. Algorithm: Double DQN.
- Prioritized Experience Replay, Schaul et al, 2015. Algorithm: Prioritized Experience Replay (PER).
- Rainbow: Combining Improvements in Deep Reinforcement Learning, Hessel et al, 2017. Algorithm: Rainbow DQN.


#### You can see full source code and run by yourself. The source is located in this folder.
#### Source code: Navigation_Solution_Bongsang.ipynb

### Thank you
# Bongsang