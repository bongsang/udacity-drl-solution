[image1]: result.png
[image2]: https://youtu.be/yhdOoZNa1K8


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
- Noise Decay = OU Noise Decay Rate


# [SOLUTION] Bongsang's solution
## Hyperparameter tuned results
- gamma = 0.99
- tau = 1e-3 
- noise_decay = 1 + 5e-6

## Training logs result
- Episode 10	Average Score: 1.56
- Episode 20	Average Score: 1.19
- Episode 30	Average Score: 2.39
- Episode 40	Average Score: 2.58
- Episode 50	Average Score: 3.29
- Episode 60	Average Score: 5.13
- Episode 70	Average Score: 7.65
- Episode 80	Average Score: 9.348
- Episode 90	Average Score: 10.04
- Episode 100	Average Score: 13.56
- Episode 110	Average Score: 18.51
- Episode 120	Average Score: 21.44
- Episode 130	Average Score: 28.31
- Episode 132	Average Score: 30.14
- Solved! episodes = 132 	Average Score: 30.14


## Training Scores Graph result
![][image1]


## Realtime training visualization result
![][image2]
![](https://youtu.be/yhdOoZNa1K8)

# [Next] Next Study Plan
- ![Silver, et al. Deterministic Policy Gradients][http://jmlr.org/proceedings/papers/v32/silver14.pdf]
- ![Lillicrap, et al. Continuous control with Deep Reinforcement Learning][http://arxiv.org/pdf/1509.02971v2.pdf]



#### You can see full source code and run by yourself. The source is located in this folder.
#### Source code: Continuous_Control_final.ipynb

### Thank you
# Bongsang
