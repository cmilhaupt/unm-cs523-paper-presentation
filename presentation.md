# Title

Abandoning Objectiv Abandoning Objectives: Evolution Through Through the Search for Novelty Alone

Joel Lehman
University of Central Florida
Kenneth O. Stanley
University of Central Florida

Colin Milhaupt & Greg Jacobus
University of New Mexico

# Background

- point

# The Search for Novelty

- Objective fitness functions don't reward intermediate stepping stones that lead to the objective
- Instead, reward instances whose functionality is significantly different from what has been discovered before
- Seems naive $\rightarrow$ where is the pressure to adapt?
- Not necessary $\rightarrow$ stepping stones are rewarded

# Novelty Search Algorithm

- Key idea: reward divergence from prior behavior
- Create a spatial mapping of evolved solutions
- Use k-means to measure sparsity (higher is better)

$$ \rho (x) = \frac{1}{k}\sum_{i=0}^k \text{dist}(x, u_i)  $$

Where $x$ is the point in question and $u_i$ is the $i$th nearest neighbor of $x$

# Experiment 1: Maze
$$
\includegraphics[width=200px]{"images/maze.png"}
$$

- Great for deception problems because dead ends that lead close to the goal are local optima
- Fitness-based NEAT metric is defined as the distance from the robot to the goal at the end of an evaluation
- Novelty-based NEAT metric rewards the robot for ending in a place where none have ended before; the method of traversal is ignored

# Experiment 1: Maze Results
$$
\includegraphics[width=200px]{"images/maze_performance.png"}
$$

- Fitness-based NEAT was three times slower (56k evaluations vs 18k)
- The average genomic complexity of solutions evolved by fitness-based NEAT was almost three times greater  than those evolved by Novelty-based NEAT
- The hard map was solved 3/40 times by fitness-based NEAT and 39/40 times by novelty-based NEAT

# Experiment 1: Maze Behaviors
$$
\includegraphics[width=150px]{"images/maze_with_walls_comparison.png"}
$$

- Bounding the Size of the Archive in the Maze Domain
    + Possible to limit the archive size, and thus additional computational effort, without significantly decreasing the performance of novelty search
- Removing Walls in the Maze Domain
    + Fitness fares no better; fitness-based search is not necessarily a viable alternative even when novelty search is not effective

# Experiment 1: Maze Behaviors

- Lengthening the Behavioral Characterization
    + High-dimensional behavior characterization is not a sufficient basis for predicting that novelty search should fail
- Reducing the Precision of the Behavioral Characterization
    + Archive size can be limited without significant loss of performance
- Characterizing Behavior as the Fitness Measure
    + This type of conflation can be disruptive to novelty search

# Experiment 2

- point

