---
layout: default
title: Sequencing
nav_order: 1
---

# Sequencing

How to formulate a disassembly problem as a sequencing / decision making problem? Commonly studied in manufacturing, less in architecture. Challenge is how to augment existing strategies to describe problems in construction more aptly. Consider the intermediate bracing to a column and girder in the removal of this roof joist. 

<video autoplay muted loop playsinline controls="" width="100%">
    <source src="../../assets/videos/rumlang_2_small.mp4" type="video/mp4"/>
</video>
<br>
<div class="d-flex">
  <div class="flex: 0 0 50%; mr-8">
    <img src="{{ '/assets/images/toy_ex.png' | relative_url }}">
  </div>

   <div style="flex: 0 0 50%;">
    <p>
      Assemblies can be represented with elements as nodes, and edges as connections. Here's a simple example. The graph hold topological information but not spatial information. Computing spatial relationships can be encoded in so called contact and constraint matrices. The algorithms to compute them are shown below. The disassembly sequence starts with a node, using some heuristic like the least number of connected parts, choose blocking elements until nothing is in the way, remove the node, and adjust the matrices.
    </p>
  </div>
</div>


<br>

<video autoplay muted loop playsinline controls="" width="100%">
    <source src="../../assets/videos/disassembly_seq.mp4" type="video/mp4"/>
</video>
 
### Experiments:
<br> 
More examples below to find bugs, geometric or logic, to learn how the algorithm scales with complexity of assembly and number of parts.
<br>

<img src="{{ '/assets/images/experiments-01.jpg' | relative_url }}" alt="experiments" class="w-100">
<br>
<img src="{{ '/assets/images/experiments-sequence_results-01.png' | relative_url }}" alt="experiments" class="w-100">
<br>
### Time Complexity:
<br>
<div class="d-flex">
  <div class="flex: 0 0 67%; mr-4">
    <img src="{{ '/assets/images/computational_time_plot-01.png' | relative_url }}">
  </div>

   <div style="flex: 0 0 33%;">
    <p>
      Checking stresses and motion constraints are bottlenecks. A different approach from voxel mapping and solving the PDE for linear elasticity would make things faster.
    </p>
  </div>
</div>



<!-- ### Discrete State Transitions:
States and actions:  
$$ s \in S$$ and $$ a \in A $$  
Transitions are defined as actions that get you from one state to another:  
$$ s' = T(s,a)$$  
The challenge is to find a trajectory of states that satisfies some constraint, where we reach a goal state:  
$$ \sigma = (s_1, s_2, ...,s_n)$$  
### Graph Search:<br>
DFS, BFS, Iterative Deepening go up to depth with DFS, then BFS, then forget everything and increase depth.<br>
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
</video> -->

<!-- ## Autonomous industrial equipment:

Forklift robot, autonomous material handling $$\rightarrow$$ Frazzoli @ ETH <br>

### Critical Radius for Random Geometric Graphs
$$ r_n = \gamma (\dfrac{\log(n)}{n})^{(\dfrac{1}{d})}$$ -->

<!-- ## Multi Agent Planning:
Many agents, reactive and non-reactive for which the optimal strategy is a nash equilibrium <br>
Combinatorial explosion in dynamic games, $$\mathcal{O}(m^{\mathcal{A}})$$<br>
Use Fast Marching Trees Algorithm to deal with high dimensionality of search space $$\mathcal{O}(n^{-\dfrac{1}{d}+\rho})$$<br>
Or use graph factorization, by using subgames, hence building a simpler graph. <br>

Here's a multi-agent simulation using RRT* for path planning, and some right of way behaviour to plan collision free paths for autonomous differential drive robots:<br>
<video controls="" width="75%">
    <source src="../../assets/videos/multi_agent.mp4" type="video/mp4"/>
</video> -->


