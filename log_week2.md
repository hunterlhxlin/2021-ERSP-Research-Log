# ERSP Research Log
## Week 2 (10.4-10.10)
### Goals:

- [x] Update research log
- [x] Continue reading related materials
- [x] Meet and talk with porfesser via zoom
- [x] Watch lecture videos sent by professor


### Tuesday, Oct 5 (1.5 hour):
#### Accomplishments
- Update research log
- Watching Lecture that introduced the research topic
#### Study Log
- Introduction to Information Retrieval and Web Search 
  1 Spider (a.k.a. crawler/robot) – builds corpus & Collects web pages recursively
    - For each known URL, fetch the page, parse it, and extract new URLs
    - Repeat
    - Additional pages from direct submissions & other sources
  2 Indexer and offline text mining
    - create inverted indexes so online system can search
    - Enrich knowledge on things and their relationship though data mining and learning
  3 Online query process– serves query results
    - Front end – query reformulation, word processing
    - Back end – finds matching documents and ranks them
- Our topic focus on the algorithms that rank the documents by relativity for given queries
- Inverted Index
  - A dictionary
  - maps each word(query) to a linked list that contains the address of where the words appeared in which document
- User interaction, distributed storage, data mining, system optimization, etc.

### Wednesday, Oct 6(1.5 hour):
#### Accomplishments
- Update research log
- study slides sent by professor about ranking
#### Study Log
- Aspects of ranking 
  - Relevance
    - Documents need to be relevant to a user query.
  - Authoritativeness.
    - High quality content is normally preferred since users rely on trustful information to learn or make a decision.
  - Freshness.
    - Latest information is desired for time-sensitive queries.
  - Preference
    - Personal or geographical preference can impact the choices
- Weighted scoring for ranking
  - linear combination of feature scores and weights
    - Text frequency, Text proximity, etc.
  - Query dependent and Query independent
  - Modern system has more features: various text and document features
  - Simple example of the method & how the set-up can be more complex and specific
- Machine learning solution
  - Support Vector Machine(SVM): create a hyper plane (decision surface) that does classification
  - Convert ranking as SVM based classification
    - each pair of document can be classified as if more is more relevent to the query than another or not
    - ranking based on the relevence relations derived by the classification above


### Thursday, Oct 7(1 hour):
#### Accomplishments
- Meet with professor via zoom, starting at 1:10pm
#### Study Log
- Inverted index: Each index term is associated with an inverted list
  - Contains lists of documents, or lists of word occurrences in documents, and other information
    - Support multiple ranking features, word counts, etc.  
  - Each entry is called a posting or postings
  - Lists are usually document-ordered (sorted by document number)
  - Used to speed up search process
- Data compression: Encoding and Decoding
  - For modern internet, too many documents
  - Compress data to save disk and memory space
    1 Delta Encoding - encode differences between consecutive numbers, if all document IDs are not very sparse
    2 V-byte encoding: instead of 4-byte for every integer, smaller number has smaller size: an binary identifier 
    3 Huffman Encoding: more frequent numbers becomes shorter after encoding
    - all methods only works well under specific situations
- Fast Ranking Approaches
  - Simplest way: sum all term socres in the query, TF-IDF, BM25, etc.
  - Term-at-a-Time (TAAT) query processing
    - reads posting lists for query terms successively
    - maintains an accumulator for each result document with value
  - Document-at-a-time (DAAT)
    - Assumes document-ordered posting lists
    - Reads posting lists for query terms concurrently
    - Computes score when same document is seen in one or more posting lists
    - Always advances posting list with lowest current document identifier
  - Pruning: to optimize, skip postings that will not be part of the search results
    - Skip pointers
      - Tradeoff:
        - More skips - shorter skip spans Þ more likely to skip. But lots of comparisons to skip pointers.
        - Fewer skips - few pointer comparison, but then long skip spans Þ few successful skips.
    - Early Termination: stop early, skipping, and partial scoring
    - Weak AND(WAND) query processing
      - Maintain a current document ID pointer at each posting list of term t: cdid(t)
      - MaxScore(t) is the maximum term score in term t’s posting list.
      - Dynamically maintain minScore as minimum score to be in top K
      - Skip some documents which are impossible to be in top K
        - if the score is lower than the current(searched) top K lower bound
    - BlockMax WAND(BMW)
      - Splits the inverted lists into blocks such that each block can be decompressed separately 
      - Create an extra table, which stores for each block
        - The max/min docID, Maximum score for each block
        - Still need to compute the maximum score per term posting list
      - Leverage more accurate per-block max score while skipping blocks of documents quickly
      - only decompress "promising blocks" to make the rank process more efficient
### Friday, Oct 8(0.5 hour):
#### Accomplishments
- Update research log

