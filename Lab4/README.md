# Reinforcement Learning to improve agent's reward on popular ATARI games

## App Description 

The main purpose of this excerise, was to make computer capable of human-level performance on a classic Atari 2600 game "MsPacman". Just like a human, the algorithm played based on its vision of the screen. Starting from scratch, 
it discovered gameplay strategies that let it meet (and in many cases, exceed) human benchmarks.

## Different Environments 

This game was studed in three different environments:

1. Deterministic: Fixed Frameskip of 4
2. NoFrameskip: No frame skip and no action repeat stochasticity
3. Empty: Frameskip is sampled from (2,5)

Each of these could be either v0 or v4:

* v0: It has repeat_action_probability of 0.25 (meaning 25% of the time the previous action will be used instead of the new action)
* v4: It has 0 repeat_action_probability (always follow your issued action)

Of course, each environment defines a different problem (total 6) we want to optimize.

## Different algorithms

We compare three different algorithms:

1.Deep Q-Network (DQN)
2.Policy Optimization (PPO)
3.Actor Critic (A2C)

## Optimizing

We come to the conclusion that DQN algorithm is suitable for our game, despite the environment. Using TensorBoard, we found best parameters of dqn_model. As an example,
we visualized the learning performance of DQN using MLP policy (blue color) and CNN policy (red color):

![111](https://user-images.githubusercontent.com/50829499/111368954-25617c80-869f-11eb-8e24-582fc54db4c6.png)

## Final Results

Finally, the agent's perforamnce after hours of training with optimized DQN:

To watch this video, click here: [Best Computer's performance to MSPacman](https://user-images.githubusercontent.com/50829499/111369399-b0db0d80-869f-11eb-86d4-0bbc6b319cb5.mp4)


Score is around 4.000 (!) and it is really satisfactory since the agent learns to avoid monsters, collect all points and contiius to new stages. 



