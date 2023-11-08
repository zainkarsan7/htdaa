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
### Disassembly Sequencing: A Survey, Lambert 2003

* Search for optimum
* mechancial eleoctromechancial electronic devices
* disassembly is more than the reverse of assembly:
    * Disassembly depth is a variable, ie incomplete disassembly
    * assembly may not be reversible
    * the value added is far less than in assembly
    * more uncertainty:
        * quality
        * supply 
        <br>

Hence, robotic automation of disassembly is more challenging <br>
Different areas of research:
* disassembly planning
    * path planning for robots
        * stability analysis
        * component collisions
* scheduling
    * task planning
    * inventory control
* optimization and sequence generation
    * connection diagrams
    * precedence relations
    * subassembly feasibility / detection
        * modularity analysis, parallelism
    * clustering -> relating to logistics of recycling


### Novel Selective Disassembly Sequence Planning Method for Adaptive Reuse Buildings, Sanchez, 2019

> "Disassembly sequence planning is one of the most efficient methods to increase the reuse rate of components and reduce environmental impacts" --Rule-based recursive selective disassembly sequence planning for green design Smith,Chen 2011
* component by component disassembly with:  
    * environmental impacts
    * building cost
    * physical constraints
* more specifically: 
    * geometric data
    * spatial constraints (movement direction)
    * disassembly constraints (precedent relationships)
    * LCA data, component based
    * resource project management
        * materials
        * labor
        * machinery
    * cost
    * scheduling
* next, develop critical path sequences for Project management
* stocks from urban to transnational scales: a review, Renew. Sust. Energ
* Life cycle assessment of building B. Sanchez, et al. Automation in Construction 107 (2019) 102921 1
* Material stocks in Germany’s non-domestic buildings: a new quantification method
* A. Stephan, A. Athanassiadis, Quantifying and mapping embodied environmental requirements of urban building stocks
* J. Won, J.C.P. Cheng, Identifying potential opportunities of building information modeling for construction and demolition waste management and minimization
* M. Gorgolewski, Designing with reused building components: some challenges, Build. Res
* disassembly sequencing or deconstruction planning is typically done inuitively, but this commonly leads to failures because of the complexity of the process, data gathering, multiple criteria.
* toolchain for retrieving data from the BIM Model, to automate deconstruction planning.
* they use a constraint matrix with $M$ rows denoting components and $N$ columns denoting extraction directions $(\pm x, \pm y, \pm z)$. 
* uses a rule based heuristic method to improve solution time
    * merge similar nodes from different SDPB (single target disassembly sequence plan)
    * if set(A) has no intersection with set(B), keep their graphs separate
    * merge graphs with the same root node, choosing an extraction direction, biased to be x or y

* limited by the quality of the BIM model being deconstructed
* requires a liason graph too, how to construct it automatically
* H. Macher, T. Landes, P. Grussenmeyer, From point clouds to building information models: 3D semi-automatic reconstruction of indoors of existing buildings, Appl.
* . Kobyshev, H. Riemenschneider, A. Bódis-Szomorú, L. Van Gool, Efficient architectural structural element decomposition, Comput. Vis. Image Underst. 157 (2017) 300–312
* comparison to manufacturing disassembly, the problem is different, in product disassembly there is one worker, in a building there are many
    * this should hint to multi agent disassembly sequencing
* Used Tally in Revit to get LCA data, TRACI

* compare the construction industry to the manufacturing industry
    * destructive vs non-destructive
    * complete vs selective
    * sequential vs parallel
* disassembly time, reorientations, change of extraction directions, hardness of joint elements, selecting working tools, postural requirements, and material handling requirements
* no examples of this level of detail in the build con field

### Framework for Robot Assisted Deconstruction: Process,modelling, subsystems
* 30-80% of waste is CDW waste 
* until 2050, more than 50 billion euros spent on refurbishing and deconstruction
* conventional demolition includes:
    * manually
    * balling
    * pusher arm
    * deliberate collapse
    * wire rope pulling
    * implosion/explosion
    * high reach excavators
* these are all dangerous, require skilled labour, and potentially damaging to surroundings, aside from being  unsustainable
* demolition cost is borne by the party proposing the new building, so faster the better
* agent based modelling
* different on-site factories demolition strategies
* STCR 

### Framework for Estimating Reuse Value of In situ Bldg Materials
* urban mining
* Domestic Material Consumption (DMC) 90 billion tons per year from 2050. 2 billion tons annual waste, 60% is CDW 
* limited availability landfill, disposal cost, dumping restrictions
* "end of life" --> "end of placement" 
* transition to circular business models, "Building as Material Bank"
* material passports help provide a common ground for data collection of available material...somehow. 
* Factors that affect value of in situe materials:    

