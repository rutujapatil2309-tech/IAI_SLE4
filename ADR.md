# SLE-4: Final Viva & Architecture Decision Record (ADR)

**Course:** 02AML204 – Introduction to Artificial Intelligence  
**PRN:** 25UAM050  
**Name:** Rutuja Patil  
**Division:** A  
**GitHub:** https://github.com/rutujapatil2309-tech/IAI_SLE4

## Part A — Architecture Decision Record

### Title: Use Breadth-First Search (BFS) as the primary strategy for shortest-path search in an unweighted graph
**Status:** Accepted

### 1. Context
SLE-1 introduced a graph-search agent to find a route from a start node to a goal node. SLE-2 compared Breadth-First Search (BFS) and Depth-First Search (DFS), examining nodes expanded and runtime. SLE-3 documented the system architecture using C4 views. SLE-4 brings these activities together to justify a design choice that is understandable, testable, and suitable for an unweighted graph.

### 2. Decision
BFS is selected as the primary algorithm when the goal is to find a path with the fewest edges in an unweighted graph. DFS remains a useful comparison algorithm but is not the default when shortest-path correctness is required.

### 3. Alternatives considered
- **Depth-First Search (DFS):** follows one branch deeply before backtracking. It may find a goal, but does not guarantee a shortest path.
- **Uniform-Cost Search:** considers cumulative path cost and is appropriate when edges have different costs. Its priority queue and cost bookkeeping are unnecessary for a simple unweighted graph.
- **A* Search:** can efficiently find paths when a suitable heuristic is available, but requires a meaningful heuristic and additional implementation decisions.

### 4. SLE-2 profiling evidence
The previously reported SLE-2 measurements are summarised below. Runtime is environment- and implementation-dependent; retain the original profiling output as supporting evidence.

| Measure | BFS | DFS |
|---|---:|---:|
| Nodes expanded | 15 | 23 |
| Average runtime | 0.011774 ms | 0.008656 ms |

In this run, BFS expanded fewer nodes, while DFS recorded a lower average runtime. These results are not contradictory: runtime can be affected by implementation overhead, graph traversal order, and measurement noise. The choice of BFS is based primarily on its shortest-path guarantee for unweighted graphs, not on a claim that it is always faster.

### 5. Rationale and trade-offs
- BFS explores nodes level by level and finds a path with the fewest edges when every edge has equal cost.
- DFS is useful as a baseline, but its returned path depends on neighbour order and may not be shortest.
- Using the same graph and goal makes the SLE-2 comparison more meaningful.
- A frontier and visited collection help avoid repeated exploration.
- Separating graph setup, search logic, and result display makes the system easier to test and maintain.
- BFS may consume more memory than DFS because it can hold many frontier nodes simultaneously.
- Ordinary BFS does not guarantee a minimum-cost path when edge weights differ.

### 6. Consequences
**Benefits**
- Shortest-path correctness for unweighted graphs.
- Predictable, easy-to-explain traversal behaviour.
- Search strategies can be compared or replaced in a modular design.

**Costs and limitations**
- Potentially higher memory use on wide graphs.
- Runtime and memory depend on graph structure and implementation.
- Weighted graphs require a cost-aware algorithm such as Uniform-Cost Search.

## Part B — Summary of the SLE journey
**SLE-1:** Developed the foundation of a graph-search agent and documented the implementation.  
**SLE-2:** Compared BFS and DFS using nodes expanded and runtime. The reported results were 15 nodes and 0.011774 ms for BFS, and 23 nodes and 0.008656 ms for DFS.  
**SLE-3:** Described the system using C4 architecture views, showing the system and its internal responsibilities at different levels.  
**SLE-4:** Consolidated the earlier work into an Architecture Decision Record, weighed alternatives, recorded evidence, and prepared to defend the decision during the viva.

The repository links are included below. The final submission should be checked against the actual SLE-2 profiling output and SLE-3 diagrams before upload.

- SLE-2: https://github.com/rutujapatil2309-tech/IAI_SLE2
- SLE-3: https://github.com/rutujapatil2309-tech/IAI_SLE3
- SLE-4: https://github.com/rutujapatil2309-tech/IAI_SLE4

## Part C — AI contribution and verification
AI assistance was used to help organise the ADR, explain algorithm trade-offs, and draft documentation and viva practice material. The student remains responsible for checking the implementation, confirming profiling evidence, reviewing architecture diagrams, and being able to explain the design independently. The contribution log should be reviewed to ensure it truthfully represents the tools and assistance actually used.

## Part D — Viva preparation
1. **What is an ADR?** A short record of a design decision, its context, alternatives, rationale, and consequences.
2. **Why choose BFS?** It finds a path with the fewest edges in an unweighted graph.
3. **How does BFS differ from DFS?** BFS uses a FIFO queue and explores by levels; DFS follows a branch deeply before backtracking.
4. **Does DFS always find the shortest path?** No. Its path depends on traversal order.
5. **Why use a visited set?** To prevent repeated exploration and help avoid loops in cyclic graphs.
6. **What did the SLE-2 results show?** BFS expanded 15 nodes at 0.011774 ms; DFS expanded 23 nodes at 0.008656 ms in the reported measurements.
7. **Why was DFS faster despite expanding more nodes?** Timing can depend on implementation overhead, traversal order, and measurement noise; one run does not prove a general speed advantage.
8. **What are C4 diagrams?** Architecture views that describe a system at levels such as context, containers, components, and code.
9. **What is a limitation of BFS?** It can use substantial memory on wide graphs.
10. **When is BFS unsuitable?** When edge costs differ and a minimum-cost path is required; a cost-aware algorithm is then needed.

## References
- SLE-2 repository: https://github.com/rutujapatil2309-tech/IAI_SLE2
- SLE-3 repository: https://github.com/rutujapatil2309-tech/IAI_SLE3
- SLE-4 repository: https://github.com/rutujapatil2309-tech/IAI_SLE4
