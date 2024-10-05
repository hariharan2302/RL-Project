# RL-Project
OPTIMIZING ROBOT NAVIGATION IN DYNAMIC ENVIRONMENTS
Robot Navigation Simulation
## Project Overview
This project, conducted from March 2024 to May 2024, focuses on optimizing robot navigation in dynamic environments using Reinforcement Learning techniques. We developed a realistic 10x10 continuous space simulation using RVO2 for effective path planning and collision avoidance.
Key Features
Realistic 10x10 continuous space simulation
RVO2 implementation for path planning and collision avoidance
ORCA policy for human movement simulation
DQN with Prioritized Experience Replay (PER) implementation
Advantage Actor-Critic (A2C) implementation
51% success rate in autonomous navigation in dynamic, human-populated environments
Environment
Environment Visualization
Our simulation features a 2D 10x10 continuous space environment where:
The robot (agent) is represented by a red circle
Humans are represented by blue circles
The robot's goal is marked by a golden star
The environment is designed to be stochastic, with humans spawning at random locations and moving towards random goal points.
Observation Space
The observation space includes the collective state of all agents (robot and humans), containing:
Robot's position (x, y)
Robot's goal position (x, y)
Robot's velocity (vx, vy)
For each human: position (x, y), goal position (x, y), and velocity (vx, vy)
Action Space
The action space is discrete, consisting of nine possible actions:
Stop moving
Move Right
Move Up
Move Left
Move Down
Move Up-Right (Diagonal)
Move Up-Left (Diagonal)
Move Down-Right (Diagonal)
Move Down-Left (Diagonal)
Reward System
Collision penalty: -20 (episode ends)
Goal reached: +500 (episode ends)
Risk of collision: -10
Default reward: -1 * Euclidean distance between initial and final positions
Algorithms Used
DQN with Prioritized Experience Replay (PER)
Deep Q-Network (DQN) with Prioritized Experience Replay is an advanced reinforcement learning algorithm that combines deep neural networks with Q-learning and prioritized sampling of experiences.
Pros:
Improved sample efficiency
Better handling of rare but important experiences
Faster convergence in many environments
Cons:
Increased computational complexity
Potential for over-fitting to high-priority experiences
Requires careful tuning of hyperparameters
Advantage Actor-Critic (A2C)
A2C is a policy gradient method that uses an actor-critic architecture to simultaneously learn a policy and a value function.
Pros:
More stable learning compared to pure policy gradient methods
Can handle continuous action spaces
Generally more sample efficient than value-based methods
Cons:
Can be sensitive to hyperparameter choices
May converge to suboptimal policies in some environments
Requires careful balancing of actor and critic learning rates
Results
DQN with PER Results
A2C Results
Our experiments showed that DQN with PER outperformed A2C in this specific environment, achieving a 51% success rate in reaching the final position during testing.
Challenges and Future Work
Implementing multiple algorithms was necessary due to the stochastic nature of the environment.
The current implementation relies on obstacle positions for basic awareness. Future work could incorporate sensor data for enhanced real-time feedback and adaptability.
Extending the project to work on perception, path planning, and decision-making could increase complexity and improve performance.
References
Crowd-Robot Interaction: Crowd-aware Robot Navigation with Attention-based Deep Reinforcement Learning
Reinforcement Learning for Robot Navigation in Dynamic Environments: A Comprehensive Review
A Survey on Deep Reinforcement Learning for Mobile Robot Navigation
A comprehensive review of deep reinforcement learning for robot navigation
CrowdNav GitHub Repository
CrowdNav Prediction AttnGraph GitHub Repository
Contributors
Hariharan Venkatraman
Eshwanth Dhanichetty Gopichandran
Roopesh Vinodh Kumar Lal
