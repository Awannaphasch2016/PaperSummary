# INTRODUCTION
# REFERENCES
* url 
    * https://arxiv.org/pdf/2102.08122.pdf
# TERMINOLOGY
# RELATED WORK
# KEY CONTRIBUTION
* supervised representation of sitaution to learn a more appropriate presentation for a given analytical task.
* Dynamically looking ofr similar "infection situations" instead of sticking to a fixed periodicity could be a key to varied seasonlity and pandemics for influenza prediction.
# HOW AUTHOR COME UP WITH THIS IDEA
# FURTHER READING
# FUTURE DIRECTION
# CHALLENGES
# STANDARD AND BASELINE
# METHODOLOGY
* task 
    * one-step prediction and multi-step prediction.
* preprocessing
    * graph construction
        * virtual graph
            * different form a natural graph with static nodes and edges, virtual graph is defined as a set of nodes and edges in which every node an dedge are 
                supervisedly or semi-supoervisedly dynamically leanred during the training.
        * virtual edges
            * virtual edges conencts two virutal nodes at two timepoints.
            * each edges describes the significnace of the similarity.
                * similarity is based on "infection-situation" embedding vectors
            * Virtual edges significnance
                * to a givne node, different neighbors may have different similarities in "infection situations", the significance of a virtual edge needs to be decided.
                * virutal edge significance between nodes are computed by performing inner product on the after linear project and instance normalization on the 
                    high-deminsional node embeding vectors of "infection-situtaions"
                * properties
                    * value is between -1 and 1
                    * self loop has value of 1
                    * virutal edge is non-directional.
            * virtual edges are calculated by measure simialrity between 2 virtual nodes. Formula can be seen below.
                ```
                    \begin{aligned}
                    t_{(v, u)} &=\kappa\left(s_{v}, s_{u}\right) \\
                    &=\text { inst_norm }\left[W_{\text {line_proj }} s_{v}\right] \odot \text { inst_norm }\left[W_{\text {line_proj }} s_{u}\right]
                    \end{aligned}

                    * where $t_{(v, u)}$ is the the significance of the virtual edge from the node $u$ to $v$, inst_norm $(\cdot)$ is the instance normalization,
                    $W_{\text {line_proj }} \in \mathbb{R}^{256 \times 2 \overline{5} 6}$ is the trainable weight of the linear projection and $\odot$ is the inner product.
                ```
            * each node can be trained to capture "infection situations'
            * the embedding of the virtual node, representing the comprehensive "infection situations" at the time point.
            * definition of "infection-situation"
                * infection-situation embedding vector needs to include comprehensive infective information, such as 
                    * the timing, severity, and duration of the infection at a given timepoint.
                    * the first -order differneces ("speed") and the secon-order differences ("acceleration") at a given timepoint
                    * tendency (upward, downward, fluctuation, or a turning point)
                    * descriptive statistics (mean, median, maximum, minimum, variance, and the like) at a given time point.
            * 2 layers MLP are applied to obtained node representation of "infection-situation"
# RESULT
# FREQUENCY ASK QUESTION 
