fritz2021combining
    Combining Graph Neural Networks and Spatio-temporal Disease Models to Predict COVID-19 Cases in Germany
    kapoor2020examining
        Examining covid-19 forecasting using spatio-temporal graph neural networks
    gao2020stan
        Stan: Spatio-temporal attention network for pandemic prediction using real world evidence
wang2020using
    Using Mobility Data to Understand and Forecast COVID19 Dynamics
deng2020cola
    Cola-GNN: Cross-location Attention based Graph Neural Networks for Long-term ILI Prediction
cao2020spectral
    Spectral Temporal Graph Neural Network for Multivariate Time-series Forecasting
znhea% for each paper, how is spatial graph construction ng2021dynamic
    Dynamic Virtual Graph Significance Networks for Predicting Influenza

Dynamic Knowledge Graph based Multi-Event Forecasing.
Epidemic Graph Convolutional Network

==mention what type of node an d edges are used. (mentioned along with main paper)

Combingin Graph Neural Netowrks and Spatio-temoral Disease Models to Predict COVID-19 Cases in Germany
    panagopoulos2020transfer
        Transfer Graph Neural Networks for Pandemic Forecasting
== read content on node immunization ==

In single-layered, 
graph protection scheme, there are two common approaches: pre-emptive and postemptive protection.
NetShield \cite{tong2010vulnerability} and NetShield+ \cite{chen2015node} were proposed as
pre-emptive algorithms employing the properties of matrix perturbation to find a set of nodes to be
immunized (Tong et al. 2010).
Taking into account the role of infection flow, graph connectiviity, and out-degree centrality
GraphShield method was proposed by taking into account the role of infection flow, graph
connectivity, and outdegree centrality. \cite{wijayanto2017flow}
Meanwhile, for postemptive graph protection, Zhange and Praskash introduced polynomial-time
heuristics algorithms DAVA \cite{zhang2014dava} and DAVA-fast. \cite{zhang2015data}
Song et al. \cite{song2015node} implemented NIIP to extract a maximum directed acyclic graph from
the graph then performs a Monte Carlo simulation to estimate the distribution of k over each time
point t given the probability of a healthy node being infected.

In multiplex network setting, 
Zuzek et al.\cite{zuzek2015epidemic} investigated random immunization method to protect k random
functional nodes \cite{zuzek2015epidemic, wu2016epidemic, zhao2014immunization}.
Wang et al. \cite{zuzek2015epidemic} proposed acquaintance method which selects a set of random
neighbor of a randomly chosen node.
Buono et al \cite{buono2015immunization} employed top k high-degree nodes for protection, termed
Targeted Immunization Method. (TIM) 
Zhao et al. \cite{zhao2014immunization} introduced an improvement of TIM, called Spreading Degree.
Osat et al. \cite{osat2017optimal}, Zhao et al. \cite{zhao2017vital} investigated several protection
methods and concluded in favor of Explosive Immunization (EI) and Simulated Annealing (SA) methods.
EI removed all the vertices the gradually reinserted to the network but aiming to prevent the
formation of the giant connected component (GCC), until a stage where the GCC formation is
inevitable. To add a new node, each node is measured and then chosen by a predefined kernel
function. A major disadvantage of this method is that its total iteration get computationally
costly, especially for large size network. \cite{osat2017optimal}
Simulated Annealing (SA) methods reintroduced one type of a traditional
metaheuristic, which unfortunately not scalable and required a significant
amount of running time to converge \cite{nourani1998comparison}
Thus, both of EI and SA are not promising for large size network
application.

== classifiy into tables

graph types 
* large vs small
* theoritical vs practical entwork 
* simutation vs real 
    * simultated real vs simulated theoritical
    * real data of small cohort vs real data representing the whole population. 
* Epidimiology Diffusion assumption
    * SIS vs SIR vs ...
* multiplex network (a type of multilayer network) vs single layer network
* homogeneous nodes vs heterogeneous nodes 
* homogeneous edges vs heterogeneous edges 

tasks
* uncertainty vs certainty
* node immunity vs graph protection vs influence maximization
* data-aware vaccination
* uncertain data-aware vaccination
* practical vs theoritical
* pre-emptive vs post-emptive
* predicting distribution vs actual number
* is budget (# of vaccine per time step) provided?
* decision making 
    * note
        * I feel like all of the RL based model that let agents make decision to suppress spread are all in this category. 
        * this is simply node/edges ranking problem on temporal graph?
    * balancing between mobility and infected cases.
        * song2020reinforced
    * time delay before information and decision making?
        * 
    * vaccinated with/without test
    * test distribution
        * meirom2020stop 
    * vaccines distribution

* control diffusive process.
* firefighter problem

* tasks found in related work 
    *  influence blocking maximization
        * social network 
        * malware protection.
    * theoritical
        * graph cut
        * stochasitic 
    * multilayer
        * a type of graph

* validation process
    * note 
        * most of these validation are done by comparing methods from graph that strategy has been applied to original graph.  
    * survival ratio
    * final size of epidemic (footprint)
        * i.e., the fraction of nodes that have been reached by the process when
                 it ends
        * often average epidemic size is computed.
        * paper 
            * ciaperoni2020relevance
    * benefit ()
    * contained. 
        * 

* parameters related to epidemic spread.
    * layer-wise epidemic stochastic propagation rate. (ratio betweeen the
    probability of the target node infect its neighbors and recovery probability of a target node)


* graph contruction
    * is simulated?
        * note
            * usually make graph larger with properties of real graph being maintained 
    * real
        * data collection styles
            * Infection tracing vs contact tracing vs and diary-based studies.
    * nodes 
        * 
    * edges 
        * edges = time of the interactions
            * transmission probability 
                * meirom2020stop

* images
    * exapmle of mini newtork, micro network, mezzo network (heterogenous node network; multilayer network), macro network.
    * I should visualize tasks/objective. 
    * provide figure 2 of meirom2020stop

FAQs
* why does phase tranition important in ocmplex networks? 

==============
* papers that i have already sumamrized
    * ciaperoni2020relevance
    * tomy2021estimating 
    * cohen2003efficient
    * meirom2020stop


Scale and Objective
    Dataset
    Real Network
    Idealized Network
    Pairwise approximation
Transmission Dynamic on Network
    Static Network 
    Dynamic Network
Simulation
    * Micro Network 
    * Mezzo Network
Network Construction
    Multilayer Networks
    Temporal Networks
Node Construction
    Micro Network
    Mezzo Network
    Macro Network
Edge Construction
    Micro Network
    Mezzo Network
    Macro Network
Feature Encoding
    Graph Embeddings
    Node Embeddings
    Edges Embeddings
