---
layout: default
title: Sequencing
nav_order: 1
---

# Sequencing

This is a sort of deep dive into how to formulate a disassembly problem as a sequencing / decision making problem. For that, we need to describe disassembly more precisely, such that it can be formulated as an optimization problem, some ways of disassembling are better than others. Given some initial state, and some set of actions, how do we systematically take something apart and arrive at a state where nothing can be further disassembled? Further, how do we describe the transition from one state of disassembly to another, and how do we measure which set of disassembly sequences is better or worse. To do this, we look at discrete planning, graph and set theory to formalize the problem mathematically. And we can use different programming strategies to solve this problem. 
1.  formulate
2.  solve

And theres different ways to do both. Here, we enumerate some strategies to solve a toy disassembly problem, just to see what's out there. 

* Discrete Planning
* Dynamic programming
* Multi-agent simulation
* Reinforcement Learning
* Fuzzy Logic 
* Bees Algorithm

---

### Discrete State Transitions:
States and actions:  
$$ s \in S$$ and $$ a \in A $$  
Transitions are defined as actions that get you from one state to another:  
$$ s' = T(s,a)$$  
The challenge is to find a trajectory of states that satisfies some constraint, where we reach a goal state:  
$$ \sigma = (s_1, s_2, ...,s_n)$$  
### Graph Search:<br>
DFS, BFS, Iterative Deepening --> go up to depth with DFS, then BFS, then forget everything and increase depth.<br>
### Heuristic Searches:<br>
A*, admissible heuristics are no less than the cost to reach the goal from a particular state. Good to steer towards a goal state if there's some knowledge about the topology of the problem. 

### Markov Decision Processes: <br>
Here use bellman optimality to iterate a value function until it converges. The value function is:  
$$V_\pi(s_t) = max \left(R(s_t,a_t) + \gamma \sum_{s_{t+1}\in S}P(s_t,a_t,s_{t+1})V(s_{t+1})\right) $$  
The summation is an expectation from the different possibilities of a given action and their respective resulting values.

<p>Policy and Value iteration:</p>
<video controls="" width="75%">
    <source src="../../assets/videos/policy.mp4" type="video/mp4"/>
</video>
<video controls="" width="75%">
    <source src="../../assets/videos/value.mp4" type="video/mp4"/>
</video>

### Getting Started with PyBullet: <br>
Pybullet hello world, make a simple URDF cnc machine, get it to move in a circle with positional commands.
More experiments will follow here:<br>

<video controls="" width="75%">
    <source src="../../assets/videos/pb_test.mp4" type="video/mp4"/>
</video>

