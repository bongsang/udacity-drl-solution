[image1]: result.png

# [Description] DDPG's architecture and its hyperparameters
Deep Deterministic Policy Gradient (DDPG) is an algorithm which concurrently learns a Q-function and a policy. 
It uses off-policy data and the Bellman equation to learn the Q-function, and uses the Q-function to learn the policy.
This approach is closely connected to Q-learning, and is motivated the same way.
- DDPG is an off-policy algorithm.
- DDPG can be thought of as being deep Q-learning for continuous action spaces.

DDPG trains a deterministic policy in an off-policy way. Because the policy is deterministic, if the agent were to explore on-policy, in the beginning it would probably not try a wide enough variety of actions to find useful learning signals. 
To make DDPG policies explore better, we add noise to their actions at training time. The authors of the original DDPG paper recommended time-correlated OU noise, but more recent results suggest that uncorrelated, mean-zero Gaussian noise works perfectly well. Since the latter is simpler, it is preferred.


## DDPG Hyperparameters Description
- gamma: Discount factor
- tau: Soft update rate of target parameters
- Ornstein-Uhlenbeck noise parameter

# [SOLUTION] Bongsang's solution
## Hyperparameter tuned results
- GAMMA = 0.99            # discount factor
- TAU = 7e-2              # for soft update of target parameters
- OU_SIGMA = 0.2          # Ornstein-Uhlenbeck noise, volatility
- OU_THETA = 0.12         # Ornstein-Uhlenbeck noise, speed of mean reversion

