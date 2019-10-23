# Welcome

## Specialization roadmap

Fundamentals of Reinforcement Learning_ Learning Objectives : https://d3c33hcgiwev3.cloudfront.net/nWJ7AazREemJ1w4LYV5qDg_56a68a293aa34cc8963ca23600315ba5_Fundamentals-of-Reinforcement-Learning_-Learning-Objectives-.pdf?Expires=1571788800&Signature=UXSgP9W69qHToz~HcUPuyTl6vzBpi8KwMW-qFh1Ex9LVfG7xW0umjwzu4BY~ivZIgVNhXtSt7MGnd2Fa2DGSSQlc13HlBTErgrxTCEI-6eKEoCGkfzW~TxYODPFFLSRdZ9rSBPJ31QcwhrgzRjF2dpU62nyOGLxJ06Fe1gpzK6I_&Key-Pair-Id=APKAJLTNE6QMUY6HBC5A

RL book : https://d3c33hcgiwev3.cloudfront.net/Ph9QFZnEEemRfw7JJ0OZYA_808e8e7d9a544e1eb31ad11069d45dc4_RLbook2018.pdf?Expires=1571788800&Signature=IwpWMHDgoUjTSoGLGhRnPo6-FbNqxqqqACf-eaG0XQ3sv5X-j3lI8haGX8L1otwDno-V6RWP7shxWmPxpmje1mCTl7Oj1kF8iwN4tByI1gIsCddudmxMdolXrbtEalVlMHNwFvnxJsX3bcptOfzQmPkyiwsVh-ruM-ipRhWv7q8_&Key-Pair-Id=APKAJLTNE6QMUY6HBC5A

# The K-Armed Bandit Problem
## Lesson 1: The K-Armed Bandit Problem
### Understand the temporal nature of the bandit problem

专治选择困难症——bandit算法 : https://zhuanlan.zhihu.com/p/21388070

### Define k-armed bandit
### Define action-values

Action-Values (or action value function) : q*(a)=E(R_t|A_t=a) = sum(p(r|a)r)

### Define reward

The goal is to maximize the expected reward : argmax(q*(a))

2 从Multi-arm Bandits问题分析 - RL进阶 : https://blog.csdn.net/coffee_cream/article/details/58034628

## Lesson 2: What to Learn? Estimating Action Values
### Define action-value estimation methods

Sample-average = sum of rewards when a taken prior to t / number of times a taken prior to t

Greedy action : chose the current best

### Define exploration and exploitation

exploration - exploitation dilemma : 探索-利用困境

### Select actions greedily using an action-value function
### Define online learning

Incremental update rule : new_estimate = old_estimate + step_size * (target - old_estimate)

Q_n+1 = (R_n - Q_n) / n + Q_n

### Understand a simple online sample-average action-value estimation method
### Define the general online update equation

Exponential, recency−weighted average : 

Q_n+1 = (1 - alpha) ^ n * Q_1 + sum(alpha * (1 - alpha) ^ (n - i) * R_i)

### Understand why we might use a constant stepsize in the case of non-stationarity

To convergent ?

## Lesson 3: Exploration vs. Exploitation Tradeoff
### Compare the short-term benefits of exploitation and the long-term benefits of exploration

Epsilon-Greedy Action Selection : P_epsilon to explore, (1 - P_epsilon) to exploit

### Understand optimistic initial values
### Describe the benefits of optimistic initial values for early exploration

Drive early exploration

### Explain the criticisms of optimistic initial values
### Describe the upper confidence bound action selection method
### Define optimism in the face of uncertainty
