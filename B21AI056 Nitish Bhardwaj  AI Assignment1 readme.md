# Sorting Algorithms Project 

## Overview

This Colab Notebook contains the implementation of seven different search algorithms for sorting numbers in an array. These algorithms are designed to efficiently arrange an input array into the desired sorted order. The project includes the following sorting algorithms:
1. Depth-First Search (DFS)
2. Iterative Deepening Depth-First Search (IDDFS or IDS)
3. Breadth-First Search (BFS)
4. Uniform Cost Search (UCS)
5. Greedy Search
6. A* Search (A-Star Search)
7. Hill Climbing Search

 Here is a 5 min read of these algorithm as implemented (interested readers may read, else you may skip it)
## Sorting using BFS

**Algorithm:** The code uses BFS to sort an input array by swapping adjacent elements.

**Data Structures:** It employs a queue (q), a path list, and a parent_map dictionary.

**BFS Implementation:**
- Starts with the initial array in the queue.
- Iteratively explores states (arrays) and generates child states by swapping elements.
- Tracks visited states and parent-child relationships.
- Continues until the sorting goal (sorted array) is reached.

**Path Retrieval:**
- Extends the path with unexplored states in the queue.
- Reconstructs the sorting path using the parent_map.

**Output:** Returns the original array, sorted array, sorting path, and nodes explored.

**Printing Results:** The code prints the start state, goal state, sorting path, and nodes explored.

**Purpose:** Demonstrates how BFS systematically explores states to achieve a goal (sorting an array).
## Sorting using DFS

**Algorithm:** The code uses Depth-First Search (DFS) to sort an input array by swapping adjacent elements.

**DFS Implementation:**
- Begins with the initial array.
- Recursively explores states (arrays) and generates child states by swapping elements.
- Maintains a visited list to track visited states.
- Stops when the sorting goal (a sorted array) is achieved or all possible states are explored.

**Path Retrieval:**
- Reconstructs the sorting path from the initial state to the sorted state.
- Uses a parent_map dictionary to track parent-child relationships.

**Output:** Returns the original array, the sorted array, the sorting path, and the number of nodes (states) explored during DFS.

**Printing Results:** The code prints:
- The start state (original array).
- The goal state (sorted array).
- The path taken from the start state to the goal state.
- The number of nodes explored during DFS traversal.

**Purpose:** Demonstrates how DFS explores states in a depth-first manner to achieve a goal (sorting an array).

## Sorting using Iterative Deepening

**Algorithm:** The code implements the IDDFS algorithm to sort an input array by swapping adjacent elements.

**IDDFS Implementation:**
- Starts with a depth of 1 and iteratively increases the depth limit until the sorting goal is achieved.
- Utilizes a depth-limited depth-first search (DFS) approach within each iteration.
- Maintains a visited set to track visited states and a stack for DFS traversal.

**DFS Implementation:**
- Begins with the initial array and adds it to the stack.
- Continues DFS traversal until the current depth limit is reached.
- Explores child states by swapping adjacent elements.
- Keeps track of the explored path, the current node, and the depth of the current search.
- Stops when the sorting goal (a sorted array) is achieved or all states within the depth limit are explored.

**Output:** Returns the original array, the sorted array, the sorting path, the number of nodes (states) explored during DFS, and the depth of the search.

**Printing Results:** The code prints:
- The start state (original array).
- The goal state (sorted array).
- The path taken from the start state to the goal state.
- The number of nodes explored during DFS traversal.
- The depth of the search.

**Purpose:** Demonstrates how the IDDFS algorithm explores states at increasing depths to achieve a goal (sorting an array) while ensuring a controlled exploration depth.

## Sorting using Uniform Cost Search (UCS)

**Algorithm:** The code implements the Uniform Cost Search (UCS) algorithm to sort an input array by swapping adjacent elements.

**UCS Implementation:**
- Utilizes a priority queue (PriorityQueue) to manage states (arrays) based on their path cost.
- Maintains a visited set to track visited states.

**Priority Queue:** The priority queue ensures that states with lower path costs are explored first, making UCS optimal.

**UCS Process:**
- Starts with the initial array and its path cost of 0.
- Continues to explore states with the lowest path cost.
- Stops when the sorting goal (a sorted array) is achieved.

**Output:** Returns the original array, the sorted array, the sorting path, the number of nodes (states) explored, and the cost of the solution.

**Printing Results:** The code prints:
- The start state (original array).
- The goal state (sorted array).
- The path taken from the start state to the goal state.
- The number of nodes explored during UCS traversal.
- The cost of the solution (total path cost).

**Purpose:** Demonstrates how UCS systematically explores states with the lowest path cost to find an optimal solution (sorting an array).

