# IAI SLE-4 — Final Viva and Architecture Decision Record

**Student:** Rutuja Patil  
**PRN:** 25UAM050  
**Course:** 02AML204 – Introduction to Artificial Intelligence  
**Division:** Fill in before submission  
**Repository:** https://github.com/rutujapatil2309-tech/IAI_SLE4

## Objective
SLE-4 documents and defends an architecture decision based on the earlier SLE work. This submission explains why Breadth-First Search (BFS) is preferred for shortest-path search in an unweighted graph, considers alternatives, and prepares for the viva.

## Repository contents
- [ADR.md](ADR.md) — Architecture Decision Record, SLE journey, rationale, trade-offs, and viva notes.
- [AI_CONTRIBUTION_LOG.md](AI_CONTRIBUTION_LOG.md) — record of AI assistance and student verification responsibilities.
- [VIVA_PREPARATION.md](VIVA_PREPARATION.md) — concise viva questions and answers.
- [SLE4_PRN.docx](SLE4_PRN.docx) — four-page Word report, to be added to this repository after generation.

## Main decision
BFS is selected as the default for finding a shortest path in an unweighted graph because it explores nodes level by level and minimizes the number of edges in the returned path. DFS, Uniform-Cost Search, and A* are alternatives with different trade-offs.

## Before submission
1. Fill in your division.
2. Add the **actual** SLE-2 BFS/DFS runtime and nodes-expanded measurements to the ADR/report. Do not invent values.
3. Check that the report accurately reflects your own implementation and SLE-3 C4 diagrams.
4. Review the contribution log so it truthfully describes the tools and work used.
5. Confirm the Word report is four pages and follows the faculty naming convention.
6. Upload the final report to Moodle and prepare to explain the decision during the viva.

**Important:** Profiling fields remain blank until actual measurements are confirmed.
