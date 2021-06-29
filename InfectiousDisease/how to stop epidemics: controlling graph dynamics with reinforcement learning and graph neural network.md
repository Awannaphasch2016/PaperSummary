*  #[[Research Paper]]
    - URL: https://arxiv.org/pdf/2010.05313.pdf
    - Citation:
        @article{meirom2020stop,
          title={How to stop epidemics: controlling graph dynamics with reinforcement learning and graph neural networks},
          author={Meirom, Eli A and Maron, Haggai and Mannor, Shie and Chechik, Gal},
          journal={arXiv preprint arXiv:2010.05313},
          year={2020}
        }
    - Status::
        - Tags::: 
            - [[Paper Keywords]]: 
                - Author::
    - [[Publication]]:
    - [[Published Date]]:
    - [[Date Submitted by the Author]]:
    - Content:: (link to saved copy in Pocket)
    - Abstract::
    - [[You May Want to See Also]]

* [[Research Paper]] (Non Survey Paper)
    - [[Table of Content]]
    - [[Note to self]]
    - [[Summary]]
        * note 
            * only apply to paper that pass first read.
        * Tags:: (Complete citation: Key Words: General subject: Specific subject:)
        * [[Use case: What is take away knowledge that you can use in your work?]]
        * [[Related work: what are referenced papers that closely related to the paper?]]
        * [[Data: what is data characteristic?]]
        * [[Technique: what are technique used in the paper?]] 
        * [[Context: what's the context for the paper]]
            * [[Application Domain]]
                * note
                    * basically "task" but expand to include whole domain application (use case).
            * [[Problem: What are exact problems that it solve?]]
            * [[Hypothesis]]
            * [[Methodology results]]
            * [[what idea does the paper expand further?]]
            * [[Concept: what's the key contribution of the paper]]
                * note 
                    * concept answers 'what' paper does to solve the problem.
            * [[Implemntation: how does the paper implement thier core idea?]]
                * note
                    * implementation answers 'how' paper solve the problem.
                    * 'implementation' doesn't refer to the exact implementation, rather 'implementation' refers to 'how' authors materialize their core ideas. (key contribution)
            * [[Significance (to the field; in relation to your own work):]]
            * [[Relevance: How is this relevant to you own work?]]
                * note
                    * make note only when you are working on something.
                    * explain your goal and what you are working on, then explain what can be helpful.
            * [[Visual: Important Figures and/or Tables (brief description; page number):]]
        * [[criticisms of the work]]
        * [[any other thoughts/comments]]
    - [[Introduction]]
        * 
    - [[Summary]]
    * [[Future Read]]
    - [[Key Contribution]]
        * To the best of our knowledge, this work is the first work that consider Deep RL in the
        context of a temporally evolving graph
        o Finding
            - {{query: {and: [Finding][Name of this Paper]}}}
    - [[Grounded Claim]] 
    - [[Future Direction]]
    - [[Standard/Benchmark]]
        - [[Data]]
            * [[therea are more]] stochastic block model (SBM) 
            * preferential attachment (PA)
            * contact-tracing networks
        * [[Evaluation]]
            * \% healthy
                * The percent of nodes kept healthy throughout the simulation.
            * \% contained
                * The probability of containing
                the epidemic. This was computed as the fraction of simulations having cumulative infected nodes smaller than
                a fraction α. We focus on this metric because it captures the important notion of the capacity of a health system
    - [[Tool]]
    - [[Related Work]]
        * Deep learning on graph 
            * traffic prediction 
                * Several works combine recurrent mechanisms with GNNs to learn temporal graph data, e.g., [16, 58, 11, 55] tackled the traffic forecasting
                problem .

        * ranking on graph 
            * The problem of ranking on graphs is a fundamental problem in Computer Science, in
            which the task is to rank the nodes of a given graph according to some criteria. It has various applications such
            as web page ranking [38, 3] and knowledge graph search [53].
        * Reinforcement learning on graph 
            * Recently, a surge of work combining Reinforcement Learning and
            graphs emerged. These works can be split into two main categories: leveraging graph structure for general RL
            problems (e.g., [56, 21]), and applying reinforcement learning methods for graph problems. Our work falls into
            the latter. An important line of work uses Reinforcement Learning to solve NP-hard combinatorial optimization
            problems defined on a graph [59, 5]. Another common application is the usage of RL for path searching in a
            knowledge graph [53, 6]. Reinforcement learning was also shown in a few other graph problems, such as
            chemical reaction prediction [7].
    - [[Defining Equation, Notation, Terminology, Theory, and Law]]
        -[[Terminology]]
            -[[Notation]]    
    - [[How does researcher think of this research idea?]]
    - Challenges
        - [[Challenges]]
        -  {[[query]]: {and: [[Challenges]] [[Name of this paper]]}}
    - [[Approach]]
        - [[Purpose]]
        - [[Tasks]]
            * We evaluate this approach in three types of socialnetworks: community-structured, preferential attachment, and based on statistics from real cellular tracking.
                * learning to
                perform local interventions to steer the global dynamics of a graph-based dynamical system.

        - [[Evaluation]]
        - [[Architecture]]
            * we design RLGN,
            a novel tractable Reinforcement Learning (RL) scheme to prioritize which nodes should be tested, using
            Graph Neural Networks (GNNs) to rank the graph nodes
            * the model must learn to handle two types of dynamics: 
                * note
                    * these two process operate on different time scales.
                    * combining RL with temporal graphs requires to stabilize how information
                    is aggregated from neighbors when updating nodes hidden states, and control how actions are sampled during
                    training to ensure sufficient exploration
                * learn to infer the potential risk of not removing a node
                * learn to predict the probability that a node becomes infected
            * assumption
                * s. First, we do not assume a node can be vaccinated or immunized against the epidemic 
                    * In other cases, such as human epidemics, it
                    is likely that factors such as underlying personal health condition (e.g, if a person is at increased risk) will be
                    the dominant factor in prioritizing vaccination.
                        *  Therefore, here we consider the problem at its pre-vaccination
                        stage, where every node is susceptible to the disease.
                * Second, we do not assume a node can be quarantined or disconnected from the graph without justification,
                namely, without a positive test result. It may be tempting to isolate a high-degree node from the network, like
                putting a bus-driver in quarantine or disconnecting a hub computer from the network, but we view this solution
                as problematic. Nodes perform required network functionality. Removing a load balancer without a proper
                replacement will substantially impair the computer network functionality. Quarantining a bus driver due to her
                connectivity pattern will result in either replacing the bus driver with another driver with the same interactions
                pattern, or the transportation network functionality will deteriorate. In other words, a preemptive node removal
                would either not affect the network connectivity or impair the network functionality. Therefore, we assume that
                a node can be put in isolation only after it tests positive for infection
                * Finally, most previous works considered a setup in which a single vaccination decision is taken at t = 0
                (with a possible delay execution), based only on the information available at t = 0 . In our setup, the agent
                needs to decide at each time step t on its testing policy, given the information available at t ≥ 0, which include
                the results of past actions. Furthermore, the agent is aware to the fact that it may take additional action at
                later times. The agent needs to balance between retrieving information (for better informed future decisions),
                maximizing the probability that the immediate intervention will be successful, and optimizing the long-term
                goal that depends the stochastic epidemic evolution, current action and future actions. The agent needs to
                optimize the trajectory of test allocations, where each decision is taken under different information setting. In
                contrast to other work, the agent need not only know where to test, but also when to test each node, in a partially
                observed setup with little information
            * the author has shown that it is suboptimal to choose algorithm that act upon nodes that are most likely infected.
                * the author give the following example
                    * note 
                        * the assumption account for delay + probability of nodes being infected from its neighbours (test is negative = 100 not infected, and vice versa), but it doesn't consider that misclassification could be caused by test itself.
                    * assume taht we test a single nodes at odd timesteps.
                        * If the node is identified
                        as infected, it is sent to quarantine and cannot further interact with other nodes.
                            * our goal is to minimize the number of infected nodes.
                    * [[re-written]] the author argues that, at the time step where nodes are likely to be infected. most papers assumes that node will be infected in the next time step, in fact, due to decision making delay (implies that infection and decision making cannot occurs at the same time step), node may already be infected, hence targeting these nodes resulted in suboptimal performance.
                        * This example illustrates that an optimal policy must balance two factors: the probability that the dynamics
                        is affected - that a test action yields a “positive”, and the future consequences of our action - the strategic
                        importance of selecting v1 vs. v2, expressed by the ratio m1/m2
                            * A policy targeting likely-infected nodes
                            will always pick node v1, but since it only focuses on the first term and ignores the second term, it is clearly
                            suboptimal. 
            * graph construction
                * node construction
                    * dynamic features
                        * all test results that were performed up the curren tiem stamps (including positive and negative test results) 
                    * static features
                        * topological graph centralities (betweenness, closeness, eigenvector and degree centralities) and random nodes features.
                            * [[Validation]] what is random nodes features?
                * edges construction
                    * transmission probability
            * RL Agent Ranking modules 
                *  Epidemic GNN.
                    * The spread of epidemic through point contact is modeled by a GNN E. 
                        * . As the epidemic
                        cannot spread by more than one hop per step, it is sufficient to model the spread with a single GNN layer.
                * Information GNN
                    * The score of a node is affected both by the propagation dynamics, and by the information available to the agent.
                        * e information can propagate long distance in the graph almost instantaneously. As a simple
                        example, consider nodes in a connected chain of (untested) nodes and note that they are statistically dependent.
                        As a result, revealing the state of one node immediately affects the distribution over all nodes in the chain.
                            * As discussed above, updated information on a node u a few hops away from node v may
                            abruptly change our beliefs on the state of v. Furthermore, this change may occur even if v and u did not
                            interact in the last time step but rather a while ago.
                                * they construction a multi-graph where where the set of edges between nodes v and u at time t are all the interactions that occurred
                                during the last τ
                                    * features of each edges are the interaction delay during the last τ, and tranmission probability.
                * Noamlziation in scale-free network 
                    * RNN are well-known to suffer from the problem of exploding or
                    vanishing gradients. This problem is exacerbated in a RNN-GNN framework used for RL algorithms, because
                    they may be applied for arbitrary long episodes, causing internal state to grow unbounded. This problem is
                    particularly severe if the underlying graph contains hubs (highly connected nodes). O
                        * One approach to alleviate
                        this problem, is by including an RNN like a GRU module, where the hidden state values pass through a sigmoid
                        layer. As the magnitude of the input grows, gradient become smaller and training slows down.
                    * GNN
                        * cale-free networks contain with high probability ”hub” nodes that have high-degree, namely O(n) neighbors. The presence of these hubs further aggravates this problem. As a simple case, consider a star graph with
                        a large number of nodes. In a GNN framework, it receives updates from a large number of neighbors and its
                        internal state increases in magnitude. 
                            * This problem can be solved by directly normalizing each node hidden state. We have experimented with
                            various normalization methods, and found that L2 normalization worked best, as shown in the next section.

                    
    - #[[Experiments, Results and Analysis]] #[[Finding]]
        * In the context of COVID-19 spread, we show that using the RL-GNN approach
        increases the fraction of healthy by 25% and allows for confining the spread of an epidemic 30% more often,
        and 3× times more often that using non-learned approaches.


    - [[Frequently Ask Questions]]
        - {{query: {and: [Validate] [Name of the Page]}}}
    - [[Paper Reference]]
