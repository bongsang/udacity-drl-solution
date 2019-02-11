# Deep Q-Network's architecture and its hyperparameters

## [Description] DQN overcomes unstable learning by mainly 2 techniques below:
- Experience Replay
- Target Network

### Experience Replay
Experience Replay is originally proposed in Reinforcement Learning for Robots Using Neural Networks in 1993. DNN is easily overfitting current episodes. Once DNN is overfitted, it’s hard to produce various experiences. To solve this problem, Experience Replay stores experiences including state transitions, rewards and actions, which are necessary data to perform Q learning, and makes mini-batches to update neural networks. This technique expects the following merits:
- reduces correlation between experiences in updating DNN
- increases learning speed with mini-batches
- reuses past transitions to avoid catastrophic forgetting

### Target Network
In TD error calculation, target function is changed frequently with DNN. Unstable target function makes training difficult. So Target Network technique fixes parameters of target function and replaces them with the latest network every thousands steps.

[image1]: https://cdn-images-1.medium.com/max/2000/1*Zplt-1wTWu_7BGmZCBFjbQ.png
![][image1]

Using the Bellman equation,the TD target is just the reward of taking that action at that state plus the discounted highest Q value for the next state.
[image2]: https://cdn-images-1.medium.com/max/1600/1*KsQ46R8zyTQlKGv91xi6ww.png
![][image2]

At every Tau step, the parameters are copied from our DQN network to update the target network.
[image3]: https://cdn-images-1.medium.com/max/2000/1*D9i0I2EO7LKL2aAb2HLfTg.png 
![][image3]


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