## Training logs result
- Episodes 10	Max Reward: 0.100	Moving Average: 0.010
- Episodes 20	Max Reward: 0.000	Moving Average: 0.005
- Episodes 30	Max Reward: 0.000	Moving Average: 0.003
- Episodes 40	Max Reward: 0.000	Moving Average: 0.003
- Episodes 50	Max Reward: 0.000	Moving Average: 0.002
- Episodes 60	Max Reward: 0.000	Moving Average: 0.002
- Episodes 70	Max Reward: 0.100	Moving Average: 0.004
- Episodes 80	Max Reward: 0.100	Moving Average: 0.005
- Episodes 90	Max Reward: 0.100	Moving Average: 0.009
- Episodes 100	Max Reward: 0.100	Moving Average: 0.012
- Episodes 110	Max Reward: 0.100	Moving Average: 0.013
- Episodes 120	Max Reward: 0.100	Moving Average: 0.015
- Episodes 130	Max Reward: 0.100	Moving Average: 0.017
- Episodes 140	Max Reward: 0.200	Moving Average: 0.022
- Episodes 150	Max Reward: 0.000	Moving Average: 0.022
- Episodes 160	Max Reward: 0.100	Moving Average: 0.023
- Episodes 170	Max Reward: 0.100	Moving Average: 0.026
- Episodes 180	Max Reward: 0.100	Moving Average: 0.027
- Episodes 190	Max Reward: 0.200	Moving Average: 0.030
- Episodes 200	Max Reward: 0.100	Moving Average: 0.029
- Episodes 210	Max Reward: 0.200	Moving Average: 0.034
- Episodes 220	Max Reward: 0.100	Moving Average: 0.039
- Episodes 230	Max Reward: 0.100	Moving Average: 0.042
- Episodes 240	Max Reward: 0.100	Moving Average: 0.040
- Episodes 250	Max Reward: 0.100	Moving Average: 0.044
- Episodes 260	Max Reward: 0.100	Moving Average: 0.048
- Episodes 270	Max Reward: 0.100	Moving Average: 0.047
- Episodes 280	Max Reward: 0.100	Moving Average: 0.051
- Episodes 290	Max Reward: 0.200	Moving Average: 0.052
- Episodes 300	Max Reward: 0.200	Moving Average: 0.058
- Episodes 310	Max Reward: 0.200	Moving Average: 0.057
- Episodes 320	Max Reward: 0.200	Moving Average: 0.054
- Episodes 330	Max Reward: 0.100	Moving Average: 0.051
- Episodes 340	Max Reward: 0.200	Moving Average: 0.053
- Episodes 350	Max Reward: 0.100	Moving Average: 0.055
- Episodes 360	Max Reward: 0.200	Moving Average: 0.055
- Episodes 370	Max Reward: 0.200	Moving Average: 0.055
- Episodes 380	Max Reward: 0.200	Moving Average: 0.057
- Episodes 390	Max Reward: 0.300	Moving Average: 0.063
- Episodes 400	Max Reward: 0.100	Moving Average: 0.058
- Episodes 410	Max Reward: 0.200	Moving Average: 0.062
- Episodes 420	Max Reward: 0.300	Moving Average: 0.072
- Episodes 430	Max Reward: 0.300	Moving Average: 0.078
- Episodes 440	Max Reward: 0.200	Moving Average: 0.079
- Episodes 450	Max Reward: 0.200	Moving Average: 0.087
- Episodes 460	Max Reward: 0.300	Moving Average: 0.095
- Episodes 470	Max Reward: 0.300	Moving Average: 0.100
- Episodes 480	Max Reward: 0.200	Moving Average: 0.103
- Episodes 490	Max Reward: 0.300	Moving Average: 0.099
- Episodes 500	Max Reward: 0.300	Moving Average: 0.107
- Episodes 510	Max Reward: 0.300	Moving Average: 0.109
- Episodes 520	Max Reward: 0.200	Moving Average: 0.103
- Episodes 530	Max Reward: 0.200	Moving Average: 0.104
- Episodes 540	Max Reward: 0.200	Moving Average: 0.112
- Episodes 550	Max Reward: 0.400	Moving Average: 0.111
- Episodes 560	Max Reward: 0.900	Moving Average: 0.132
- Episodes 570	Max Reward: 0.100	Moving Average: 0.130
- Episodes 580	Max Reward: 0.200	Moving Average: 0.125
- Episodes 590	Max Reward: 0.300	Moving Average: 0.126
- Episodes 600	Max Reward: 0.600	Moving Average: 0.133
- Episodes 610	Max Reward: 0.100	Moving Average: 0.126
- Episodes 620	Max Reward: 0.500	Moving Average: 0.128
- Episodes 630	Max Reward: 0.300	Moving Average: 0.129
- Episodes 640	Max Reward: 0.400	Moving Average: 0.125
- Episodes 650	Max Reward: 0.500	Moving Average: 0.128
- Episodes 660	Max Reward: 0.600	Moving Average: 0.114
- Episodes 670	Max Reward: 0.800	Moving Average: 0.125
- Episodes 680	Max Reward: 0.700	Moving Average: 0.158
- Episodes 690	Max Reward: 2.300	Moving Average: 0.205
- Episodes 700	Max Reward: 1.900	Moving Average: 0.214
- Episodes 710	Max Reward: 2.600	Moving Average: 0.258
- Episodes 720	Max Reward: 3.100	Moving Average: 0.305
- Episodes 730	Max Reward: 1.800	Moving Average: 0.376
- Episodes 740	Max Reward: 2.800	Moving Average: 0.417
- Episodes 750	Max Reward: 2.200	Moving Average: 0.438
- Episodes 760	Max Reward: 4.500	Moving Average: 0.468
- Solved in 668 episodes!                 


## Training Scores Graph result
![][image1]

# [Next] Next Study Plan
- ![Deep Deterministic Policy Gradients in TensorFlow][https://pemami4911.github.io/blog/2016/08/21/ddpg-rl.html]
- ![Silver, et al. Deterministic Policy Gradients][http://jmlr.org/proceedings/papers/v32/silver14.pdf]
- ![Lillicrap, et al. Continuous control with Deep Reinforcement Learning][http://arxiv.org/pdf/1509.02971v2.pdf]


### Thank you
# Bongsang
