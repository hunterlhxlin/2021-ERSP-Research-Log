# ERSP Research Log
## Week 8 (11.22-11.28)
### Goals:

- [x] Update research log
- [x] Meet and talk with porfesser and phd student via zoom
- [x] read the materials
- [x] testing the performance of algorithms with more options
- [x] analyze why performance is limited
- [x] keep writing research proposal

### Accomplishments (7.5 hours)
- Talked and think the main difference is the different distribution of the scores.
- Most dynamic pruning algorithms are implemented based on the maximum score of posting lists and blocks, thus tend to be more efficient when maximum can better represent the whole distribution. 
- However, as illustrated by the figures below, maximum scores tends to diverge more from the whole distribution, thus pruning become less efficient.
- BM25 distribution
- ![Outcome](/bm25.png)
- DeepImpact distribution
- ![Outcome](/deepimapct.png)
- Form some basic solutions for this problem
- Remove Stop Words: 
- - words such as ``and", ``or", ``an", ``the" often hardly contribute to the content of the document, thus we refer them as stop words. However, these stop words exist in almost all documents, resulting in massive posting lists for the algorithm to search and prune. Removing these words may help to reduce the size of the indexers and improve time efficiency of the algorithms.
- Accuracy-Efficiency Trade Off
- - Given DeepImpact outperforms traditional term score systems with respect to accuracy but is limited on time efficiency, it is a reasonable choice to trade some of the accuracy for faster retrieval. As mentioned before, currently, most dynamic pruning algorithms use the maximum score of a branch to decide whether a ``branch" should be pruned or not. Such logic guaranteed that no high relevance document will be pruned, but could be less efficient as more high score outliers appears. 
- - For modern information retrieval systems, given the fact that there are enough relevant document in the database and high-relevance documents are often quoting each other, missing a few related documents becomes more acceptable for pruning algorithms and thus a possible feature to trade for efficiency. Since high-score outliers are more common in DeepImpact than in BM25, instead of using MaxScore, a new metric that better represents the distribution of an entire block may be the solution for a more efficient dynamic pruning algorithm.
