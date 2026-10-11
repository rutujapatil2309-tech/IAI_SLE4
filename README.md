# IAI SLE-4 — Final Viva and Architecture Decision Record

**Student:** Rutuja Patil  
**PRN:** 25UAM050  
**Course:** 02AML204 – Introduction to Artificial Intelligence  
**Division:** A  
**Repository:** https://github.com/rutujapatil2309-tech/IAI_SLE4

## Objective
SLE-4 consolidates earlier work into an Architecture Decision Record (ADR). It explains why Breadth-First Search (BFS) is preferred for shortest-path search in an unweighted graph, compares alternatives, records the SLE-2 profiling values discussed for this project, and prepares for the viva.

## Repository contents
- [ADR.md](ADR.md) — Parts A–D: decision, SLE journey, AI contribution note, and viva preparation.
- [AI_CONTRIBUTION_LOG.md](AI_CONTRIBUTION_LOG.md) — AI assistance and student verification checklist.
- [VIVA_PREPARATION.md](VIVA_PREPARATION.md) — concise viva questions and answers.
- [SLE4_REPORT.md](SLE4_REPORT.md) — report text in Markdown format.

The editable four-page Word report, **SLE4_25UAM050_Rutuja_Patil.docx**, is supplied separately as a download.

## Main architecture decision
BFS is selected for shortest-path search in an unweighted graph because it explores nodes level by level and finds a path with the fewest edges. DFS remains useful as a comparison, but does not guarantee the shortest path.

## SLE-2 profiling values
| Metric | BFS | DFS |
|---|---:|---:|
| Nodes expanded | 15 | 23 |
| Average runtime | 0.011774 ms | 0.008656 ms |

These are the previously reported values and should be checked against the original profiling output. In the reported run BFS expanded fewer nodes, while DFS had lower average runtime. The algorithm choice is based on the shortest-path requirement, not on a claim that BFS is always faster.

## Before submission
1. Confirm the profiling values against the original SLE-2 evidence.
2. Ensure the SLE-3 C4 diagrams and architecture descriptions match your actual work.
3. Check the document page count and any faculty-specific formatting rules.
4. Review the AI contribution log so it truthfully reflects the assistance used.
5. Practise explaining the decision and its trade-offs in your own words.
