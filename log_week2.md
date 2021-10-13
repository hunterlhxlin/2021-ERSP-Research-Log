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

### Friday, Oct 8(0.5 hour):
#### Accomplishments
- Update research log

