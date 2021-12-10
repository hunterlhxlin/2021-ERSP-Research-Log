# ERSP Research Log
## Week 7 (11.8-11.14)
### Goals:

- [x] Update research log
- [x] Meet and talk with porfesser and phd student via zoom
- [x] read the materials
- [x] figure out methods to implement DeepImpact and test with it
- [x] figure out how to test with DeepImpact

### Accomplishments (10 hours)
- Start writing the research proposal base on the DeepImpact score
- Found this pyserini project on Github that already implemented DeepImpact
- Run the DeepImpact build index on our server
- Found that the performance is limited
- Noticed term-expansion feature of the DeepImpact: insert related terms into original document to boost accuracy, however this results in larger inverted indexes, thus limited performance
- Discuss possible solutions
- Analyze performance of DeepImpact and BM25 with differnt block size and top_k.
- Graphs listed below.
- ![Outcome](/visual.png)
- ![Outcome](/visual.png)
