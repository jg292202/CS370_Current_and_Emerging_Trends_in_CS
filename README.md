# Pirate Intelligent Agent | Deep Q-Learning

**Python • TensorFlow/Keras • Deep Q-Learning • Reinforcement Learning • Neural Networks • Jupyter Notebook**

A reinforcement-learning project in which an intelligent agent learns to navigate an 8x8 maze and reach a target through repeated interaction, exploration, experience replay, and neural-network training.

This project was completed as part of **CS 370: Current and Emerging Trends in Computer Science** at Southern New Hampshire University.

## Project Overview

The project uses a pirate-themed treasure hunt to demonstrate Deep Q-Learning. Rather than following a predefined route, the intelligent agent interacts with the maze, receives rewards and penalties for its actions, and gradually learns behavior that allows it to reach the treasure.

The course provided the maze environment, experience-management framework, neural-network starter structure, and a skeleton for the Q-training algorithm. My primary responsibility was completing and refining the reinforcement-learning logic used to train and validate the agent.

## My Implementation

My work focused on the Deep Q-Learning training process, including:

- Implementing the Q-training control loop
- Selecting random starting positions for training episodes
- Implementing epsilon-greedy exploration and exploitation
- Integrating experience replay into the training process
- Selecting actions using predicted Q-values
- Tracking wins, losses, training loss, and rolling win rate
- Training the Q-network from replayed experiences
- Implementing epsilon decay as training progressed
- Synchronizing a target network with the primary network
- Adding completion-based early stopping
- Adjusting model architecture and training parameters to improve learning behavior

## Reinforcement-Learning Approach

### Exploration vs. Exploitation

The training process uses an **epsilon-greedy strategy** to balance exploration and exploitation.

During exploration, the agent selects from valid actions to discover new paths through the environment. During exploitation, the agent uses predicted Q-values from the trained model to select the action with the highest expected value.

Training begins with a high exploration rate. Epsilon gradually decreases as the agent accumulates experience, allowing learned behavior to play a larger role in future decisions.

### Experience Replay

Each interaction produces an experience containing the previous state, selected action, reward, resulting state, and game status.

The training loop stores these experiences through the provided `GameExperience` framework and retrieves batches of previous experiences for subsequent model updates. Integrating replayed experiences into training allows the network to learn from prior interactions rather than relying only on the most recent transition.

### Target Network

I incorporated a separate target network by cloning the primary model and periodically synchronizing its weights with the actively trained network.

This provided a separate network for the experience-management framework while the primary Q-network continued to train.

### Neural-Network and Training Adjustments

During development, I experimented with the model and training configuration to improve convergence and stability.

Adjustments included:

- Adding an additional hidden layer
- Increasing the size of the intermediate layer
- Using the Adam optimizer
- Lowering the learning rate to `0.0005`
- Adjusting replay-memory and batch-size parameters
- Periodically updating the target network
- Reducing the maximum number of training epochs for a more practical runtime in the course environment

These changes gave me an opportunity to evaluate how model architecture and training parameters affect reinforcement-learning behavior.

## Validation and Results

Success was evaluated using more than a single successful run through the maze.

The training loop tracks a rolling win rate and uses a completion check that evaluates the trained model from available starting positions within the environment. Training stops only when the rolling win rate reaches the required threshold and the model successfully passes that completion validation.

In the final recorded training run, the model satisfied the stopping condition at:

**Epoch 278**

The complete training run finished in approximately:

**8.79 minutes**

The recorded training output shows the win rate progressing from near zero during early exploration to the successful stopping condition as the agent increasingly relied on learned behavior.

This demonstrated that the trained model could satisfy the validation criteria established by the project rather than merely succeeding during a single favorable episode.

## Provided Framework vs. My Contribution

To accurately represent the scope of my work, the project included both course-provided starter components and code that I implemented or enhanced.

### Provided Starter Framework

The course provided:

- `TreasureMaze` environment
- `GameExperience` experience-management framework
- Maze and game setup
- Neural-network starter structure
- Q-training skeleton, requirements, and pseudocode

### Implemented or Enhanced by Me

My work included:

- Deep Q-Learning training loop
- Epsilon-greedy action-selection logic
- Experience-replay integration
- Training and loss tracking
- Win/loss and rolling win-rate tracking
- Epsilon-decay behavior
- Target-network creation and synchronization
- Completion-based early stopping
- Neural-network architecture adjustments
- Learning-rate tuning
- Training and replay-memory parameter adjustments

This distinction is intentional so the repository clearly represents my contribution to the completed project.

## Engineering Takeaways

One of the most useful aspects of this project was seeing how an intelligent system improves through repeated feedback rather than following an explicitly programmed solution.

The project reinforced several concepts that extend beyond reinforcement learning:

1. Understand the system and its constraints.
2. Define measurable criteria for successful behavior.
3. Observe how the system behaves.
4. Test changes rather than assuming they improve the result.
5. Adjust parameters and architecture deliberately.
6. Validate the final behavior against more than a single successful case.

It also introduced broader considerations around responsible AI. Reward design, training behavior, and validation criteria all influence the behavior a learning system ultimately develops, making testing and human oversight important parts of intelligent-system development.

## Technologies & Concepts

- Python
- TensorFlow / Keras
- NumPy
- Jupyter Notebook
- Reinforcement Learning
- Deep Q-Learning
- Neural Networks
- Experience Replay
- Epsilon-Greedy Exploration
- Target Networks
- Machine Learning
- Model Training and Validation

## Repository Contents

- `Glista_Joseph_ProjectTwo.ipynb` - Deep Q-Learning implementation, training process, validation, results, and analysis

## Academic Context

Completed as part of **CS 370: Current and Emerging Trends in Computer Science** at Southern New Hampshire University.

This repository is presented as a portfolio artifact demonstrating my implementation and refinement of Deep Q-Learning training logic within a provided intelligent-agent framework.
