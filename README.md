# Pirate Intelligent Agent | Deep Q-Learning

**Python • Deep Q-Learning • Reinforcement Learning • Neural Networks • Jupyter Notebook**

Reinforcement-learning project in which an intelligent agent learns to navigate a grid-based environment and reach a target through repeated interaction, exploration, and training.

The project was completed as part of CS 370 Current and Emerging Trends in Computer Science at Southern New Hampshire University.

## Project Overview

The application uses a pirate-themed grid environment to demonstrate reinforcement learning. Rather than being given a fixed path to the goal, the agent learns from repeated experiences and gradually improves its navigation strategy.

A starter framework provided the environment setup, game loop, and neural-network structure.

My primary responsibility was implementing the **Q-training algorithm** that enabled the agent to learn.

## My Implementation

I completed the reinforcement-learning logic responsible for:

- Deep Q-Learning training
- Epsilon-greedy exploration and exploitation
- Experience replay
- Iterative model updates based on agent experiences
- Episode-based training
- Refining agent behavior through repeated feedback

The completed training process allowed the agent to learn a successful path to the target through repeated trial and error.

## Reinforcement-Learning Approach

The agent learns by interacting with the environment and using previous experiences to improve future decisions.

### Exploration vs. Exploitation

An epsilon-greedy strategy balances two behaviors:

- **Exploration** allows the agent to try different actions and discover new paths.
- **Exploitation** allows the agent to use what it has already learned to select stronger actions.

As training progresses, the balance can shift toward relying more heavily on learned behavior.

### Experience Replay

Previous agent experiences are retained and reused during training. Sampling prior experiences helps the model learn from more than just the agent's most recent action and supports iterative improvement of the Q-network.

## Results

Through repeated training episodes, the intelligent agent learned behavior that allowed it to successfully navigate the environment and reach the treasure.

The project demonstrated how reinforcement learning can improve decision-making through repeated interaction and feedback rather than requiring an explicitly programmed solution path.

## What I Learned

This project gave me hands-on experience implementing reinforcement-learning logic and helped connect concepts including neural networks, exploration versus exploitation, experience replay, and iterative model training.

It also reinforced an engineering approach I continue to use in other projects:

1. Understand the system and its constraints.
2. Break the problem into smaller components.
3. Observe system behavior.
4. Test and adjust the implementation.
5. Repeat until the system behaves as expected.

The project also introduced broader questions around responsible AI, particularly how reward design, training data, and model behavior can influence system outcomes.

## Project Scope

### Provided Starter Framework

- Grid-based environment
