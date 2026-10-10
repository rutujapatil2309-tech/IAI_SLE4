# SLE-4: Final Viva & Architecture Decision Record (ADR)

**Course:** 02AML204 – Introduction to Artificial Intelligence  
**PRN:** 25UAM050  
**Name:** Rutuja Patil  
**Division:** ______  
**Date:** 10 October 2026  
**GitHub:** https://github.com/rutujapatil2309-tech/IAI_SLE4

## Part A — Architecture Decision Record

### Title: Use Breadth-First Search (BFS) as the primary search strategy for an unweighted graph
**Status:** Accepted

### 1. Context
In SLE-1, I implemented a graph-search agent to find a route from a start node to a goal node. The graph contains connected nodes and the task is to find a path to the target. In SLE-2, I compared Breadth-First Search (BFS) and Depth-First Search (DFS) and considered their runtime behaviour and number of explored nodes. In SLE-3, I documented the system structure using C4 architecture views. The search strategy needed to be understandable, testable, and appropriate for an unweighted graph.

### 2. Decision
I selected **BFS as the primary algorithm** when the objective is to find the shortest path in an unweighted graph. DFS remains a useful comparison algorithm, but it is not the default when shortest-path correctness is required.

### 3. Alternatives Considered
- **Depth-First Search (DFS):** explores one branch deeply before backtracking. It can find a goal, but does not guarantee the shortest path.
- **Uniform-Cost Search:** useful when edges have different costs, but adds priority-queue and path-cost management that are unnecessary for an unweighted graph.
- **A* Search:** can be efficient when a suitable heuristic is available, but requires a meaningful heuristic and additional implementation decisions.

### 4. Rationale / Justification
- BFS explores the graph level by level and therefore finds a path with the fewest edges when all edges have equal cost.
- DFS is a valuable baseline, but the path it returns can depend strongly on neighbour order.
- The SLE-2 comparison was designed to examine the two algorithms on the same graph and goal, making the comparison more meaningful.
- The graph-search implementation uses a frontier and a visited collection to avoid repeatedly exploring already discovered nodes.
- In the C4 design, keeping input/graph setup, search logic, and result display as separate responsibilities makes the algorithm easier to test and replace.
- BFS may use more memory than DFS because it can hold many frontier nodes at once.
- **Measured evidence from SLE-2 must be recorded here before submission:** BFS runtime: ___; DFS runtime: ___; BFS nodes expanded: ___; DFS nodes expanded: ___. Use the actual results from your profiling report—do not estimate or invent these values.
- Based on shortest-path correctness for an unweighted graph, BFS is the better default for this task; measured performance should be discussed alongside this correctness requirement.

### 5. Consequences
**Positive**
- Finds a shortest path in an unweighted graph.
- Behaviour is systematic and straightforward to explain during viva.
- A modular design makes it easier to compare or replace search strategies.

**Negative / Trade-offs**
- BFS can consume substantial memory on wide graphs.
- Runtime and memory usage depend on graph size and structure.
- For weighted graphs, ordinary BFS is not sufficient to guarantee a minimum-cost path.

### 6. References
- SLE-2 repository: https://github.com/rutujapatil2309-tech/IAI_SLE2
- SLE-3 repository: https://github.com/rutujapatil2309-tech/IAI_SLE3
- SLE-4 repository: https://github.com/rutujapatil2309-tech/IAI_SLE4

## Part B — Summary of My SLE Journey
In SLE-1, I built a graph-search agent and documented the code and AI assistance. In SLE-2, I compared BFS and DFS and considered runtime and nodes expanded. In SLE-3, I represented the system using C4 architecture diagrams at different levels of detail. For SLE-4, I recorded why BFS is preferred for shortest-path search in an unweighted graph, considered alternatives, and documented the benefits and trade-offs. The final rationale should be checked against my actual SLE-2 profiling measurements and SLE-3 diagrams.

## Part C — AI Contribution Note
- **AI tools used:** ChatGPT and GitHub tools, where applicable.
- **What AI helped with:** Organising the ADR, explaining algorithm trade-offs, and preparing possible viva questions.
- **What I did myself:** I am responsible for checking the implementation, confirming the SLE-2 profiling values, reviewing the C4 diagrams, and ensuring I can explain and defend the decision. Update this note to reflect the assistance actually used.

## Part D — Viva Preparation Notes
1. BFS uses a FIFO queue and explores nodes level by level.
2. BFS finds a shortest path in an unweighted graph; DFS does not guarantee this.
3. BFS generally uses more memory; DFS can use less memory depending on the implementation and graph.
4. A visited set prevents repeated exploration and helps avoid loops.
5. Explain the measured BFS/DFS runtime and expanded-node counts from the SLE-2 report, and describe how the C4 views separate system responsibilities.
