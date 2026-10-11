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
The previously reported measurements were: BFS expanded 15 nodes with average runtime 0.011774 ms; DFS expanded 23 nodes with average runtime 0.008656 ms. Verify these values against the original profiling output before submission.

## 7. Why did DFS have lower runtime despite expanding more nodes?
Runtime can be affected by implementation overhead, traversal order, and measurement noise. One run does not establish a general speed advantage.

## 8. What is the purpose of C4 diagrams?
C4 diagrams describe software architecture at different levels, from system context down to containers, components, and code-level structure.

## 9. How does modular design help?
Separating graph/input handling, search logic, and output makes each responsibility easier to test and maintain.

## 10. What did AI contribute?
State honestly which parts AI helped draft or explain and which parts you implemented, tested, measured, and verified yourself.
