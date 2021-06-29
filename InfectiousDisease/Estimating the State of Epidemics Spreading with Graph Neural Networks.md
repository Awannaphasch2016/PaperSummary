* reference for this template
    * https://academia.stackexchange.com/questions/44786/strategies-to-remember-papers-that-you-read

# NOTE TO SELF
* this is usually used not to help remember content. Instead, its is used to make todo notes about my goals that required me to read this paper.
    * eg
        * comment about writing style when making survey papers
        * what content should be added where
# CITATION
@article{tomy2021estimating,
  title={Estimating the State of Epidemics Spreading with Graph Neural Networks},
  author={Tomy, Abhishek and Razzanelli, Matteo and Di Lauro, Francesco and Rus, Daniela and Della Santina, Cosimo},
  journal={arXiv preprint arXiv:2105.05060},
  year={2021}
}
# SUMMARY
* note 
    * only apply to paper that pass first read.
## Tags: Complete citation: Key Words: General subject: Specific subject:
* GNN/ simulation/ epidemic/ semi-supervised/ classification/ COVID19/
## what's the context for the paper
### Hypothesis
* GNN may be useful for estimating network generated based on SIERD model.
### Methodology results
## what's the key contribution of the paper 
* semi-supervised learning to predict distribution of SIERD classes.
* the paper demonstrate important of GNN to estimate generated network based on SIERD model.
### Summary of key points
### Significance (to the field; in relation to your own work):
* for the larger dataset (scenario 2) model misclassified susceptibles as infected.
    * the model over predict throughout the predicted time period.
    * [[validate]] I suspect that this is due to effect of class imbalance on dynamic network. 
### Important Figures and/or Tables (brief description; page number):
* result
    * figure 4,5,7 
## criticisms of the work
* the paper doesn't explains/demonstrate effect of class imbalance. 
## any other thoughts/comments
# INTRODUCTION
* Many natural and artificial systems can be described with models whose state
assumes value on a graph rather than on a standard Euclidean space. Within
this class of systems, the problem of estimating the full state from partial measurements is a very relevant one
* If the network follows linear and continuous
dynamics, standard techniques can be used
# REFERENCES
# TERMINOLOGY
# FUTURE READ
* graph data/model
    *  Several
    algorithms are being proposed that can extract the social structure from GPS
    localization and other mobility information provided by contact tracing apps
    (Ferretti et al., 2020; Cheng et al., 2020).
    * Data driven methods can then possibly be used to infer the graph topology itself (Segarra et al., 2017; Giannakis
    et al., 2018).
* inspiration
    * We consider a model for disease transmission inspired by recent modeling of
    Covid-19 Yang et al. (2020); He et al. (2020).
* the paper's result
    * stacking LSTMs layers
    in between the GNNs did not produce a statistically relevant increasing of the
    network performance and as such has not been included in the present work
    * the use of attention mechanisms (Veliˇckovi´c et al., 2017) have been
    tested but not included due to the negligible increment of performance that
    they resulted into
# RELATED WORK
# KEY CONTRIBUTION
# HOW AUTHOR COME UP WITH THIS IDEA
# FURTHER READING
# FUTURE DIRECTION
# CHALLENGES
# STANDARD AND BASELINE
# METHODOLOGY
* task 
    * only partial state (subset of nodes) are know.
        * predicting {S, E+I, R+D}
            * [[validate]] why does predicting E+I (contacted virus) and R+D (no more infected; nodes still existing in the network) together?

* validation 
    * note
        * masking 95 − 90 − 80% of nodes
    * validate on nodes that are outside of training subset of nodes (partial state)

