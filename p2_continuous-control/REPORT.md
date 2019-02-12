[image1]: https://cdn-images-1.medium.com/max/2000/1*Zplt-1wTWu_7BGmZCBFjbQ.png
[image2]: https://cdn-images-1.medium.com/max/2000/1*D9i0I2EO7LKL2aAb2HLfTg.png
[image3]: result/scores_graph.png
[image4]: result/navigation_solution_bongsang.gif


# [Description] DDPG's architecture and its hyperparameters
Deep Deterministic Policy Gradient (DDPG) is an algorithm which concurrently learns a Q-function and a policy. It uses off-policy data and the Bellman equation to learn the Q-function, and uses the Q-function to learn the policy.
This approach is closely connected to Q-learning, and is motivated the same way.
- DDPG is an off-policy algorithm.
- DDPG can be thought of as being deep Q-learning for continuous action spaces.

DDPG trains a deterministic policy in an off-policy way. Because the policy is deterministic, if the agent were to explore on-policy, in the beginning it would probably not try a wide enough variety of actions to find useful learning signals. To make DDPG policies explore better, we add noise to their actions at training time. The authors of the original DDPG paper recommended time-correlated OU noise, but more recent results suggest that uncorrelated, mean-zero Gaussian noise works perfectly well. Since the latter is simpler, it is preferred. To facilitate getting higher-quality training data, you may reduce the scale of the noise over the course of training.


## DDPG Hyperparameters Description
- gamma: Discount factor
- tau: Soft update rate of target parameters
- Noise Decay = OU Noise Decay Rate


# [SOLUTION] Bongsang's solution
## Hyperparameter tuned results
- gamma = 0.99
- tau = 1e-3 
- noise_decay = 1 + 5e-6

## Training logs result
- Average score over 100 episodes: 8.99	Best score: 25.419999431818724
- Average score over 100 episodes: 28.31	Best score: 37.83999915421009
- Episode 226,	Scores: 31.51,	 Average scores: 27.55


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