**Note:** For the task of sorting, all edge costs are the same.

## Sorting using Greedy Search (Best First Search)

**Algorithm:** The code implements the Greedy Search (Best First Search) algorithm to sort an input array by swapping adjacent elements.

**Greedy Search Implementation:**
- Utilizes a priority queue (priority_queue) to manage states (arrays) based on their heuristic values.
- Keeps track of visited states and an exploration path.

**Priority Queue:** The priority queue ensures that states with lower heuristic values (closer to the goal) are explored first.

**Heuristic Function:** It employs a custom heuristic function that counts the number of out-of-place elements in the array, providing an estimate of the distance from the current state to the goal state.

**Greedy Search Process:**
- Begins with the initial state and its heuristic value.
- Continues to explore states with the lowest heuristic values.
- Stops when the sorting goal (a sorted array) is achieved.

**Output:** Returns the original array, the sorted array, the sorting path, and the number of nodes (states) explored.

**Printing Results:** The code prints:
- The start state (original array).
- The goal state (sorted array).
- The path taken from the start state to the goal state.
- The number of nodes explored during Greedy Search.

**Purpose:** Demonstrates how Greedy Search uses a custom heuristic function to estimate the "closeness" to the solution, guiding the search efficiently towards the goal state. It's suitable for problems where a heuristic can provide a meaningful estimate of the distance to the solution.

## Sorting using A* Search

**Algorithm:** The code implements the A* Search algorithm to sort an input array by swapping adjacent elements. It uses a heuristic function to guide the search efficiently.

**A* Search Implementation:**
- Utilizes a priority queue (pqueue) to manage states (arrays) based on their estimated cost (fcost) which combines the cumulative cost and the heuristic value.
- Keeps track of visited states, an exploration path, and the total cost of each state.

**Priority Queue:** The priority queue ensures that states with lower estimated costs (fcost=h_cost + g_cost) are explored first, considering both the current cumulative cost and the heuristic value.

**Heuristic Function:** It employs a heuristic function (heuristic) to estimate the distance or cost from the current state to the goal state, which is added to the cumulative cost to calculate fcost.

**A* Search Process:**
- Begins with the initial state and its cumulative cost and fcost.
- Continues to explore states with the lowest estimated costs (fcost=h_cost + g_cost).
- Stops when the sorting goal (a sorted array) is achieved.

**Output:** Returns the original array, the sorted array, the sorting path, and the number of nodes (states) explored.

**Printing Results:** The code prints:
- The start state (original array).
- The goal state (sorted array).
- The path taken from the start state to the goal state.
- The number of nodes explored during A* Search.

**Purpose:** Demonstrates how A* Search uses a heuristic function to estimate the "closeness" to the solution and combines it with the cumulative cost to prioritize states for exploration. It is particularly useful for problems where both cost and heuristic information are available to guide the search efficiently.

## Sorting using Hill Climbing

**Algorithm:** The code implements the Hill Climbing algorithm with a heuristic function to sort an input array by swapping adjacent elements.

**Hill Climbing Implementation:**
- Utilizes a recursive function `rec_hc` for the Hill Climbing search.
- Keeps track of visited states, explored nodes, and the current state.

**Recursive Hill Climbing:**
- The `rec_hc` function recursively explores the state space by generating and evaluating neighboring states.
- It evaluates each neighboring state's heuristic value, and if a better state is found, it progresses to that state.
- The process continues until a local maximum (the best state) is reached or a goal state (sorted array) is found.

**Output:** Returns the goal state (sorted array) and the number of nodes (states) explored during the search.

**Printing Results:** The code prints:
- The start state (original array).
- The goal state (sorted array).
- The number of nodes explored during the Hill Climbing search.

**Purpose:** Demonstrates how Hill Climbing, guided by a heuristic function, attempts to reach the best state (local maximum) in the state space. It may not always find the global optimum but efficiently converges to local maxima. This approach is suitable for sorting problems where a heuristic can assess the quality of the current state.



## Usage Instructions

1. Open the Colab Notebook file `B21AI056 Nitish Bhardwaj  AI Assignment1.ipynb` in your preferred Notebook environment.

2. Navigate through the notebook to explore and execute each algorithm's implementation. Each section is clearly labeled with the name of the algorithm it demonstrates.

3. Follow the provided code to understand the algorithms' functionality and how they can be used for sorting tasks.

4. Feel free to modify or adapt the code as needed for your specific sorting requirements.

## Dependencies

This Jupyter Notebook is implemented in Python and does not require external libraries beyond the standard Python libraries.

## Author

Nitish Bhardwaj (B21AI056)

## Contact

For any questions or inquiries, please feel free to contact [bhardwaj.11@iitj.ac.in].