* dataset 
    * 2 types of scenario 
        * note
            * the two have different topological
            characteristics. 
            * . It is again important to stress that the proposed algorithm is
            optimized to estimate the distribution of subjects rather than the total size of
            each class, which should therefore be regarded as a secondary index

        1. The first one is an homogeneous network, in which any node
        has the same probability of being connected with all the others.
            * We use this
            scenario to test extensively the effectiveness and scalability of the method
            * [[there are more]] generated from generative algorithm.
                * We
                showcase results for networks with average degree hki = 30. This value is
                comparable with the number of daily contacts at risk as measured in a recent
                survey (Melegaro et al., 2011)
            * we are training the neural architecture with
            a small-village community, and testing it with a medium size city
            * note
                * It is very important
                to stress here that these overall statistics serve here only to get a sense of the
                overall quality of the network predictions.
                    * The goal of the neural architecture
                    is indeed not to estimate these values directly, but the exact way in which
                    each class is spread over the social network

        2. The second scenario we consider aims at modeling a more realistic social structure, such as the one of a relatively big city.
            * note
                * multi-layer graph 
                    * where nodes of the lower layer are network.
            * We need to consider both a model
            that takes into account the existence of different neighborhoods and the age
            distribution of people living in that area.
                * We take as a reference the City of
                Boston and Cambridge, Massachusetts, USA.
            * [[there are more]] The generative model, which takes inspiration from the work in (Mistry
            et al., 2021),
                * Within each
                neighborhood, the topology reflects the contact patterns between different ageclasses, as described in the Supplementary material of (Mistry et al., 2021)
                * To
                do so, we cohort the population into age groups of size 5 years, and we model
                the contact patterns among groups based on their age with a stochastic block
                model (Holland et al., 1983). 
                    * . Stochastic block models are generative models for
                    random graphs that are use to generate topologies that have a community-like
                    structure
                * The Affinity matrix we use is the Massachusetts agecontact matrix, as described in the supplementary material of (Mistry et al.,
                2021). 
                * [[there are more]] The last step is to connect different neighborhoods by allowing nodes
                in each neighborhood to have links with nodes from other neighborhoods. To
                do so, we consider a diffusion-like procedure: for each couple of neighborhoods
                we place a random number of links between randomly selected nodes from
                both communities, depending on the length of the shortest path connecting
                the two on the geographical level
                

            * n. The size of each neighborhood is taken
            from the official website of the city of Boston1 and Cambridge2

* graph construction
    * undirected
* model
    * note
        * output is predicted per timestep
    * 3 stages
        * time and uncertainty encoding
            * sample data from the volution of the known nodes y in the past k days, and counts the occurence of the three classes.
                * In this way it creates labels l encoding the temporal information
        * convolutional layers
            * three graph convolutional
            layers
        * output layer
            * output is an estimation of the
            current full state of the epidemics spreading.
    * [[there are more]] to deal with unbalance, weighted class are used 

# RESULT 
* Finally, we believe that a very important assumption to
be relaxed is the full knowledge of the social network (see Sec. 3.1). 

* scenario 1 
    * Interestingly, the quality of the predictions do not change significantly with
    the size of M
    * Overall the performance is satisfactory, with a
    general accuracy always higher than 0.75.
    * The network is not
    sensitive to small deviations of S and R + D from the maximum and the minimum value. This may be due to the fact that so small variations may not be
    captured by changes in M.
    * [[validate]] [[see picture]] gnn predicted value change in direction more quickly 
        * performance on smaller network and bigger networks have similar shape.
            * No essential differences can be
            observed
            * Overall the performance is still satisfactory, with a general accuracy
            which is even higher than the previous test set and always equal to 0.83.
                * This
                may be due to the fact that larger social networks generate more homogeneous
                distributions of the illness since the border-effects are less dominant.
                * [[validate]] may be it is due to unbalance class.

* scenario 2 
    * Although lower
    in the easier scenario 1, the accuracy is consistently good across classes and
    conditions. 
        * Yet, the accuracy of S is a bit lower than before, and the precision
    of E + I is very low. This is because the neural architecture tends to
    wrongly label a number of nodes which are susceptible as infected.
        * [[see picture]] model tends to incorrectly predict infected cases and
            susceptible.
            * [[re-written]] this tells me that diffusion of the model is too fast per time step.
            * [[validate]] what is the effect of unbalance classes to
            classification in dynamical network?
        * this behavior of the model is benefitial in real worlds scenario.
            * Although not explicitly
            forced in training phase, this behavior makes very much sense in the practice
            since it is better to isolate healthy subjects than not to act on infected ones.
# FREQUENCY ASK QUESTION 
* this paper
    * what does "state" refer to?
* general
    * what is communication contraint in network?
    * what is affinity matrix
# CONTENT

