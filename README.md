# RL-Project
OPTIMIZING ROBOT NAVIGATION IN DYNAMIC ENVIRONMENTS
Robot Navigation Simulation
## Project Overview
This project, conducted from March 2024 to May 2024, focuses on optimizing robot navigation in dynamic environments using Reinforcement Learning techniques. We developed a realistic 10x10 continuous space simulation using RVO2 for effective path planning and collision avoidance.
## Key Features
Realistic 10x10 continuous space simulation
RVO2 implementation for path planning and collision avoidance
ORCA policy for human movement simulation
DQN with Prioritized Experience Replay (PER) implementation
Advantage Actor-Critic (A2C) implementation
51% success rate in autonomous navigation in dynamic, human-populated environments
## Environment
### Environment Visualization
![image](https://github.com/user-attachments/assets/07d3c6ff-80dd-44a3-95ed-feb9440fd2a9)
Our simulation features a 2D 10x10 continuous space environment where:
* The robot (agent) is represented by a red circle
* Humans are represented by blue circles
* The robot's goal is marked by a golden star
The environment is designed to be stochastic, with humans spawning at random locations and moving towards random goal points.
## Observation Space
The observation space includes the collective state of all agents (robot and humans), containing:
- Robot's position (x, y)
- Robot's goal position (x, y)
- Robot's velocity (vx, vy)
- For each human: position (x, y), goal position (x, y), and velocity (vx, vy)
## Action Space
The action space is discrete, consisting of nine possible actions:
- Stop moving
- Move Right
- Move Up
- Move Left
- Move Down
- Move Up-Right (Diagonal)
- Move Up-Left (Diagonal)
- Move Down-Right (Diagonal)
- Move Down-Left (Diagonal)
- Reward System
- Collision penalty: -20 (episode ends)
- Goal reached: +500 (episode ends)
- Risk of collision: -10
- Default reward: -1 * Euclidean distance between initial and final positions
## Algorithms Used
### DQN with Prioritized Experience Replay (PER)
![image](https://github.com/user-attachments/assets/ec1e2c87-486e-4c34-9a91-10bf743560ba)

Deep Q-Network (DQN) with Prioritized Experience Replay is an advanced reinforcement learning algorithm that combines deep neural networks with Q-learning and prioritized sampling of experiences.

**Pros:**
Improved sample efficiency
Better handling of rare but important experiences
Faster convergence in many environments
**Cons:**
Increased computational complexity
Potential for over-fitting to high-priority experiences
Requires careful tuning of hyperparameters

### Advantage Actor-Critic (A2C)
![image](https://github.com/user-attachments/assets/5c00110c-1936-4003-8256-30c5ac524c88)

A2C is a policy gradient method that uses an actor-critic architecture to simultaneously learn a policy and a value function.
**Pros:**
More stable learning compared to pure policy gradient methods
Can handle continuous action spaces
Generally more sample efficient than value-based methods
**Cons:**
Can be sensitive to hyperparameter choices
May converge to suboptimal policies in some environments
Requires careful balancing of actor and critic learning rates

## Results
**DQN with PER Results:**
![image](https://github.com/user-attachments/assets/7def95a7-b5f2-414b-95b2-f5bd037bd21e)
![image](https://github.com/user-attachments/assets/f9cea5a9-8a2e-4ea5-8e4f-e1fd77e11752)

**A2C Results:**
![image](https://github.com/user-attachments/assets/39ef184b-2854-400a-9097-90e71c3d0b18)
![image](https://github.com/user-attachments/assets/1885b39f-288a-481c-ab1e-c24e7f6bb79f)


***Our experiments showed that DQN with PER outperformed A2C in this specific environment, achieving a 51% success rate in reaching the final position during testing.***

## Challenges and Future Work
- Implementing multiple algorithms was necessary due to the stochastic nature of the environment.
- The current implementation relies on obstacle positions for basic awareness. Future work could incorporate sensor data for enhanced real-time feedback and adaptability.
- Extending the project to work on perception, path planning, and decision-making could increase complexity and improve performance.

## References
1. Chen, C., Liu, Y., Kreiss, S., & Alahi, A. (2018). Crowd-Robot Interaction: Crowd-aware Robot Navigation with Attention-based Deep Reinforcement Learning. ArXiv. https://arxiv.org/abs/1809.08835
2. Zhou, S., Fu, H., He, H., & Liu, W. (2023). Robot Crowd Navigation in Dynamic Environment with Offline Reinforcement Learning. ArXiv. https://arxiv.org/abs/2312.11032
3. Escudie, E., Matignon, L., & Saraydaryan, J. (2024). Attention Graph for Multi-Robot Social Navigation with Deep Reinforcement Learning. ArXiv. https://arxiv.org/abs/2401.17914
4. Zhou, Z., Zhu, P., Zeng, Z. et al. Robot navigation in a crowd by integrating deep reinforcement learning and online planning. Appl Intell 52, 15600–15616 (2022). https://doi.org/10.1007/s10489-022-03191-2
5. @inproceedings{chen2019crowd,
  title={Crowd-robot interaction: Crowd-aware robot navigation with attention-based deep reinforcement learning},
  author={Chen, Changan and Liu, Yuejiang and Kreiss, Sven and Alahi, Alexandre},
  booktitle={2019 International Conference on Robotics and Automation (ICRA)},
  pages={6015--6022},
  year={2019},
  organization={IEEE}
}
6. @inproceedings{liu2022intention,
  title={Intention Aware Robot Crowd Navigation with Attention-Based Interaction Graph},
  author={Liu, Shuijing and Chang, Peixin and Huang, Zhe and Chakraborty, Neeloy and Hong, Kaiwen and Liang, Weihang and Livingston McPherson, D. and Geng, Junyi and Driggs-Campbell, Katherine},
  booktitle={IEEE International Conference on Robotics and Automation (ICRA)},
  year={2023},
  pages={12015-12021}
}

@inproceedings{liu2020decentralized,
  title={Decentralized Structural-RNN for Robot Crowd Navigation with Deep Reinforcement Learning},
  author={Liu, Shuijing and Chang, Peixin and Liang, Weihang and Chakraborty, Neeloy and Driggs-Campbell, Katherine},
  booktitle={IEEE International Conference on Robotics and Automation (ICRA)},
  year={2021},
  pages={3517-3524}
}

## Contributors
* Hariharan Venkatraman
* Eshwanth Dhanichetty Gopichandran
* Roopesh Vinodh Kumar Lal
