# Learning to play Pong with Deep Reinforcement Learning

## Description

Traditionally, reinforcement learning has operated on "tabular" state spaces, e.g. "State 1", "State 2", "State 3" etc. However, many important and interesting reinforcement learning problems (like moving robot arms or playing Atari games) are based on either continuous or very high-dimensional state spaces (like robot joint angles or pixels). Deep neural networks constitute one method for learning a value function or policy from continuous and high-dimensional observations. 

This project teachs an agent to play the game [Pong](https://pygame-learning-environment.readthedocs.io/en/latest/user/games/pong.html) from the PyGame Learning Environment. While it is possible to learn the task directly from screen pixel values as done by DQN on the Atari games, here we consider a simpler low-dimensional state space. The agent needs to control a paddle to hit a ball and drive it past it's opponent's paddle which is controlled by the computer. The state space is 7-dimensional and continuous, and consists of the following state variables:
- player paddle's y position.
- player paddle's velocity.
- cpu paddle's y position.
- ball's x position.
- ball's y position.
- ball's x velocity.
- ball's y velocity.

The agent can take one of two actions, accelerate up or accelerate down. The agent gets a reward of +1 when it scores a point, i.e, when it drives the ball past the computer-controlled paddle, and a reward of -1 when it loses a point. We define a game (or episode) to be over when either the agent (or the computer) scores 7 points, after which a new game is started. Because the episodes become very long once the agent learns to compete with its opponent, we stop training when the agent wins a certain number of games in a row (20 by default). You can change this parameter if you wish to further train and improve your agent.

The agent uses Policy Gradient approaches to learn the task. In supervised learning tasks, the network generates a probability distribution over the outputs, and is trained to maximize the probability of a specific target output given an observation. In Policy Gradient methods, the network generates a probability distribution over actions, and is trained to maximize expected future rewards given an observation.

### Run environement : 

- You will also need to install [Pygame](https://www.pygame.org/wiki/about), Pillow, and the [PyGame Learning Environment](https://pygame-learning-environment.readthedocs.io/en/latest/user/home.html). To do so, the easiest workflow to follow is:
    - source activate ann_env
    - pip3 install Pillow
    - pip3 install pygame
    - git clone https://github.com/ntasfi/PyGame-Learning-Environment
    - cd PyGame-Learning-Environment
    - pip3 install -e .