| factor           |  
|:-----------------|  
| age of structure |
| component connections |
| component lifespan |
| cost |
|design specs|
|wear|
|env and cost of impacts|
|EoL options|
|geometry|
|governmental incentives|
|landfill fees|
|market value of secondary materials|
|market value of virgin materials|
|technology|

* technology applied to take buliding apart, either conventionally destroyed, or labor intensively deconstructed
* if recovered material is low value, theres no point to dismantle carefully.
* Phase 1: Identify amount recoverable with Akanbi Recoverability Factor: $$ RF = f \times (1-e^{t-\alpha} - \dfrac{t}{10 \alpha})$$
    * $f$ is an adjustment factor scrap rate, $t$ is time, $\alpha$ is life span of material / component
$$M_{recover} = M \times RF$$
* no clue what this is based on, goes asymptotic as $t \rightarrow \alpha$ 

* Phase 2: identify cost with three scenarios:
    * disposal
    * recylcing/downcycling
    * cleaning and reuse
* Phase 3: Assess environmental impacts
    * assess for each scenario
* Phase 4: estimate total cost and value of material
$$ Cost_{Net} = M_{recover} \times (E_{cost} + E_{env} - T - V_{recover})$$
where T is a tax reduction, and $V_{recover}$ is market value of recovered material.  

* The paper uses a case study which concludes that the recycling of steel scrap is more economical than the reuse of steel primarily due to the cost of deconstruction, but somehow this equates to an environmental impact. 
* next step involves doing sensitivity analysis to identify key drivers of net cost. 

### Lego-Like Steel Framed System 

* demountable shear connections for composite flooring with precast elements, adjustable steel connections for beam-beam and column beam. Used at Petite Maison, ESCH2022.

* recovered steel has a GWP of $47 kg CO_2-e/tonne$ compared to 850 for blast furnace, and 550 for electric arc furnace production of new steel. 

* hence, recovered steel can be used in a continuous chain of construction products. 
* normally composite floor slabs have embedded studs and welded to steel beams, so difficult to remove. 
* L shaped brackets with slots for bolt through connections. 
* cast in place sleeves for underside connection to flanges. 
* The sleeve bolt shear connection is comparable or with cast in place studs, with high initial stiffness due to pretensioning. This is given by the so-called secant stiffness:  

$$S_{ini} = \dfrac{F_s}{s_{F_s}}$$

* but reduced stiffness as the bolt slips, roughly 40-50% of welded connections. 
* and friction coefficient suffers from reuse which affects the first phase of the bolt failure, the pretension/preload phase, secant stiffness.
* estimate of shear stress at bolt head is given by:
$$ F_v = \alpha_v \cdot f_{u,b} \cdot A_s$$

* where $F_v$ is shear stress, $\alpha$ is an experimentally derived coefficient of shear resistance - 0.58-0.67, $f_{u,b}$ is ultimate tensile strength, and A is area.
* modelled in abaqus, preload, bolt sleeve clearance and friction coefficient are most important.
* paper too boring, come back to it. 

### Review of Collective Robotic Construction

* 20% of work related injuries occur in construction from US dept of labor

* current construction trend include additive manufacturing, prefab subassemblies, and autonomous robot assisted technologies.
* collective robotic construction involves construction algos, self organizing systems, distributed computing bio inspired robotics,. 
* generalizeable methods for system integration to practice are missing, key challenge.
* depending on collective size and structural complexity, may or may not require coordination among individuals.
* for large collectives this coordination may not be advantageous.
* example: rufous hornero birds coordinate to build nest, small enough nest that its global state is easily perceptible. Counter are termites and ants, that work in a decentralized manner, each performing a task until completion irrespective of neighbors, building meter scale structures. 
* "stigmergic" coordination, agents affect other agents by affecting the environment. 
* local actions must map to their impacts on global state especially for structural stability, best evaluated globally. 
* high level planning and coordination with system dynamics, active area of research. 
* CRC should be robust to local distrubances, or individual agent failure, the more local information is exploited the more scalable and parellelized the cosntrcution can be. 
* Centralization and concurrency approach, involves dispatching robots to fulfill non-conflicting tasks, given by a central controller. 
* heterogeneous robot-rrobot or human - robot teams, higher risk of syetm failure, but potentially more energy/cost efficient
* homogenous teams are identical, robust to individual member failure
* discrete stae space planning, or combinations of discrete and continuous space, generally is material dependent, rigid elements can be modelled discretely, but deformable materials require continuous state representations.
* this paper is super high level...
* goals are represented differently, final shape, functional goal, or user specd templat. difference is emergent structure or preconcieved. 
* shape based goals involving preconcieved forms challenge is to avoid bad states, trajectory with efficient worker allocation adn ensured completion.
* mechanism and material: 
