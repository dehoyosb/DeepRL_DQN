## Report

### The Enviroment
In this implementation i used a Deep Q Network (DQN) to solve the bannana collector enviroment. The objective of the enviroment is to be used as a playground to train an agent that is capable of traveling through a world picking up yellow bananas and avoiding blue bannanas. Each time the agent picks up a yellow bannana a reward of +1 is provided, and each time the agent picks up a blue bannana a reard of -1 is provided aswell. In this manner, the objective of the agent is to pick up as many yellow bannanas as possible whilst avoiding the blue bannanas. The enviroment consist of a grid world of 37 states and contains the agents forward velocity, along a ray-based perception of objects around the agents forward direction. Additionally, the agent is only capable of choosing 4 discrete actions: Forward, Backward, turn left and turn right. The solving this enviroment is an episodic task, and is considered to be solved once the agent reaches and average score during 100 episodes of +13 or more

### The Learning Algorithm
To solve the enviroment i used the Deep Q Learning Algorithm. This algorithm has 2 important processes that work inside it. In the first one, the agent samples the enviroment by performing actions and stores away the different experience tuples in a replay memory. In the second one, the agent selects a random batch of experiences from the replay buffer and learns from it using a gradient descent step. Iterating over these 2 steps leads the agent to learn how to interact with the enviroment abstracting the optimal policy from the learned action value function.

### The Neural Network
The used Neural network is a 3 layer feed forward network with Relu activation between layers. Given that for this particular problem the input are not the raw pixels from the enviroment, rather the 37 states that contain the agents forward velocity, along a ray-based perception of objects around the agents forward direction, there was not need for the implementation of a convolutional neural network.

### The Hyperparameters
Buffer Size = 100000
Batch Size = 64
Gamma = 0.99
Tau = 0.001
Learning Rate = 0.0005

The target network was updated through the learning process, every 4 time steps if the memory buffer had at least the same ammount of experiences as the minimum batch size.

Number of Episodes = 2000
Max number of Steps per Episode = 1000
Epsilon Greedy with decay per episode = 0.995
Minimum Epsilon = 0.01
Starting Epsilon = 1

### Plot of Rewards per Episode
![Image of Reward PLot](https://github.com/dehoyosb/RL_Applications/tree/master/training_results/reward_plot.png)
![Image of Training Process](https://github.com/dehoyosb/RL_Applications/tree/master/training_results/training_process.png)


