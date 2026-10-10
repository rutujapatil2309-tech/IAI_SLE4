# SLE-4 Viva Practice

## 1. What is an ADR?
An Architecture Decision Record is a short document that explains an important design decision, the alternatives considered, the reason for the choice, and its consequences.

## 2. Why did you choose BFS?
For an unweighted graph, BFS explores nodes level by level and finds a path with the fewest edges.

## 3. What is the difference between BFS and DFS?
BFS uses a FIFO queue and explores level by level. DFS follows a branch deeply before backtracking. BFS guarantees a shortest path in an unweighted graph; DFS does not.

## 4. What are the disadvantages of BFS?
It can store many frontier nodes and use more memory, especially for wide graphs.

## 5. Why use a visited set?
It prevents the algorithm from repeatedly exploring the same nodes and helps prevent infinite traversal in cyclic graphs.

## 6. What did SLE-2 profiling show?
Answer with the actual measurements in your SLE-2 report: runtime and nodes expanded for BFS and DFS. Do not quote values until you have checked the report.

## 7. What is the purpose of C4 diagrams?
C4 diagrams describe software architecture at different levels, from system context down to containers, components, and code-level structure.

## 8. How does modular design help?
Separating graph/input handling, search logic, and output makes each responsibility easier to test and maintain.

## 9. What happens when the graph becomes larger?
BFS may require much more memory because its frontier can become wide. Runtime depends on the number of vertices and edges.

## 10. What did AI contribute?
State honestly which parts AI helped draft or explain and which parts you implemented, tested, measured, and verified yourself.
