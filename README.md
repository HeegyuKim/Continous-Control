[//]: # (Image References)

[image1]: https://user-images.githubusercontent.com/10624937/43851024-320ba930-9aff-11e8-8493-ee547c6af349.gif "Trained Agent"
[image2]: https://user-images.githubusercontent.com/10624937/43851646-d899bf20-9b00-11e8-858c-29b5c2c94ccc.png "Crawler"


# Project 2: Continuous Control

### Introduction

For this project, you will work with the [Reacher](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Learning-Environment-Examples.md#reacher) environment.

![Trained Agent][image1]

In this environment, a double-jointed arm can move to target locations. A reward of +0.1 is provided for each step that the agent's hand is in the goal location. Thus, the goal of your agent is to maintain its position at the target location for as many time steps as possible.

The observation space consists of 33 variables corresponding to position, rotation, velocity, and angular velocities of the arm. Each action is a vector with four numbers, corresponding to torque applicable to two joints. Every entry in the action vector should be a number between -1 and 1.

### Distributed Training

For this project, we will provide you with two separate versions of the Unity environment:
- The first version contains a single agent.
- The second version contains 20 identical agents, each with its own copy of the environment.  

The second version is useful for algorithms like [PPO](https://arxiv.org/pdf/1707.06347.pdf), [A3C](https://arxiv.org/pdf/1602.01783.pdf), and [D4PG](https://openreview.net/pdf?id=SyZipzbCb) that use multiple (non-interacting, parallel) copies of the same agent to distribute the task of gathering experience.  

### Solving the Environment

Note that your project submission need only solve one of the two versions of the environment. 

#### Option 1: Solve the First Version

The task is episodic, and in order to solve the environment,  your agent must get an average score of +30 over 100 consecutive episodes.

#### Option 2: Solve the Second Version

The barrier for solving the second version of the environment is slightly different, to take into account the presence of many agents.  In particular, your agents must get an average score of +30 (over 100 consecutive episodes, and over all agents).  Specifically,
- After each episode, we add up the rewards that each agent received (without discounting), to get a score for each agent.  This yields 20 (potentially different) scores.  We then take the average of these 20 scores. 
- This yields an **average score** for each episode (where the average is over all 20 agents).

The environment is considered solved, when the average (over 100 episodes) of those average scores is at least +30. 

### Getting Started

1. Download the environment from one of the links below.  You need only select the environment that matches your operating system:

    - **_Version 1: One (1) Agent_**
        - Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Linux.zip)
        - Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher.app.zip)
        - Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Windows_x86.zip)
        - Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Windows_x86_64.zip)

    - **_Version 2: Twenty (20) Agents_**
        - Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Linux.zip)
        - Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher.app.zip)
        - Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Windows_x86.zip)
        - Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Windows_x86_64.zip)
    
    (_For Windows users_) Check out [this link](https://support.microsoft.com/en-us/help/827218/how-to-determine-whether-a-computer-is-running-a-32-bit-version-or-64) if you need help with determining if your computer is running a 32-bit version or 64-bit version of the Windows operating system.

    (_For AWS_) If you'd like to train the agent on AWS (and have not [enabled a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md)), then please use [this link](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Linux_NoVis.zip) (version 1) or [this link](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Linux_NoVis.zip) (version 2) to obtain the "headless" version of the environment.  You will **not** be able to watch the agent without enabling a virtual screen, but you will be able to train the agent.  (_To watch the agent, you should follow the instructions to [enable a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md), and then download the environment for the **Linux** operating system above._)

2. Place the file in the DRLND GitHub repository, in the `p2_continuous-control/` folder, and unzip (or decompress) the file. 

### Instructions

Follow the instructions in `Report.ipynb` to get started with training your own agent!  

## Achievment
### 20-agent env training
total 102 episodes, achieve 30 average scores on recent 100 episodes!<br>
<img src="img/20agents.PNG"/>
actor-model: [ddpg-20agent-actor.pt](ddpg-20agent-actor.pt)<br>
critic-model: [ddpg-20agent-critic.pt](ddpg-20agent-critic.pt)

```
Episode 1	Total Average Score: 0.26	Mean: 0.26	Min: 0.00	Max: 0.69	Duration: 70.02
Episode 2	Total Average Score: 0.19	Mean: 0.12	Min: 0.00	Max: 0.66	Duration: 73.76
Episode 3	Total Average Score: 0.21	Mean: 0.26	Min: 0.00	Max: 0.75	Duration: 73.46
Episode 4	Total Average Score: 0.21	Mean: 0.20	Min: 0.00	Max: 0.72	Duration: 74.17
Episode 5	Total Average Score: 0.25	Mean: 0.42	Min: 0.00	Max: 1.03	Duration: 75.87
Episode 6	Total Average Score: 0.38	Mean: 1.05	Min: 0.15	Max: 1.86	Duration: 76.85
Episode 7	Total Average Score: 0.49	Mean: 1.12	Min: 0.40	Max: 1.91	Duration: 76.45
Episode 8	Total Average Score: 0.60	Mean: 1.39	Min: 0.30	Max: 2.70	Duration: 76.47
Episode 9	Total Average Score: 0.66	Mean: 1.09	Min: 0.24	Max: 2.11	Duration: 76.34
Episode 10	Total Average Score: 0.70	Mean: 1.15	Min: 0.27	Max: 2.02	Duration: 77.16
Episode 10	Total Average Score: 0.70
Episode 11	Total Average Score: 0.78	Mean: 1.54	Min: 0.42	Max: 2.66	Duration: 76.78
Episode 12	Total Average Score: 0.87	Mean: 1.85	Min: 0.81	Max: 3.32	Duration: 77.61
Episode 13	Total Average Score: 0.96	Mean: 2.10	Min: 0.36	Max: 3.94	Duration: 77.61
Episode 14	Total Average Score: 1.11	Mean: 2.97	Min: 0.97	Max: 4.95	Duration: 78.30
Episode 15	Total Average Score: 1.26	Mean: 3.45	Min: 0.47	Max: 7.03	Duration: 78.65
Episode 16	Total Average Score: 1.45	Mean: 4.25	Min: 0.85	Max: 7.40	Duration: 79.14
Episode 17	Total Average Score: 1.66	Mean: 5.01	Min: 1.95	Max: 7.01	Duration: 80.02
Episode 18	Total Average Score: 1.89	Mean: 5.78	Min: 1.86	Max: 9.09	Duration: 80.93
Episode 19	Total Average Score: 2.20	Mean: 7.78	Min: 3.24	Max: 12.45	Duration: 81.28
Episode 20	Total Average Score: 2.49	Mean: 7.97	Min: 2.44	Max: 13.52	Duration: 82.39
Episode 20	Total Average Score: 2.49
Episode 21	Total Average Score: 2.90	Mean: 11.21	Min: 5.45	Max: 16.34	Duration: 83.79
Episode 22	Total Average Score: 3.34	Mean: 12.42	Min: 2.51	Max: 21.58	Duration: 84.83
Episode 23	Total Average Score: 3.90	Mean: 16.37	Min: 9.14	Max: 30.48	Duration: 85.51
Episode 24	Total Average Score: 4.42	Mean: 16.36	Min: 6.04	Max: 26.13	Duration: 86.18
Episode 25	Total Average Score: 4.95	Mean: 17.50	Min: 9.74	Max: 25.99	Duration: 87.02
Episode 26	Total Average Score: 5.64	Mean: 23.06	Min: 12.45	Max: 33.42	Duration: 88.76
Episode 27	Total Average Score: 6.42	Mean: 26.63	Min: 13.74	Max: 36.90	Duration: 88.69
Episode 28	Total Average Score: 7.20	Mean: 28.40	Min: 19.12	Max: 39.16	Duration: 90.32
Episode 29	Total Average Score: 7.96	Mean: 29.01	Min: 23.73	Max: 37.61	Duration: 91.34
Episode 30	Total Average Score: 8.66	Mean: 29.04	Min: 19.72	Max: 37.26	Duration: 91.73
Episode 30	Total Average Score: 8.66
Episode 31	Total Average Score: 9.43	Mean: 32.61	Min: 25.11	Max: 38.76	Duration: 92.63
Episode 32	Total Average Score: 10.19	Mean: 33.72	Min: 28.20	Max: 38.67	Duration: 94.59
Episode 33	Total Average Score: 10.99	Mean: 36.67	Min: 32.48	Max: 39.22	Duration: 95.17
Episode 34	Total Average Score: 11.73	Mean: 36.16	Min: 30.93	Max: 39.62	Duration: 96.17
Episode 35	Total Average Score: 12.46	Mean: 37.01	Min: 32.83	Max: 39.22	Duration: 97.75
Episode 36	Total Average Score: 13.10	Mean: 35.83	Min: 29.88	Max: 38.59	Duration: 98.12
Episode 37	Total Average Score: 13.79	Mean: 38.60	Min: 36.41	Max: 39.54	Duration: 98.94
Episode 38	Total Average Score: 14.42	Mean: 37.41	Min: 34.95	Max: 38.80	Duration: 100.59
Episode 39	Total Average Score: 15.03	Mean: 38.44	Min: 36.95	Max: 39.39	Duration: 101.69
Episode 40	Total Average Score: 15.61	Mean: 38.09	Min: 36.37	Max: 39.56	Duration: 102.08
Episode 40	Total Average Score: 15.61
Episode 41	Total Average Score: 16.16	Mean: 38.42	Min: 36.36	Max: 39.61	Duration: 102.86
Episode 42	Total Average Score: 16.71	Mean: 38.89	Min: 38.11	Max: 39.53	Duration: 103.62
Episode 43	Total Average Score: 17.20	Mean: 37.77	Min: 36.33	Max: 38.97	Duration: 104.23
Episode 44	Total Average Score: 17.69	Mean: 38.95	Min: 37.57	Max: 39.53	Duration: 105.24
Episode 45	Total Average Score: 18.15	Mean: 38.37	Min: 34.96	Max: 39.51	Duration: 105.80
Episode 46	Total Average Score: 18.60	Mean: 38.99	Min: 37.35	Max: 39.62	Duration: 103.12
Episode 47	Total Average Score: 19.03	Mean: 38.91	Min: 37.94	Max: 39.58	Duration: 106.89
Episode 48	Total Average Score: 19.45	Mean: 38.78	Min: 35.99	Max: 39.54	Duration: 110.44
Episode 49	Total Average Score: 19.85	Mean: 39.34	Min: 37.77	Max: 39.62	Duration: 110.37
Episode 50	Total Average Score: 20.21	Mean: 37.81	Min: 36.62	Max: 39.09	Duration: 111.89
Episode 50	Total Average Score: 20.21
Episode 51	Total Average Score: 20.58	Mean: 39.06	Min: 37.79	Max: 39.64	Duration: 111.90
Episode 52	Total Average Score: 20.94	Mean: 39.43	Min: 38.90	Max: 39.60	Duration: 111.64
Episode 53	Total Average Score: 21.28	Mean: 38.69	Min: 37.38	Max: 39.64	Duration: 114.09
Episode 54	Total Average Score: 21.60	Mean: 38.81	Min: 37.76	Max: 39.48	Duration: 115.58
Episode 55	Total Average Score: 21.92	Mean: 39.01	Min: 38.12	Max: 39.63	Duration: 115.50
Episode 56	Total Average Score: 22.22	Mean: 38.99	Min: 36.39	Max: 39.58	Duration: 115.61
Episode 57	Total Average Score: 22.51	Mean: 38.77	Min: 36.83	Max: 39.59	Duration: 115.19
Episode 58	Total Average Score: 22.80	Mean: 39.11	Min: 38.02	Max: 39.56	Duration: 116.06
Episode 59	Total Average Score: 23.05	Mean: 37.36	Min: 35.93	Max: 38.99	Duration: 115.97
Episode 60	Total Average Score: 23.31	Mean: 38.66	Min: 36.48	Max: 39.62	Duration: 115.94
Episode 60	Total Average Score: 23.31
Episode 61	Total Average Score: 23.56	Mean: 38.88	Min: 37.99	Max: 39.56	Duration: 115.92
Episode 62	Total Average Score: 23.80	Mean: 38.57	Min: 37.58	Max: 39.49	Duration: 115.91
Episode 63	Total Average Score: 24.04	Mean: 38.77	Min: 37.84	Max: 39.55	Duration: 116.12
Episode 64	Total Average Score: 24.26	Mean: 37.70	Min: 35.88	Max: 39.06	Duration: 116.02
Episode 65	Total Average Score: 24.48	Mean: 39.02	Min: 38.07	Max: 39.54	Duration: 115.79
Episode 66	Total Average Score: 24.69	Mean: 38.35	Min: 36.97	Max: 39.51	Duration: 115.61
Episode 67	Total Average Score: 24.91	Mean: 39.12	Min: 38.24	Max: 39.53	Duration: 114.63
Episode 68	Total Average Score: 25.11	Mean: 38.82	Min: 37.91	Max: 39.45	Duration: 115.28
Episode 69	Total Average Score: 25.30	Mean: 38.34	Min: 37.12	Max: 39.51	Duration: 115.30
Episode 70	Total Average Score: 25.50	Mean: 39.21	Min: 38.76	Max: 39.61	Duration: 115.45
Episode 70	Total Average Score: 25.50
Episode 71	Total Average Score: 25.69	Mean: 38.83	Min: 37.54	Max: 39.41	Duration: 115.62
Episode 72	Total Average Score: 25.87	Mean: 38.65	Min: 37.52	Max: 39.33	Duration: 116.15
Episode 73	Total Average Score: 26.05	Mean: 38.70	Min: 36.63	Max: 39.65	Duration: 115.93
Episode 74	Total Average Score: 26.22	Mean: 39.14	Min: 38.31	Max: 39.65	Duration: 115.50
Episode 75	Total Average Score: 26.39	Mean: 38.75	Min: 37.45	Max: 39.50	Duration: 115.22
Episode 76	Total Average Score: 26.55	Mean: 38.87	Min: 37.85	Max: 39.49	Duration: 115.56
Episode 77	Total Average Score: 26.72	Mean: 39.25	Min: 38.55	Max: 39.58	Duration: 115.54
Episode 78	Total Average Score: 26.87	Mean: 38.48	Min: 36.12	Max: 39.49	Duration: 115.44
Episode 79	Total Average Score: 27.03	Mean: 39.09	Min: 36.85	Max: 39.57	Duration: 115.73
Episode 80	Total Average Score: 27.17	Mean: 38.80	Min: 37.66	Max: 39.64	Duration: 116.13
Episode 80	Total Average Score: 27.17
Episode 81	Total Average Score: 27.31	Mean: 38.51	Min: 37.00	Max: 39.34	Duration: 115.82
Episode 82	Total Average Score: 27.46	Mean: 39.03	Min: 37.87	Max: 39.60	Duration: 115.68
Episode 83	Total Average Score: 27.59	Mean: 38.67	Min: 36.72	Max: 39.62	Duration: 116.72
Episode 84	Total Average Score: 27.72	Mean: 38.46	Min: 37.20	Max: 39.36	Duration: 116.23
Episode 85	Total Average Score: 27.84	Mean: 37.76	Min: 36.03	Max: 39.25	Duration: 116.02
Episode 86	Total Average Score: 27.96	Mean: 38.29	Min: 36.64	Max: 39.60	Duration: 115.01
Episode 87	Total Average Score: 28.08	Mean: 38.64	Min: 36.80	Max: 39.65	Duration: 115.24
Episode 88	Total Average Score: 28.21	Mean: 38.94	Min: 37.86	Max: 39.61	Duration: 115.02
Episode 89	Total Average Score: 28.31	Mean: 37.75	Min: 34.16	Max: 39.32	Duration: 115.16
Episode 90	Total Average Score: 28.41	Mean: 37.11	Min: 34.94	Max: 38.36	Duration: 115.84
Episode 90	Total Average Score: 28.41
Episode 91	Total Average Score: 28.52	Mean: 38.05	Min: 35.55	Max: 39.49	Duration: 112.65
Episode 92	Total Average Score: 28.62	Mean: 37.81	Min: 34.65	Max: 39.54	Duration: 112.54
Episode 93	Total Average Score: 28.72	Mean: 37.82	Min: 35.81	Max: 39.61	Duration: 113.32
Episode 94	Total Average Score: 28.82	Mean: 38.38	Min: 36.62	Max: 39.51	Duration: 113.75
Episode 95	Total Average Score: 28.92	Mean: 38.59	Min: 37.44	Max: 39.63	Duration: 112.70
Episode 96	Total Average Score: 29.02	Mean: 38.47	Min: 36.68	Max: 39.56	Duration: 112.35
Episode 97	Total Average Score: 29.11	Mean: 37.53	Min: 35.69	Max: 39.10	Duration: 111.78
Episode 98	Total Average Score: 29.20	Mean: 37.62	Min: 35.94	Max: 39.18	Duration: 112.74
Episode 99	Total Average Score: 29.29	Mean: 38.24	Min: 36.62	Max: 39.57	Duration: 113.01
Episode 100	Total Average Score: 29.37	Mean: 37.24	Min: 34.45	Max: 39.22	Duration: 113.71
Episode 100	Total Average Score: 29.37
Episode 101	Total Average Score: 29.74	Mean: 37.60	Min: 35.15	Max: 38.93	Duration: 113.80
Episode 102	Total Average Score: 30.12	Mean: 37.59	Min: 35.12	Max: 39.16	Duration: 114.08
Problem Solved after 102 epsisodes!! Total Average score: 30.12
```

### 1-agent env training
total 385 episodes, achieve 30 average scores on recent 100 episodes!<br>
<img src="img/1agent.PNG"/>
actor-model: [ddpg-1agent-actor.pt](ddpg-20agent-actor.pt)<br>
critic-model: [ddpg-1agent-critic.pt](ddpg-20agent-critic.pt)

```
Episode 1	Total Average Score: 0.43	Mean: 0.43	Min: 0.43	Max: 0.43	Duration: 6.02
Episode 2	Total Average Score: 0.62	Mean: 0.81	Min: 0.81	Max: 0.81	Duration: 20.14
Episode 3	Total Average Score: 0.66	Mean: 0.75	Min: 0.75	Max: 0.75	Duration: 20.99
Episode 4	Total Average Score: 0.50	Mean: 0.00	Min: 0.00	Max: 0.00	Duration: 22.36
Episode 5	Total Average Score: 0.45	Mean: 0.27	Min: 0.27	Max: 0.27	Duration: 23.64
Episode 6	Total Average Score: 0.38	Mean: 0.00	Min: 0.00	Max: 0.00	Duration: 22.49
Episode 7	Total Average Score: 0.34	Mean: 0.12	Min: 0.12	Max: 0.12	Duration: 21.41
Episode 8	Total Average Score: 0.37	Mean: 0.56	Min: 0.56	Max: 0.56	Duration: 21.16
Episode 9	Total Average Score: 0.39	Mean: 0.56	Min: 0.56	Max: 0.56	Duration: 21.16
Episode 10	Total Average Score: 0.45	Mean: 1.04	Min: 1.04	Max: 1.04	Duration: 21.70
Episode 10	Total Average Score: 0.45
Episode 11	Total Average Score: 0.49	Mean: 0.80	Min: 0.80	Max: 0.80	Duration: 22.05
Episode 12	Total Average Score: 0.55	Mean: 1.23	Min: 1.23	Max: 1.23	Duration: 21.65
Episode 13	Total Average Score: 0.67	Mean: 2.09	Min: 2.09	Max: 2.09	Duration: 21.33
Episode 14	Total Average Score: 0.72	Mean: 1.48	Min: 1.48	Max: 1.48	Duration: 21.57
Episode 15	Total Average Score: 0.70	Mean: 0.30	Min: 0.30	Max: 0.30	Duration: 23.35
Episode 16	Total Average Score: 0.71	Mean: 0.93	Min: 0.93	Max: 0.93	Duration: 22.99
Episode 17	Total Average Score: 0.72	Mean: 0.94	Min: 0.94	Max: 0.94	Duration: 21.53
Episode 18	Total Average Score: 0.75	Mean: 1.18	Min: 1.18	Max: 1.18	Duration: 21.61
Episode 19	Total Average Score: 0.79	Mean: 1.47	Min: 1.47	Max: 1.47	Duration: 22.39
Episode 20	Total Average Score: 0.81	Mean: 1.32	Min: 1.32	Max: 1.32	Duration: 21.50
Episode 20	Total Average Score: 0.81
Episode 21	Total Average Score: 0.86	Mean: 1.83	Min: 1.83	Max: 1.83	Duration: 23.33
Episode 22	Total Average Score: 0.89	Mean: 1.38	Min: 1.38	Max: 1.38	Duration: 22.61
Episode 23	Total Average Score: 0.93	Mean: 1.87	Min: 1.87	Max: 1.87	Duration: 21.74
Episode 24	Total Average Score: 0.99	Mean: 2.43	Min: 2.43	Max: 2.43	Duration: 21.78
Episode 25	Total Average Score: 0.98	Mean: 0.74	Min: 0.74	Max: 0.74	Duration: 21.58
Episode 26	Total Average Score: 1.03	Mean: 2.31	Min: 2.31	Max: 2.31	Duration: 22.37
Episode 27	Total Average Score: 1.02	Mean: 0.61	Min: 0.61	Max: 0.61	Duration: 24.01
Episode 28	Total Average Score: 1.02	Mean: 0.98	Min: 0.98	Max: 0.98	Duration: 21.81
Episode 29	Total Average Score: 1.02	Mean: 1.07	Min: 1.07	Max: 1.07	Duration: 21.88
Episode 30	Total Average Score: 1.03	Mean: 1.50	Min: 1.50	Max: 1.50	Duration: 24.15
Episode 30	Total Average Score: 1.03
Episode 31	Total Average Score: 1.15	Mean: 4.52	Min: 4.52	Max: 4.52	Duration: 26.27
Episode 32	Total Average Score: 1.14	Mean: 1.08	Min: 1.08	Max: 1.08	Duration: 27.95
Episode 33	Total Average Score: 1.17	Mean: 2.00	Min: 2.00	Max: 2.00	Duration: 26.56
Episode 34	Total Average Score: 1.26	Mean: 4.13	Min: 4.13	Max: 4.13	Duration: 23.11
Episode 35	Total Average Score: 1.26	Mean: 1.23	Min: 1.23	Max: 1.23	Duration: 22.50
Episode 36	Total Average Score: 1.31	Mean: 3.15	Min: 3.15	Max: 3.15	Duration: 23.07
Episode 37	Total Average Score: 1.33	Mean: 1.96	Min: 1.96	Max: 1.96	Duration: 21.91
Episode 38	Total Average Score: 1.40	Mean: 4.28	Min: 4.28	Max: 4.28	Duration: 26.14
Episode 39	Total Average Score: 1.49	Mean: 4.63	Min: 4.63	Max: 4.63	Duration: 25.57
Episode 40	Total Average Score: 1.49	Mean: 1.75	Min: 1.75	Max: 1.75	Duration: 28.34
Episode 40	Total Average Score: 1.49
Episode 41	Total Average Score: 1.49	Mean: 1.41	Min: 1.41	Max: 1.41	Duration: 25.53
Episode 42	Total Average Score: 1.52	Mean: 2.90	Min: 2.90	Max: 2.90	Duration: 25.58
Episode 43	Total Average Score: 1.53	Mean: 1.69	Min: 1.69	Max: 1.69	Duration: 28.54
Episode 44	Total Average Score: 1.54	Mean: 2.04	Min: 2.04	Max: 2.04	Duration: 24.41
Episode 45	Total Average Score: 1.60	Mean: 4.29	Min: 4.29	Max: 4.29	Duration: 23.84
Episode 46	Total Average Score: 1.65	Mean: 3.71	Min: 3.71	Max: 3.71	Duration: 24.94
Episode 47	Total Average Score: 1.71	Mean: 4.75	Min: 4.75	Max: 4.75	Duration: 24.43
Episode 48	Total Average Score: 1.71	Mean: 1.37	Min: 1.37	Max: 1.37	Duration: 24.46
Episode 49	Total Average Score: 1.81	Mean: 6.86	Min: 6.86	Max: 6.86	Duration: 24.58
Episode 50	Total Average Score: 1.91	Mean: 6.81	Min: 6.81	Max: 6.81	Duration: 23.94
Episode 50	Total Average Score: 1.91
Episode 51	Total Average Score: 1.99	Mean: 5.75	Min: 5.75	Max: 5.75	Duration: 24.00
Episode 52	Total Average Score: 2.06	Mean: 5.98	Min: 5.98	Max: 5.98	Duration: 24.57
Episode 53	Total Average Score: 2.13	Mean: 5.64	Min: 5.64	Max: 5.64	Duration: 24.07
Episode 54	Total Average Score: 2.23	Mean: 7.41	Min: 7.41	Max: 7.41	Duration: 24.00
Episode 55	Total Average Score: 2.32	Mean: 7.10	Min: 7.10	Max: 7.10	Duration: 24.64
Episode 56	Total Average Score: 2.34	Mean: 3.63	Min: 3.63	Max: 3.63	Duration: 24.65
Episode 57	Total Average Score: 2.35	Mean: 2.60	Min: 2.60	Max: 2.60	Duration: 25.70
Episode 58	Total Average Score: 2.39	Mean: 5.12	Min: 5.12	Max: 5.12	Duration: 31.43
Episode 59	Total Average Score: 2.42	Mean: 4.04	Min: 4.04	Max: 4.04	Duration: 24.29
Episode 60	Total Average Score: 2.51	Mean: 7.61	Min: 7.61	Max: 7.61	Duration: 24.16
Episode 60	Total Average Score: 2.51
Episode 61	Total Average Score: 2.65	Mean: 10.96	Min: 10.96	Max: 10.96	Duration: 24.48
Episode 62	Total Average Score: 2.67	Mean: 3.85	Min: 3.85	Max: 3.85	Duration: 25.31
Episode 63	Total Average Score: 2.72	Mean: 6.24	Min: 6.24	Max: 6.24	Duration: 24.88
Episode 64	Total Average Score: 2.81	Mean: 8.39	Min: 8.39	Max: 8.39	Duration: 24.54
Episode 65	Total Average Score: 2.90	Mean: 8.94	Min: 8.94	Max: 8.94	Duration: 24.56
Episode 66	Total Average Score: 2.95	Mean: 6.19	Min: 6.19	Max: 6.19	Duration: 24.18
Episode 67	Total Average Score: 3.03	Mean: 8.09	Min: 8.09	Max: 8.09	Duration: 24.90
Episode 68	Total Average Score: 3.03	Mean: 3.08	Min: 3.08	Max: 3.08	Duration: 24.32
Episode 69	Total Average Score: 3.05	Mean: 4.57	Min: 4.57	Max: 4.57	Duration: 24.80
Episode 70	Total Average Score: 3.09	Mean: 5.78	Min: 5.78	Max: 5.78	Duration: 25.04
Episode 70	Total Average Score: 3.09
Episode 71	Total Average Score: 3.15	Mean: 7.40	Min: 7.40	Max: 7.40	Duration: 22.38
Episode 72	Total Average Score: 3.18	Mean: 4.99	Min: 4.99	Max: 4.99	Duration: 23.39
Episode 73	Total Average Score: 3.24	Mean: 7.63	Min: 7.63	Max: 7.63	Duration: 26.63
Episode 74	Total Average Score: 3.25	Mean: 4.31	Min: 4.31	Max: 4.31	Duration: 25.56
Episode 75	Total Average Score: 3.33	Mean: 9.02	Min: 9.02	Max: 9.02	Duration: 25.97
Episode 76	Total Average Score: 3.42	Mean: 9.79	Min: 9.79	Max: 9.79	Duration: 23.79
Episode 77	Total Average Score: 3.43	Mean: 4.43	Min: 4.43	Max: 4.43	Duration: 23.69
Episode 78	Total Average Score: 3.51	Mean: 9.47	Min: 9.47	Max: 9.47	Duration: 23.64
Episode 79	Total Average Score: 3.53	Mean: 5.37	Min: 5.37	Max: 5.37	Duration: 23.55
Episode 80	Total Average Score: 3.59	Mean: 8.05	Min: 8.05	Max: 8.05	Duration: 26.41
Episode 80	Total Average Score: 3.59
Episode 81	Total Average Score: 3.66	Mean: 9.21	Min: 9.21	Max: 9.21	Duration: 23.63
Episode 82	Total Average Score: 3.72	Mean: 8.74	Min: 8.74	Max: 8.74	Duration: 23.84
Episode 83	Total Average Score: 3.74	Mean: 5.23	Min: 5.23	Max: 5.23	Duration: 25.05
Episode 84	Total Average Score: 3.77	Mean: 6.53	Min: 6.53	Max: 6.53	Duration: 23.51
Episode 85	Total Average Score: 3.80	Mean: 6.70	Min: 6.70	Max: 6.70	Duration: 24.32
Episode 86	Total Average Score: 3.85	Mean: 7.97	Min: 7.97	Max: 7.97	Duration: 24.38
Episode 87	Total Average Score: 3.91	Mean: 9.23	Min: 9.23	Max: 9.23	Duration: 25.79
Episode 88	Total Average Score: 4.02	Mean: 12.98	Min: 12.98	Max: 12.98	Duration: 24.46
Episode 89	Total Average Score: 4.07	Mean: 8.53	Min: 8.53	Max: 8.53	Duration: 27.01
Episode 90	Total Average Score: 4.09	Mean: 5.92	Min: 5.92	Max: 5.92	Duration: 27.81
Episode 90	Total Average Score: 4.09
Episode 91	Total Average Score: 4.13	Mean: 7.75	Min: 7.75	Max: 7.75	Duration: 29.34
Episode 92	Total Average Score: 4.16	Mean: 7.32	Min: 7.32	Max: 7.32	Duration: 30.07
Episode 93	Total Average Score: 4.27	Mean: 13.58	Min: 13.58	Max: 13.58	Duration: 27.48
Episode 94	Total Average Score: 4.33	Mean: 10.28	Min: 10.28	Max: 10.28	Duration: 25.51
Episode 95	Total Average Score: 4.35	Mean: 6.65	Min: 6.65	Max: 6.65	Duration: 28.37
Episode 96	Total Average Score: 4.39	Mean: 7.90	Min: 7.90	Max: 7.90	Duration: 26.21
Episode 97	Total Average Score: 4.43	Mean: 8.40	Min: 8.40	Max: 8.40	Duration: 28.74
Episode 98	Total Average Score: 4.45	Mean: 6.17	Min: 6.17	Max: 6.17	Duration: 27.12
Episode 99	Total Average Score: 4.53	Mean: 12.39	Min: 12.39	Max: 12.39	Duration: 25.79
Episode 100	Total Average Score: 4.55	Mean: 6.65	Min: 6.65	Max: 6.65	Duration: 25.92
Episode 100	Total Average Score: 4.55
Episode 101	Total Average Score: 4.65	Mean: 10.68	Min: 10.68	Max: 10.68	Duration: 25.67
Episode 102	Total Average Score: 4.72	Mean: 7.13	Min: 7.13	Max: 7.13	Duration: 25.94
Episode 103	Total Average Score: 4.83	Mean: 11.67	Min: 11.67	Max: 11.67	Duration: 27.42
Episode 104	Total Average Score: 4.89	Mean: 6.58	Min: 6.58	Max: 6.58	Duration: 26.64
Episode 105	Total Average Score: 4.99	Mean: 10.20	Min: 10.20	Max: 10.20	Duration: 26.34
Episode 106	Total Average Score: 5.13	Mean: 13.82	Min: 13.82	Max: 13.82	Duration: 26.23
Episode 107	Total Average Score: 5.25	Mean: 12.41	Min: 12.41	Max: 12.41	Duration: 26.41
Episode 108	Total Average Score: 5.36	Mean: 11.57	Min: 11.57	Max: 11.57	Duration: 25.92
Episode 109	Total Average Score: 5.42	Mean: 6.71	Min: 6.71	Max: 6.71	Duration: 26.98
Episode 110	Total Average Score: 5.50	Mean: 8.41	Min: 8.41	Max: 8.41	Duration: 27.84
Episode 110	Total Average Score: 5.50
Episode 111	Total Average Score: 5.65	Mean: 16.40	Min: 16.40	Max: 16.40	Duration: 22.94
Episode 112	Total Average Score: 5.75	Mean: 10.38	Min: 10.38	Max: 10.38	Duration: 22.91
Episode 113	Total Average Score: 5.83	Mean: 10.21	Min: 10.21	Max: 10.21	Duration: 22.88
Episode 114	Total Average Score: 5.87	Mean: 5.79	Min: 5.79	Max: 5.79	Duration: 23.33
Episode 115	Total Average Score: 6.13	Mean: 26.77	Min: 26.77	Max: 26.77	Duration: 22.99
Episode 116	Total Average Score: 6.30	Mean: 17.06	Min: 17.06	Max: 17.06	Duration: 22.87
Episode 117	Total Average Score: 6.42	Mean: 13.18	Min: 13.18	Max: 13.18	Duration: 23.01
Episode 118	Total Average Score: 6.47	Mean: 6.46	Min: 6.46	Max: 6.46	Duration: 23.49
Episode 119	Total Average Score: 6.60	Mean: 14.65	Min: 14.65	Max: 14.65	Duration: 23.42
Episode 120	Total Average Score: 6.72	Mean: 12.60	Min: 12.60	Max: 12.60	Duration: 23.67
Episode 120	Total Average Score: 6.72
Episode 121	Total Average Score: 6.77	Mean: 6.91	Min: 6.91	Max: 6.91	Duration: 22.99
Episode 122	Total Average Score: 6.90	Mean: 15.15	Min: 15.15	Max: 15.15	Duration: 22.98
Episode 123	Total Average Score: 6.97	Mean: 8.90	Min: 8.90	Max: 8.90	Duration: 22.98
Episode 124	Total Average Score: 7.02	Mean: 7.42	Min: 7.42	Max: 7.42	Duration: 23.45
Episode 125	Total Average Score: 7.10	Mean: 8.48	Min: 8.48	Max: 8.48	Duration: 23.01
Episode 126	Total Average Score: 7.21	Mean: 12.88	Min: 12.88	Max: 12.88	Duration: 23.05
Episode 127	Total Average Score: 7.34	Mean: 13.61	Min: 13.61	Max: 13.61	Duration: 24.43
Episode 128	Total Average Score: 7.35	Mean: 1.86	Min: 1.86	Max: 1.86	Duration: 23.82
Episode 129	Total Average Score: 7.44	Mean: 10.18	Min: 10.18	Max: 10.18	Duration: 23.27
Episode 130	Total Average Score: 7.59	Mean: 16.99	Min: 16.99	Max: 16.99	Duration: 23.75
Episode 130	Total Average Score: 7.59
Episode 131	Total Average Score: 7.69	Mean: 14.07	Min: 14.07	Max: 14.07	Duration: 23.75
Episode 132	Total Average Score: 7.90	Mean: 22.58	Min: 22.58	Max: 22.58	Duration: 23.33
Episode 133	Total Average Score: 8.05	Mean: 17.02	Min: 17.02	Max: 17.02	Duration: 23.35
Episode 134	Total Average Score: 8.35	Mean: 34.21	Min: 34.21	Max: 34.21	Duration: 23.60
Episode 135	Total Average Score: 8.49	Mean: 14.86	Min: 14.86	Max: 14.86	Duration: 23.48
Episode 136	Total Average Score: 8.60	Mean: 14.62	Min: 14.62	Max: 14.62	Duration: 23.30
Episode 137	Total Average Score: 8.73	Mean: 14.76	Min: 14.76	Max: 14.76	Duration: 23.40
Episode 138	Total Average Score: 8.83	Mean: 13.88	Min: 13.88	Max: 13.88	Duration: 23.40
Episode 139	Total Average Score: 8.98	Mean: 19.61	Min: 19.61	Max: 19.61	Duration: 23.41
Episode 140	Total Average Score: 9.07	Mean: 11.02	Min: 11.02	Max: 11.02	Duration: 23.68
Episode 140	Total Average Score: 9.07
Episode 141	Total Average Score: 9.19	Mean: 13.05	Min: 13.05	Max: 13.05	Duration: 26.42
Episode 142	Total Average Score: 9.29	Mean: 13.16	Min: 13.16	Max: 13.16	Duration: 23.41
Episode 143	Total Average Score: 9.47	Mean: 20.06	Min: 20.06	Max: 20.06	Duration: 23.62
Episode 144	Total Average Score: 9.57	Mean: 11.24	Min: 11.24	Max: 11.24	Duration: 23.67
Episode 145	Total Average Score: 9.72	Mean: 19.37	Min: 19.37	Max: 19.37	Duration: 24.97
Episode 146	Total Average Score: 9.77	Mean: 8.70	Min: 8.70	Max: 8.70	Duration: 23.41
Episode 147	Total Average Score: 9.85	Mean: 13.35	Min: 13.35	Max: 13.35	Duration: 25.04
Episode 148	Total Average Score: 9.94	Mean: 10.13	Min: 10.13	Max: 10.13	Duration: 25.74
Episode 149	Total Average Score: 10.06	Mean: 18.82	Min: 18.82	Max: 18.82	Duration: 26.18
Episode 150	Total Average Score: 10.15	Mean: 15.49	Min: 15.49	Max: 15.49	Duration: 35.68
Episode 150	Total Average Score: 10.15
Episode 151	Total Average Score: 10.21	Mean: 11.76	Min: 11.76	Max: 11.76	Duration: 28.42
Episode 152	Total Average Score: 10.27	Mean: 12.37	Min: 12.37	Max: 12.37	Duration: 25.38
Episode 153	Total Average Score: 10.36	Mean: 14.69	Min: 14.69	Max: 14.69	Duration: 25.66
Episode 154	Total Average Score: 10.42	Mean: 13.32	Min: 13.32	Max: 13.32	Duration: 27.88
Episode 155	Total Average Score: 10.56	Mean: 21.09	Min: 21.09	Max: 21.09	Duration: 31.56
Episode 156	Total Average Score: 10.60	Mean: 8.16	Min: 8.16	Max: 8.16	Duration: 24.32
Episode 157	Total Average Score: 10.72	Mean: 13.70	Min: 13.70	Max: 13.70	Duration: 23.95
Episode 158	Total Average Score: 10.72	Mean: 5.67	Min: 5.67	Max: 5.67	Duration: 26.10
Episode 159	Total Average Score: 10.86	Mean: 17.68	Min: 17.68	Max: 17.68	Duration: 31.74
Episode 160	Total Average Score: 10.94	Mean: 15.62	Min: 15.62	Max: 15.62	Duration: 34.36
Episode 160	Total Average Score: 10.94
Episode 161	Total Average Score: 10.98	Mean: 14.73	Min: 14.73	Max: 14.73	Duration: 25.24
Episode 162	Total Average Score: 11.03	Mean: 9.03	Min: 9.03	Max: 9.03	Duration: 25.59
Episode 163	Total Average Score: 11.10	Mean: 13.10	Min: 13.10	Max: 13.10	Duration: 25.36
Episode 164	Total Average Score: 11.13	Mean: 11.44	Min: 11.44	Max: 11.44	Duration: 25.16
Episode 165	Total Average Score: 11.21	Mean: 17.46	Min: 17.46	Max: 17.46	Duration: 25.39
Episode 166	Total Average Score: 11.31	Mean: 15.95	Min: 15.95	Max: 15.95	Duration: 25.45
Episode 167	Total Average Score: 11.57	Mean: 34.36	Min: 34.36	Max: 34.36	Duration: 27.87
Episode 168	Total Average Score: 11.67	Mean: 13.24	Min: 13.24	Max: 13.24	Duration: 25.47
Episode 169	Total Average Score: 11.77	Mean: 14.04	Min: 14.04	Max: 14.04	Duration: 23.97
Episode 170	Total Average Score: 11.86	Mean: 14.96	Min: 14.96	Max: 14.96	Duration: 25.98
Episode 170	Total Average Score: 11.86
Episode 171	Total Average Score: 11.90	Mean: 11.65	Min: 11.65	Max: 11.65	Duration: 25.32
Episode 172	Total Average Score: 11.97	Mean: 11.61	Min: 11.61	Max: 11.61	Duration: 25.90
Episode 173	Total Average Score: 11.99	Mean: 9.55	Min: 9.55	Max: 9.55	Duration: 26.13
Episode 174	Total Average Score: 12.10	Mean: 15.30	Min: 15.30	Max: 15.30	Duration: 27.70
Episode 175	Total Average Score: 12.11	Mean: 10.04	Min: 10.04	Max: 10.04	Duration: 26.30
Episode 176	Total Average Score: 12.12	Mean: 11.21	Min: 11.21	Max: 11.21	Duration: 25.39
Episode 177	Total Average Score: 12.32	Mean: 24.58	Min: 24.58	Max: 24.58	Duration: 26.49
Episode 178	Total Average Score: 12.40	Mean: 17.15	Min: 17.15	Max: 17.15	Duration: 26.62
Episode 179	Total Average Score: 12.47	Mean: 12.03	Min: 12.03	Max: 12.03	Duration: 28.03
Episode 180	Total Average Score: 12.45	Mean: 6.41	Min: 6.41	Max: 6.41	Duration: 28.10
Episode 180	Total Average Score: 12.45
Episode 181	Total Average Score: 12.51	Mean: 15.39	Min: 15.39	Max: 15.39	Duration: 28.32
Episode 182	Total Average Score: 12.69	Mean: 26.09	Min: 26.09	Max: 26.09	Duration: 26.38
Episode 183	Total Average Score: 12.81	Mean: 17.29	Min: 17.29	Max: 17.29	Duration: 24.91
Episode 184	Total Average Score: 12.92	Mean: 18.03	Min: 18.03	Max: 18.03	Duration: 24.95
Episode 185	Total Average Score: 13.00	Mean: 14.90	Min: 14.90	Max: 14.90	Duration: 26.00
Episode 186	Total Average Score: 13.08	Mean: 15.69	Min: 15.69	Max: 15.69	Duration: 25.49
Episode 187	Total Average Score: 13.17	Mean: 17.78	Min: 17.78	Max: 17.78	Duration: 25.08
Episode 188	Total Average Score: 13.30	Mean: 25.84	Min: 25.84	Max: 25.84	Duration: 24.82
Episode 189	Total Average Score: 13.40	Mean: 19.46	Min: 19.46	Max: 19.46	Duration: 25.53
Episode 190	Total Average Score: 13.43	Mean: 8.91	Min: 8.91	Max: 8.91	Duration: 24.73
Episode 190	Total Average Score: 13.43
Episode 191	Total Average Score: 13.53	Mean: 17.78	Min: 17.78	Max: 17.78	Duration: 26.52
Episode 192	Total Average Score: 13.61	Mean: 14.96	Min: 14.96	Max: 14.96	Duration: 28.56
Episode 193	Total Average Score: 13.65	Mean: 17.55	Min: 17.55	Max: 17.55	Duration: 26.95
Episode 194	Total Average Score: 13.69	Mean: 13.74	Min: 13.74	Max: 13.74	Duration: 27.33
Episode 195	Total Average Score: 13.68	Mean: 6.31	Min: 6.31	Max: 6.31	Duration: 27.01
Episode 196	Total Average Score: 13.71	Mean: 10.76	Min: 10.76	Max: 10.76	Duration: 27.11
Episode 197	Total Average Score: 13.81	Mean: 18.83	Min: 18.83	Max: 18.83	Duration: 27.90
Episode 198	Total Average Score: 13.96	Mean: 20.21	Min: 20.21	Max: 20.21	Duration: 27.23
Episode 199	Total Average Score: 14.03	Mean: 19.79	Min: 19.79	Max: 19.79	Duration: 26.99
Episode 200	Total Average Score: 14.07	Mean: 11.15	Min: 11.15	Max: 11.15	Duration: 27.70
Episode 200	Total Average Score: 14.07
Episode 201	Total Average Score: 14.16	Mean: 19.57	Min: 19.57	Max: 19.57	Duration: 27.56
Episode 202	Total Average Score: 14.31	Mean: 21.57	Min: 21.57	Max: 21.57	Duration: 27.00
Episode 203	Total Average Score: 14.33	Mean: 14.13	Min: 14.13	Max: 14.13	Duration: 27.17
Episode 204	Total Average Score: 14.48	Mean: 21.42	Min: 21.42	Max: 21.42	Duration: 27.18
Episode 205	Total Average Score: 14.65	Mean: 27.15	Min: 27.15	Max: 27.15	Duration: 27.12
Episode 206	Total Average Score: 14.73	Mean: 22.23	Min: 22.23	Max: 22.23	Duration: 27.23
Episode 207	Total Average Score: 14.72	Mean: 11.40	Min: 11.40	Max: 11.40	Duration: 27.26
Episode 208	Total Average Score: 14.82	Mean: 21.65	Min: 21.65	Max: 21.65	Duration: 27.44
Episode 209	Total Average Score: 14.92	Mean: 16.37	Min: 16.37	Max: 16.37	Duration: 27.29
Episode 210	Total Average Score: 15.07	Mean: 23.15	Min: 23.15	Max: 23.15	Duration: 28.18
Episode 210	Total Average Score: 15.07
Episode 211	Total Average Score: 15.03	Mean: 12.50	Min: 12.50	Max: 12.50	Duration: 27.35
Episode 212	Total Average Score: 15.08	Mean: 15.50	Min: 15.50	Max: 15.50	Duration: 27.42
Episode 213	Total Average Score: 15.23	Mean: 25.39	Min: 25.39	Max: 25.39	Duration: 27.42
Episode 214	Total Average Score: 15.27	Mean: 9.08	Min: 9.08	Max: 9.08	Duration: 27.43
Episode 215	Total Average Score: 15.13	Mean: 13.68	Min: 13.68	Max: 13.68	Duration: 27.87
Episode 216	Total Average Score: 15.06	Mean: 9.14	Min: 9.14	Max: 9.14	Duration: 27.73
Episode 217	Total Average Score: 15.11	Mean: 18.44	Min: 18.44	Max: 18.44	Duration: 27.62
Episode 218	Total Average Score: 15.25	Mean: 20.98	Min: 20.98	Max: 20.98	Duration: 27.51
Episode 219	Total Average Score: 15.26	Mean: 14.97	Min: 14.97	Max: 14.97	Duration: 30.11
Episode 220	Total Average Score: 15.29	Mean: 15.70	Min: 15.70	Max: 15.70	Duration: 27.11
Episode 220	Total Average Score: 15.29
Episode 221	Total Average Score: 15.28	Mean: 5.89	Min: 5.89	Max: 5.89	Duration: 25.94
Episode 222	Total Average Score: 15.21	Mean: 8.52	Min: 8.52	Max: 8.52	Duration: 28.58
Episode 223	Total Average Score: 15.21	Mean: 9.00	Min: 9.00	Max: 9.00	Duration: 28.60
Episode 224	Total Average Score: 15.33	Mean: 19.64	Min: 19.64	Max: 19.64	Duration: 27.69
Episode 225	Total Average Score: 15.41	Mean: 16.04	Min: 16.04	Max: 16.04	Duration: 28.78
Episode 226	Total Average Score: 15.41	Mean: 12.84	Min: 12.84	Max: 12.84	Duration: 26.76
Episode 227	Total Average Score: 15.46	Mean: 18.69	Min: 18.69	Max: 18.69	Duration: 28.42
Episode 228	Total Average Score: 15.80	Mean: 36.13	Min: 36.13	Max: 36.13	Duration: 27.51
Episode 229	Total Average Score: 15.86	Mean: 15.82	Min: 15.82	Max: 15.82	Duration: 29.97
Episode 230	Total Average Score: 15.98	Mean: 28.58	Min: 28.58	Max: 28.58	Duration: 30.11
Episode 230	Total Average Score: 15.98
Episode 231	Total Average Score: 16.01	Mean: 17.63	Min: 17.63	Max: 17.63	Duration: 31.65
Episode 232	Total Average Score: 15.98	Mean: 19.96	Min: 19.96	Max: 19.96	Duration: 31.17
Episode 233	Total Average Score: 16.04	Mean: 22.26	Min: 22.26	Max: 22.26	Duration: 31.23
Episode 234	Total Average Score: 15.85	Mean: 15.67	Min: 15.67	Max: 15.67	Duration: 29.72
Episode 235	Total Average Score: 15.84	Mean: 13.75	Min: 13.75	Max: 13.75	Duration: 30.05
Episode 236	Total Average Score: 15.76	Mean: 6.78	Min: 6.78	Max: 6.78	Duration: 29.90
Episode 237	Total Average Score: 15.75	Mean: 13.48	Min: 13.48	Max: 13.48	Duration: 28.59
Episode 238	Total Average Score: 15.75	Mean: 13.71	Min: 13.71	Max: 13.71	Duration: 28.75
Episode 239	Total Average Score: 15.86	Mean: 30.52	Min: 30.52	Max: 30.52	Duration: 28.26
Episode 240	Total Average Score: 15.94	Mean: 19.57	Min: 19.57	Max: 19.57	Duration: 28.37
Episode 240	Total Average Score: 15.94
Episode 241	Total Average Score: 16.04	Mean: 22.53	Min: 22.53	Max: 22.53	Duration: 28.07
Episode 242	Total Average Score: 16.05	Mean: 14.22	Min: 14.22	Max: 14.22	Duration: 27.06
Episode 243	Total Average Score: 16.00	Mean: 15.41	Min: 15.41	Max: 15.41	Duration: 27.76
Episode 244	Total Average Score: 16.03	Mean: 14.59	Min: 14.59	Max: 14.59	Duration: 28.40
Episode 245	Total Average Score: 15.95	Mean: 11.21	Min: 11.21	Max: 11.21	Duration: 29.00
Episode 246	Total Average Score: 15.96	Mean: 9.33	Min: 9.33	Max: 9.33	Duration: 28.92
Episode 247	Total Average Score: 16.07	Mean: 24.11	Min: 24.11	Max: 24.11	Duration: 29.15
Episode 248	Total Average Score: 16.15	Mean: 18.44	Min: 18.44	Max: 18.44	Duration: 29.62
Episode 249	Total Average Score: 16.14	Mean: 17.92	Min: 17.92	Max: 17.92	Duration: 28.50
Episode 250	Total Average Score: 16.26	Mean: 27.43	Min: 27.43	Max: 27.43	Duration: 28.92
Episode 250	Total Average Score: 16.26
Episode 251	Total Average Score: 16.31	Mean: 17.04	Min: 17.04	Max: 17.04	Duration: 28.51
Episode 252	Total Average Score: 16.36	Mean: 16.87	Min: 16.87	Max: 16.87	Duration: 29.99
Episode 253	Total Average Score: 16.32	Mean: 11.18	Min: 11.18	Max: 11.18	Duration: 30.54
Episode 254	Total Average Score: 16.48	Mean: 28.57	Min: 28.57	Max: 28.57	Duration: 29.32
Episode 255	Total Average Score: 16.50	Mean: 23.47	Min: 23.47	Max: 23.47	Duration: 28.11
Episode 256	Total Average Score: 16.63	Mean: 21.46	Min: 21.46	Max: 21.46	Duration: 30.26
Episode 257	Total Average Score: 16.69	Mean: 19.42	Min: 19.42	Max: 19.42	Duration: 28.18
Episode 258	Total Average Score: 16.80	Mean: 17.11	Min: 17.11	Max: 17.11	Duration: 30.10
Episode 259	Total Average Score: 16.78	Mean: 15.60	Min: 15.60	Max: 15.60	Duration: 30.36
Episode 260	Total Average Score: 16.86	Mean: 23.53	Min: 23.53	Max: 23.53	Duration: 29.54
Episode 260	Total Average Score: 16.86
Episode 261	Total Average Score: 17.03	Mean: 31.33	Min: 31.33	Max: 31.33	Duration: 28.39
Episode 262	Total Average Score: 17.04	Mean: 10.34	Min: 10.34	Max: 10.34	Duration: 28.02
Episode 263	Total Average Score: 17.12	Mean: 20.46	Min: 20.46	Max: 20.46	Duration: 27.92
Episode 264	Total Average Score: 17.16	Mean: 16.37	Min: 16.37	Max: 16.37	Duration: 28.07
Episode 265	Total Average Score: 17.28	Mean: 28.94	Min: 28.94	Max: 28.94	Duration: 27.93
Episode 266	Total Average Score: 17.34	Mean: 22.24	Min: 22.24	Max: 22.24	Duration: 28.29
Episode 267	Total Average Score: 17.24	Mean: 24.22	Min: 24.22	Max: 24.22	Duration: 27.91
Episode 268	Total Average Score: 17.39	Mean: 27.85	Min: 27.85	Max: 27.85	Duration: 27.76
Episode 269	Total Average Score: 17.44	Mean: 18.89	Min: 18.89	Max: 18.89	Duration: 27.88
Episode 270	Total Average Score: 17.53	Mean: 23.96	Min: 23.96	Max: 23.96	Duration: 27.75
Episode 270	Total Average Score: 17.53
Episode 271	Total Average Score: 17.61	Mean: 19.65	Min: 19.65	Max: 19.65	Duration: 29.00
Episode 272	Total Average Score: 17.74	Mean: 25.21	Min: 25.21	Max: 25.21	Duration: 27.60
Episode 273	Total Average Score: 17.88	Mean: 23.48	Min: 23.48	Max: 23.48	Duration: 31.45
Episode 274	Total Average Score: 17.95	Mean: 22.21	Min: 22.21	Max: 22.21	Duration: 28.06
Episode 275	Total Average Score: 18.03	Mean: 18.11	Min: 18.11	Max: 18.11	Duration: 28.58
Episode 276	Total Average Score: 18.12	Mean: 20.13	Min: 20.13	Max: 20.13	Duration: 27.25
Episode 277	Total Average Score: 18.13	Mean: 25.35	Min: 25.35	Max: 25.35	Duration: 30.60
Episode 278	Total Average Score: 18.08	Mean: 12.64	Min: 12.64	Max: 12.64	Duration: 27.99
Episode 279	Total Average Score: 18.20	Mean: 24.00	Min: 24.00	Max: 24.00	Duration: 27.87
Episode 280	Total Average Score: 18.38	Mean: 24.09	Min: 24.09	Max: 24.09	Duration: 27.62
Episode 280	Total Average Score: 18.38
Episode 281	Total Average Score: 18.51	Mean: 28.63	Min: 28.63	Max: 28.63	Duration: 28.02
Episode 282	Total Average Score: 18.59	Mean: 34.12	Min: 34.12	Max: 34.12	Duration: 28.45
Episode 283	Total Average Score: 18.53	Mean: 10.67	Min: 10.67	Max: 10.67	Duration: 32.83
Episode 284	Total Average Score: 18.58	Mean: 23.05	Min: 23.05	Max: 23.05	Duration: 28.37
Episode 285	Total Average Score: 18.62	Mean: 19.32	Min: 19.32	Max: 19.32	Duration: 27.73
Episode 286	Total Average Score: 18.74	Mean: 27.90	Min: 27.90	Max: 27.90	Duration: 27.09
Episode 287	Total Average Score: 18.90	Mean: 33.34	Min: 33.34	Max: 33.34	Duration: 28.77
Episode 288	Total Average Score: 18.85	Mean: 20.97	Min: 20.97	Max: 20.97	Duration: 27.65
Episode 289	Total Average Score: 18.90	Mean: 24.20	Min: 24.20	Max: 24.20	Duration: 29.40
Episode 290	Total Average Score: 19.03	Mean: 22.61	Min: 22.61	Max: 22.61	Duration: 29.46
Episode 290	Total Average Score: 19.03
Episode 291	Total Average Score: 19.08	Mean: 22.89	Min: 22.89	Max: 22.89	Duration: 29.73
Episode 292	Total Average Score: 19.23	Mean: 29.17	Min: 29.17	Max: 29.17	Duration: 27.80
Episode 293	Total Average Score: 19.29	Mean: 24.20	Min: 24.20	Max: 24.20	Duration: 28.51
Episode 294	Total Average Score: 19.42	Mean: 26.31	Min: 26.31	Max: 26.31	Duration: 27.08
Episode 295	Total Average Score: 19.67	Mean: 31.90	Min: 31.90	Max: 31.90	Duration: 27.09
Episode 296	Total Average Score: 19.87	Mean: 30.40	Min: 30.40	Max: 30.40	Duration: 27.28
Episode 297	Total Average Score: 19.99	Mean: 30.52	Min: 30.52	Max: 30.52	Duration: 27.06
Episode 298	Total Average Score: 20.05	Mean: 26.19	Min: 26.19	Max: 26.19	Duration: 28.37
Episode 299	Total Average Score: 20.14	Mean: 29.41	Min: 29.41	Max: 29.41	Duration: 28.65
Episode 300	Total Average Score: 20.28	Mean: 25.08	Min: 25.08	Max: 25.08	Duration: 29.41
Episode 300	Total Average Score: 20.28
Episode 301	Total Average Score: 20.25	Mean: 16.70	Min: 16.70	Max: 16.70	Duration: 29.35
Episode 302	Total Average Score: 20.32	Mean: 28.57	Min: 28.57	Max: 28.57	Duration: 28.18
Episode 303	Total Average Score: 20.45	Mean: 26.23	Min: 26.23	Max: 26.23	Duration: 28.03
Episode 304	Total Average Score: 20.53	Mean: 29.94	Min: 29.94	Max: 29.94	Duration: 32.18
Episode 305	Total Average Score: 20.59	Mean: 33.30	Min: 33.30	Max: 33.30	Duration: 28.75
Episode 306	Total Average Score: 20.66	Mean: 29.08	Min: 29.08	Max: 29.08	Duration: 28.29
Episode 307	Total Average Score: 20.83	Mean: 28.17	Min: 28.17	Max: 28.17	Duration: 28.46
Episode 308	Total Average Score: 20.89	Mean: 28.31	Min: 28.31	Max: 28.31	Duration: 27.97
Episode 309	Total Average Score: 21.10	Mean: 37.17	Min: 37.17	Max: 37.17	Duration: 27.79
Episode 310	Total Average Score: 21.23	Mean: 36.11	Min: 36.11	Max: 36.11	Duration: 28.54
Episode 310	Total Average Score: 21.23
Episode 311	Total Average Score: 21.39	Mean: 28.41	Min: 28.41	Max: 28.41	Duration: 28.27
Episode 312	Total Average Score: 21.51	Mean: 27.46	Min: 27.46	Max: 27.46	Duration: 28.78
Episode 313	Total Average Score: 21.58	Mean: 32.47	Min: 32.47	Max: 32.47	Duration: 29.05
Episode 314	Total Average Score: 21.78	Mean: 28.92	Min: 28.92	Max: 28.92	Duration: 28.29
Episode 315	Total Average Score: 21.76	Mean: 11.71	Min: 11.71	Max: 11.71	Duration: 28.39
Episode 316	Total Average Score: 21.99	Mean: 32.44	Min: 32.44	Max: 32.44	Duration: 29.09
Episode 317	Total Average Score: 22.14	Mean: 33.47	Min: 33.47	Max: 33.47	Duration: 29.29
Episode 318	Total Average Score: 22.08	Mean: 14.94	Min: 14.94	Max: 14.94	Duration: 28.43
Episode 319	Total Average Score: 22.24	Mean: 30.57	Min: 30.57	Max: 30.57	Duration: 28.61
Episode 320	Total Average Score: 22.40	Mean: 32.17	Min: 32.17	Max: 32.17	Duration: 28.61
Episode 320	Total Average Score: 22.40
Episode 321	Total Average Score: 22.70	Mean: 35.01	Min: 35.01	Max: 35.01	Duration: 29.52
Episode 322	Total Average Score: 22.94	Mean: 33.09	Min: 33.09	Max: 33.09	Duration: 28.90
Episode 323	Total Average Score: 23.13	Mean: 27.66	Min: 27.66	Max: 27.66	Duration: 30.02
Episode 324	Total Average Score: 23.19	Mean: 26.14	Min: 26.14	Max: 26.14	Duration: 29.98
Episode 325	Total Average Score: 23.15	Mean: 11.52	Min: 11.52	Max: 11.52	Duration: 28.64
Episode 326	Total Average Score: 23.34	Mean: 31.73	Min: 31.73	Max: 31.73	Duration: 29.97
Episode 327	Total Average Score: 23.49	Mean: 33.79	Min: 33.79	Max: 33.79	Duration: 28.66
Episode 328	Total Average Score: 23.43	Mean: 30.11	Min: 30.11	Max: 30.11	Duration: 29.06
Episode 329	Total Average Score: 23.60	Mean: 33.53	Min: 33.53	Max: 33.53	Duration: 27.91
Episode 330	Total Average Score: 23.65	Mean: 33.31	Min: 33.31	Max: 33.31	Duration: 29.92
Episode 330	Total Average Score: 23.65
Episode 331	Total Average Score: 23.76	Mean: 28.83	Min: 28.83	Max: 28.83	Duration: 28.76
Episode 332	Total Average Score: 23.92	Mean: 35.94	Min: 35.94	Max: 35.94	Duration: 29.43
Episode 333	Total Average Score: 24.03	Mean: 33.41	Min: 33.41	Max: 33.41	Duration: 30.88
Episode 334	Total Average Score: 24.06	Mean: 17.96	Min: 17.96	Max: 17.96	Duration: 28.10
Episode 335	Total Average Score: 24.16	Mean: 23.52	Min: 23.52	Max: 23.52	Duration: 27.96
Episode 336	Total Average Score: 24.43	Mean: 34.60	Min: 34.60	Max: 34.60	Duration: 28.15
Episode 337	Total Average Score: 24.52	Mean: 21.98	Min: 21.98	Max: 21.98	Duration: 28.00
Episode 338	Total Average Score: 24.62	Mean: 23.86	Min: 23.86	Max: 23.86	Duration: 28.84
Episode 339	Total Average Score: 24.54	Mean: 22.84	Min: 22.84	Max: 22.84	Duration: 30.53
Episode 340	Total Average Score: 24.69	Mean: 34.19	Min: 34.19	Max: 34.19	Duration: 31.90
Episode 340	Total Average Score: 24.69
Episode 341	Total Average Score: 24.76	Mean: 29.50	Min: 29.50	Max: 29.50	Duration: 29.82
Episode 342	Total Average Score: 24.96	Mean: 34.78	Min: 34.78	Max: 34.78	Duration: 29.77
Episode 343	Total Average Score: 25.11	Mean: 30.37	Min: 30.37	Max: 30.37	Duration: 28.82
Episode 344	Total Average Score: 25.19	Mean: 21.72	Min: 21.72	Max: 21.72	Duration: 32.07
Episode 345	Total Average Score: 25.42	Mean: 34.60	Min: 34.60	Max: 34.60	Duration: 28.95
Episode 346	Total Average Score: 25.69	Mean: 36.44	Min: 36.44	Max: 36.44	Duration: 29.60
Episode 347	Total Average Score: 25.78	Mean: 33.06	Min: 33.06	Max: 33.06	Duration: 29.23
Episode 348	Total Average Score: 25.89	Mean: 28.95	Min: 28.95	Max: 28.95	Duration: 30.04
Episode 349	Total Average Score: 26.01	Mean: 30.45	Min: 30.45	Max: 30.45	Duration: 29.49
Episode 350	Total Average Score: 26.10	Mean: 36.86	Min: 36.86	Max: 36.86	Duration: 30.84
Episode 350	Total Average Score: 26.10
Episode 351	Total Average Score: 26.21	Mean: 27.30	Min: 27.30	Max: 27.30	Duration: 30.16
Episode 352	Total Average Score: 26.32	Mean: 28.55	Min: 28.55	Max: 28.55	Duration: 30.89
Episode 353	Total Average Score: 26.48	Mean: 26.95	Min: 26.95	Max: 26.95	Duration: 28.49
Episode 354	Total Average Score: 26.50	Mean: 30.69	Min: 30.69	Max: 30.69	Duration: 28.71
Episode 355	Total Average Score: 26.56	Mean: 29.12	Min: 29.12	Max: 29.12	Duration: 28.53
Episode 356	Total Average Score: 26.72	Mean: 37.48	Min: 37.48	Max: 37.48	Duration: 28.57
Episode 357	Total Average Score: 26.87	Mean: 34.25	Min: 34.25	Max: 34.25	Duration: 28.55
Episode 358	Total Average Score: 27.05	Mean: 35.09	Min: 35.09	Max: 35.09	Duration: 29.00
Episode 359	Total Average Score: 27.17	Mean: 28.06	Min: 28.06	Max: 28.06	Duration: 29.33
Episode 360	Total Average Score: 27.23	Mean: 28.84	Min: 28.84	Max: 28.84	Duration: 28.69
Episode 360	Total Average Score: 27.23
Episode 361	Total Average Score: 27.12	Mean: 20.89	Min: 20.89	Max: 20.89	Duration: 28.70
Episode 362	Total Average Score: 27.31	Mean: 29.31	Min: 29.31	Max: 29.31	Duration: 28.78
Episode 363	Total Average Score: 27.41	Mean: 30.79	Min: 30.79	Max: 30.79	Duration: 28.84
Episode 364	Total Average Score: 27.57	Mean: 31.47	Min: 31.47	Max: 31.47	Duration: 29.62
Episode 365	Total Average Score: 27.64	Mean: 36.19	Min: 36.19	Max: 36.19	Duration: 29.02
Episode 366	Total Average Score: 27.74	Mean: 32.82	Min: 32.82	Max: 32.82	Duration: 28.88
Episode 367	Total Average Score: 27.87	Mean: 36.50	Min: 36.50	Max: 36.50	Duration: 29.21
Episode 368	Total Average Score: 27.93	Mean: 34.35	Min: 34.35	Max: 34.35	Duration: 29.14
Episode 369	Total Average Score: 28.05	Mean: 30.63	Min: 30.63	Max: 30.63	Duration: 28.92
Episode 370	Total Average Score: 28.18	Mean: 37.20	Min: 37.20	Max: 37.20	Duration: 28.94
Episode 370	Total Average Score: 28.18
Episode 371	Total Average Score: 28.26	Mean: 27.55	Min: 27.55	Max: 27.55	Duration: 29.01
Episode 372	Total Average Score: 28.36	Mean: 35.02	Min: 35.02	Max: 35.02	Duration: 28.89
Episode 373	Total Average Score: 28.49	Mean: 36.27	Min: 36.27	Max: 36.27	Duration: 29.02
Episode 374	Total Average Score: 28.64	Mean: 37.26	Min: 37.26	Max: 37.26	Duration: 29.37
Episode 375	Total Average Score: 28.79	Mean: 33.35	Min: 33.35	Max: 33.35	Duration: 29.17
Episode 376	Total Average Score: 28.95	Mean: 36.25	Min: 36.25	Max: 36.25	Duration: 28.99
Episode 377	Total Average Score: 29.06	Mean: 36.13	Min: 36.13	Max: 36.13	Duration: 29.08
Episode 378	Total Average Score: 29.28	Mean: 34.82	Min: 34.82	Max: 34.82	Duration: 31.41
Episode 379	Total Average Score: 29.37	Mean: 32.79	Min: 32.79	Max: 32.79	Duration: 33.35
Episode 380	Total Average Score: 29.47	Mean: 34.23	Min: 34.23	Max: 34.23	Duration: 34.34
Episode 380	Total Average Score: 29.47
Episode 381	Total Average Score: 29.51	Mean: 32.42	Min: 32.42	Max: 32.42	Duration: 30.20
Episode 382	Total Average Score: 29.52	Mean: 35.40	Min: 35.40	Max: 35.40	Duration: 32.04
Episode 383	Total Average Score: 29.73	Mean: 32.16	Min: 32.16	Max: 32.16	Duration: 32.03
Episode 384	Total Average Score: 29.88	Mean: 37.98	Min: 37.98	Max: 37.98	Duration: 33.27
Episode 385	Total Average Score: 30.03	Mean: 33.64	Min: 33.64	Max: 33.64	Duration: 32.71
Problem Solved after 385 epsisodes!! Total Average score: 30.03
```


