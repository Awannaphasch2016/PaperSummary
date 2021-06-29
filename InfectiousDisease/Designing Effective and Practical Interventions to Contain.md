# Tags
in-progress/ 

# NOTE TO SELF
* I have no clue how what the paper do with linear programming.

# SUMMARY
* note 
    * only apply to paper that pass first read.
## Tags: Complete citation: Key Words: General subject: Specific subject:
# citation 
@inproceedings{sambaturu2020designing,
  title={Designing effective and practical interventions to contain epidemics},
  author={Sambaturu, Prathyush and Adhikari, Bijaya and Prakash, B Aditya and Venkatramanan, Srinivasan and Vullikanti, Anil},
  booktitle={Proceedings of the 19th International Conference on Autonomous Agents and MultiAgent Systems},
  pages={1187--1195},
  year={2020}
}
## what's the context for the paper
### Hypothesis
### Methodology results
## what's the key contribution of the paper 
### Summary of key points
### Significance (to the field; in relation to your own work):
### Important Figures and/or Tables (brief description; page number):
## criticisms of the work
## any other thoughts/comments
# INTRODUCTION
# REFERENCES
# TERMINOLOGY
# STANDARD
## DATASET
* 3 classes of networks (6 in total) 
    * 2 random entworks
        * small world
        * preferential attachment 
    * We study the results on the CA-GrQc collaboration
    network [20], since it is a type of social network.
    * We
    also consider synthetic agent based populations for Montgomery
    County, VA, and Portland, OR, constructed by a first principles
    approach by [6, 11].
        * This network has a rich set of demographic attributes for each node, e.g., age, gender, and income. The datasets
        are summarized in Table 2.
# FUTURE READ
* Optimization in the SI/SIS type models,
in static or dynamic networks, e.g., [25, 27–30]. Much of this work
is based on controlling spectral properties, but does not give any
guaranteed bounds on the expected outbreak size
# RELATED WORK
* type of methods for EPICONTROL tasks 
    * Optimization in the SI/SIS type models,
    in static or dynamic networks
    * Firefighter
    problem, which can be viewed as EpiControl on SI model with
    with 𝑝 = 1
    *         * Static interventions in SIR models

# KEY CONTRIBUTION
# HOW AUTHOR COME UP WITH THIS IDEA
# FURTHER READING
# FUTURE DIRECTION
# CHALLENGES
# STANDARD AND BASELINE
# METHODOLOGY
* task
    * EPICONTROL
        * designing vaccination strategies to minimize the expected
            outbreak size in an SIR epidemic process on a network 𝐺 = (𝑉 , 𝐸)
            * We only focus on one stage (1sEpiControl) or two stage
    (2sEpiControl) versions of EpiControl here,
        * the paper introduced the following constraint: 
            * budget at each time step
* method 
    * linear programming rounding technique + simple average approximatino tehcnique fro mstochastic optimization.
# RESULT
We study the following questions:
* Scaling: how well does saaRound scale to large networks?
How effective are the techniques for choosing the number of
samples and pruning?
* Approximation Guarantees: what is the approximation factor of saaRound in practice? How does it compare with the
other baselines?
* Effect of multiple stages: how does the effectiveness of the
solution vary with the number of stages and the budget in each?
* Characteristics of the solutions: what kinds of nodes are
picked in the solutions at each stage?
# FREQUENCY ASK QUESTION 
# CONTENT
* this paper 
    * what is EPICONTROL?
    * saaRound?
    * how is graph used here?
    * sparsification step?
* general
    * how to use linear programming for epidemic?
        * it solve optimization problem.
    * SIR on graph?
    * what is firefighter problem?


