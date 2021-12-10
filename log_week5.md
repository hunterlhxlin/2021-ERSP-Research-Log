# ERSP Research Log
## Week 5 (10.25-10.31)
### Goals:

- [x] Update research log
- [x] Meet and talk with porfesser and phd student via zoom
- [x] read the materials
- [x] Get the code running, test outcome with different parameters
- [ ] visualize the results
- [ ] looking for related papers, get prepared for research proposal
- [ ] Figure out the time measurement issue


### Monday, Oct 18 (1.5 hour):
#### Accomplishments
- Update research log
- Read the paper assigned by the professor
- Located why there's the error message - missing the file that contains the normalized document length.

### Tuesday, Oct 19 (1.5 hour):
#### Accomplishments
- Update research log
- Read the paper assigned by the professor
- Fixed the code
- Run the code with different parameters

### Thursday, Oct 21(2.5 hour):
#### Accomplishments
- Meet with phd student via zoom
- Ask questions about the paper and the code
- Discuss the general structure of the code and all the setup.
- Visual
![Outcome](/visual.png)

### Friday, Oct 22(2 hour):
#### Accomplishments
- Discovered something wrong with the code
  - how the time of the queries are measured is confusing.
  - It seems like for C++, measuing time using `duration_cast` inside and outside a function leads to certain difference.
  - Talking about this with the phd - seems like measuring time cost inside and outside a c++ function leads to quite a big difference.
