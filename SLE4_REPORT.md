# SLE-4 Report — Rutuja Patil

**PRN:** 25UAM050  
**Course:** 02AML204 – Introduction to Artificial Intelligence  
**Division:** A

## Part A — Architecture Decision Record
### Decision
Use Breadth-First Search (BFS) as the primary algorithm for shortest-path search in an unweighted graph.

### Context
SLE-1 developed the graph-search foundation, SLE-2 compared BFS and DFS, and SLE-3 documented architecture using C4 views. SLE-4 records the design decision and explains the trade-offs.

### Alternatives
- **DFS:** explores deeply before backtracking; does not guarantee a shortest path.
- **Uniform-Cost Search:** suitable for graphs with different edge costs, but unnecessary for equal-cost edges.
- **A* Search:** can be efficient with a suitable heuristic, which must be designed and validated.

### Evidence and rationale
The previously reported profiling values are:

| Metric | BFS | DFS |
|---|---:|---:|
| Nodes expanded | 15 | 23 |
| Average runtime | 0.011774 ms | 0.008656 ms |

BFS expanded fewer nodes in this run; DFS had a lower average runtime. Runtime can vary with implementation overhead, traversal order, and measurement noise. BFS is selected because it guarantees the fewest-edge path for an unweighted graph. BFS can use more memory than DFS, and ordinary BFS is not sufficient for weighted shortest-path problems.

## Part B — SLE journey
SLE-1 established the graph-search agent. SLE-2 compared BFS and DFS through node expansion and runtime. SLE-3 represented system structure using C4 architecture views. SLE-4 connects these outputs into a documented decision with alternatives, evidence, trade-offs, and viva preparation.

- SLE-2: https://github.com/rutujapatil2309-tech/IAI_SLE2
- SLE-3: https://github.com/rutujapatil2309-tech/IAI_SLE3
- SLE-4: https://github.com/rutujapatil2309-tech/IAI_SLE4

## Part C — AI contribution
AI assistance helped organise the ADR, clarify search algorithm trade-offs, and draft documentation and practice questions. The student is responsible for verifying the implementation, profiling output, architecture diagrams, and final wording. The contribution log should be edited if any statement does not accurately reflect the work performed.

## Part D — Viva preparation
1. **What is an ADR?** A record of a design decision, context, alternatives, rationale, and consequences.
2. **Why BFS?** It finds a path with the fewest edges in an unweighted graph.
3. **BFS vs DFS?** BFS explores by levels with a FIFO queue; DFS explores deeply before backtracking.
4. **Does DFS guarantee shortest path?** No.
5. **Why visited set?** To prevent repeated exploration.
6. **What were the SLE-2 results?** BFS: 15 nodes, 0.011774 ms; DFS: 23 nodes, 0.008656 ms, as previously reported.
7. **Why was DFS faster in runtime?** Runtime depends on traversal order, implementation overhead, and measurement noise.
8. **What are C4 views?** Different levels of software architecture, from context to components and code.
9. **BFS limitation?** It may use considerable memory.
10. **When should a cost-aware algorithm be used?** When edges have different costs and minimum total cost matters.

## Final verification
Check the reported profiling values against the original output, ensure the C4 diagrams reflect the actual SLE-3 submission, and practise explaining the decision independently before submitting.
