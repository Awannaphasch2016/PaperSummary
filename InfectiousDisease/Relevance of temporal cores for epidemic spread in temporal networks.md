*  #[[Research Paper]]
    - URL:: https://arxiv.org/pdf/2003.09377.pdf
    - Citation
        @article{ciaperoni2020relevance,
          title={Relevance of temporal cores for epidemic spread in temporal networks},
          author={Ciaperoni, Martino and Galimberti, Edoardo and Bonchi, Francesco and Cattuto, Ciro and Gullo, Francesco and Barrat, Alain},
          journal={Scientific reports},
          volume={10},
          number={1},
          pages={1--15},
          year={2020},
          publisher={Nature Publishing Group}
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

## [[Research Paper]] (Non Survey Paper)
    - [[Table of Content]]
    - [[Note to self]]
    - [[Summary]]
        * note 
            * only apply to paper that pass first read.
        * Tags:: (Complete citation: Key Words: General subject: Specific subject:)
        * [[Use case: What is take away knowledge that you can use in your work?]]
            * span-core mitigating strategy is used for graph protection task, but it required that temporal network is known therefore it is not helpful for a practical use where there are lots of uncertainty in the data. It is, however, according to the paper, span-core is the first attempt toward capturing "intermediate pattern" rather than only focus on nodes. 
        * [[Related work: what are referenced papers that closely related to the paper?]]
        * [[Data: what is data characteristic?]]
            * small network of real contact network data.
        * [[Technique: what are technique used in the paper?]] 
            * span-core mitigating strategy for graph protection
        * [[Context: what's the context for the paper]]
            * [[Application Domain]]
                * note
                    * basically "task" but expand to include whole domain application (use case).
                * it is application for theoretical network analysis on graph protection
            * [[Problem: What are exact problems that it solve?]]
                * graph protection
                    * the task is to minimize attacked/infected nodes by identify nodes and remove edges connected to the nodes 
            * [[Hypothesis]]
                * nodes in span-core are long-lasting groups of interacting individuals which mean influences are induced/enhanced by nodes members, as a result, it could detect high influence node that static network analysis cannot detect.
                * the paper assumes that nodes inside span-core have high influence, and as value of span-core increases, there are more chances that seeds inside span-core will have more influence on average.
            * [[Methodology results]]
                * nodes in span-core are shown to have high influence which mean removing its connected edges can mitigate risk of nodes being attacked.
            * [[what idea does the paper expand further?]]
            * [[Concept: what's the key contribution of the paper]]
                * note 
                    * concept answers 'what' paper does to solve the problem.
            * [[Implemntation: how does the paper implement thier core idea?]]
                * note
                    * implementation answers 'how' paper solve the problem.
                    * 'implementation' doesn't refer to the exact implementation, rather 'implementation' refers to 'how' authors materialize their core ideas. (key contribution)
            * [[Significance (to the field; in relation to your own work):]]
                * span-core is the first theoretical idea that is purposed to captured "intermediate pattern" rather than focusing on nodes individually.
            * [[Relevance: How is this relevant to you own work?]]
                * note
                    * make note only when you are working on something.
                    * explain your goal and what you are working on, then explain what can be helpful.
            * [[Visual: Important Figures and/or Tables (brief description; page number):]]
                * figure 1 
                    * [[re-written]] figure 1 observed value and duration of span-core from the beginning to the end. The goal is to understand how span-core forms within network without any inferences.
        * [[criticisms of the work]]
            * data contains only for a few minutes, so there are not information about contact network during the week and between days.
        * [[any other thoughts/comments]]
    - [[Introduction]]
        * A large body of work aims in particular at understanding how the network’s features
        impact the outcome of processes taking place on top of them, with the ambition of devising control and prediction capabilities.
            * For instance, several methods have been put forward to identify the nodes of a network that play a more important role in a
            spreading process, either because they are "influencers" able to widely spread an information, or because they are "sentinels"
            with a high probability to be reached by a disease in its early stages and thus can give an early warning, or because their
            immunization is likely to hinder the spread2–11 
        * Such a task (temporal grpah) becomes even more complex when dealing
        * with temporal networks, in which edges between nodes can
        appear and disappear on different time scales

        * The temporal dimension can yield non-trivial temporal features such as broad distributions of interaction times and of
        inter-event times ("burstiness"), heterogeneous activity distributions, causality constraints, and overall a broader diversity of
        activity/connectivity patterns than in static networks12–15
        * This has raised new questions on designing surveillance and control
        strategies for epidemic processes in temporal networks16–23. Identifying single nodes for the design of targeted interventions
        (immunization, isolation) can however be challenging in practice: indeed, centrality measures can fluctuate strongly over time
        and depend on details of the system that change in different periods; they might moreover be difficult to relate to interpretable
        features
                *  Data with limited resolution can also make it difficult to correctly identify the most central nodes24.u
                    * In particular,
                    several works17, 18, 21 have addressed the issue of designing causal interventions, in which node properties are measured until a
                    certain time and determine the nodes to immunize to contain a future spread. 
                        * . In practice, the impact of such strategies depends
                        strongly on the data set under study and is limited by temporal fluctuations in the centralities of nodes.
        * Moreover, action at the
        level of individuals is subjected to many informational and operational constraints.
        * Therefore, strategies based on intermediate scales have been advocated, targeting structures rather than single nodes, with
        the goal of identifying patterns that can be acted upon in practice
            * The idea in this case is to first identify potential structures
            of interest in (static or temporal) networks, and then verify that they play an important role in spreading processes:
                * step 1 
                    * this is
                    typically done by thought experiments in which one compares the outcome of a spreading process on the original network with
                    the outcome if the structure of interest is altered or removed.
                    * Alternatively, one can seed the process from the structure and
                    investigate the spreading power of nodes of the structure
                * step 2
                    * A second important step is to relate the structures to interpretable
                    features of the system of interest
                        * Examples of such
                        structures include groups or communities in the population, in which individuals have more contacts with each other than with
                        the rest of the population, leading to the proposal of reactive measures of class closure22, 25, or sets of links with correlated
                        activity patterns23
                * step 3 
                    * the third step is to use this knowledge to propose actionable strategies
        * The nodes belonging to the more central cores have
        been shown to play an important role in standard theoretical models of
        epidemic spreading processes on static networks
        \cite{castellano2012competing, kitsak2010identification}


    - [[Summary]]
    * [[Future Read]]
    - [[Key Contribution]]
        * Here, we contribute to the first, most theoretical step of this line of research by proposing a novel type of candidate
        structures for idealized targeted interventions: the span-cores of a temporal network

         - Finding
              - {{query: {and: [Finding][Name of this Paper]}}}
    - [[Grounded Claim]] 
    - [[Future Direction]]
    - [[Standard/Benchmark]]
        - [[Data]]
            * note
                * all data is collected from 
                    * SocioPatterns30 gathers longitudinal data on physical proximity
                    and face-to-face contacts of individuals in different contexts using a sensing platform based on wearable badges equipped with
                    radiofrequency identification devices (RFIDs). Contact data are collected with a temporal resolution of 20 seconds.
                    * Further
                    data describing human proximity are provided by Toth et al.31, who deployed a platform composed of wireless ranging enabled
                    nodes (WRENs) in several schools in the USA. Each WREN collects signals from other WRENs in proximity at intervals of
                    approximately 20 seconds. Signal strength criteria are used to select pairs of individuals wearing these WRENs located at
                    distance lower than or equal to 1 meter: this is the practical definition used to define a contact between individuals at each time.
                    For each data set, we aggregate all interactions in successive time-windows (timestamps) of 300 seconds. We thus obtain from
                    each data set a temporal network in which nodes represent individuals, and a temporal edge is drawn in a timestamp t between
                    two nodes if the two corresponding individuals have been in contact in this time-window.
            * 8 dataset describing human interactions with high spatial and temporal resolutions in a variety of contexts.
                * primary school 
                * high school
                * hospital 
                * conference
                * SFHH
                * workplace
                * elementary
                * middle school
    - [[Tool]]
    - [[Related Work]]
        * The recent availability of time-resolved data sets of interactions has pushed
        network science beyond the static graph representation and has led to the development of the field of temporal networks12, 13
        * Reactive school closure weakens the network of social interactions
        and reduces the spread of influenza
        * Revealing latent factors of temporal networks for mesoscale intervention
        in epidemic spread.
    - [[Defining Equation, Notation, Terminology, Theory, and Law]]

        -[[Terminology]]
            * core-decomposition 
                * We recall that the core-decomposition of a static network yields a hierarchy of
                subgraphs that are increasingly densely connected:
                    * a core with coreness k is defined as the maximal subgraph such that all
                    nodes within it have degree (number of neighbors in the core) at least k
                    27
            * span-core
                * In temporal networks, the span-cores are defined26 as temporal subgraphs as follows: a span-core C of order k is defined
                on an interval ∆ of contiguous timestamps, such that all nodes in C have at all timestamps of that interval at least k stable
                neighbours in C (i.e., the links to these nodes are present during all timestamps of the interval).
                    * Each span-core is thus
                    characterized by two quantities:
                        * its order
                        * its duration 
            * spreading maximization
                * which choice of the initial seed and tiem of the spread leads to the largest spread. 
            *
            -[[Notation]]    
    - [[How does researcher think of this research idea?]]
    - Challenges
        - [[Challenges]]
            * We discuss
            some limitations and perspectives in the Discussion section, in particular concerning the need to know the temporal network in
            advance to find the span-cores, showing that one has to be able to interpret the span-core structures in order to translate this
            theoretical knowledge into actionable strategies.

        -  {[[query]]: {and: [[Challenges]] [[Name of this paper]]}}
    - [[Approach]]
        - [[Purpose]]
        - [[Tasks]]
            * task 
                * performs 2 types of experiments
                    * impact of the removeal of maximal span-cores with large order and/or duration on spreading processes in a variety of empirical temporal networks.
                        * We quantify this impact by
                        the resulting decrease in epidemic risk and compare the removal of span-cores to random baselines and to the isolation of
                        nodes based on properties in the static aggregated network known to be relevant to spreading processes4, 28
                * As mentioned in the introduction, two complementary questions are typically investigated in order to test the role of nodes
                or structures in spreading processes: how to best contain or mitigate a spread, and which seed(s) have the largest spreading
                power?
                * [[there are more]] mitigation strategies
                    * These interventions consist in removing temporal edges in the network,
                    and different strategies consider different ways of choosing the edges to be removed
                    * As the maximal cores can be classified along two properties, their order and their durations, we consider in fact two separate
                    strategies:
                        * The top-k maximal span-cores strategy (for short kM) removes temporal edges starting from the maximal span-cores
                        with highest order, independently of their duration
                        * The top-∆ maximal span-cores strategy (for short ∆M) removes temporal edges starting from the maximal span-cores
                        with longest duration, independently of their order
                * seedling strategies
                    * The idea underlying the proposed procedure is
                    that nodes that represent influential spreaders are likely to belong to the span-cores of highest order at the timestamp in which
                    the spread begins
        - [[Evaluation]]
            * final size of the epidemic 
                * In the spreading mitigation scenario, our aim is to compare the unfolding and impact of these processes, for each data set,
                on the original temporal network and on temporal networks modified according to several intervention strategies
                    * We first consider the value of the epidemic threshold, i.e., the critical value
                    of disease transmissibility β above which the spread is able to reach a large fraction of the population
                        * The analytical method
                        developed by Valdano et al.32, based on the approximation of the process by a Markov chain, allows to express the epidemic
                        threshold for both processes in terms of the spectral radius of a matrix that encodes both network structure and disease dynamics
                    * We moreover consider the final size of the epidemic, i.e., the fraction of nodes that have been reached by the process when
                    it ends
                        * We then compute the epidemic size ratio for each strategy and parameter values, defined as the
                        ratio between the average epidemic size for processes on the reduced temporal network obtained according to a strategy and the
                        average epidemic size for processes on the original temporal network
                    * n compute the epidemic size ratio, in which the numerator and denominator are given by the average epidemic sizes for
                    processes seeded according to a strategy and for randomly seeded processes, respectively
                * for SIR
                    * d we compare (for the SIR case) the average final epidemic size in
                    both cases.

        - [[Architecture]]
            * a series of publicly available data sets describing temporal networks of particular relevance for epidemic spreading scenarios, namely high-resolution social network data on face-to-face interactions in a variet 
                *  This allows us to study data with a broad variety of structural and temporal patterns. The data sets we consider are
                all represented as temporal networks on discrete timestamps: nodes represent individuals, and a temporal edge (i, j,t) between
                two nodes i and j in time window t corresponds to the fact that these two nodes have been in contact during that time window.
            of settings, collected independently by two different collaborations30, 31
            * SIS and SIR are used as spreading process.
                * SIS
                    * A susceptible node in contact with an infected one becomes
                    infected with a fixed probability β per unit time. Infected nodes recover with a constant rate ν and become susceptible again.
                    The system can thus either reach a steady state in which there is constantly a finite fraction of the nodes in the I state, or the
                    epidemic can die out if all nodes recover. In the SIR model, nodes that recover enter the Recovered (R) class and can no longer
                    take part in the epidemic process
                * In the SIR model, nodes that recover enter the Recovered (R) class and can no longer
                take part in the epidemic process.
                    * Therefore, no steady state can be reached: the epidemic process ends when no more infected
                    nodes are present, and all nodes are then either susceptible (those who have not been reached by the disease) or recovered
            *  The span-cores are structures that we
            recently introduced26 to decompose a temporal network into hierarchies of subgraphs of controlled duration and increasing
            connectivity, generalizing the core-decomposition of static graphs
                * They could thus in temporal contact networks be interpreted
                as long-lasting groups of interacting individuals. 
                *  In reference26, we have introduced the definition of span-cores
                and maximal span-cores, devised efficient algorithms to extract them from data, and performed a preliminary analysis of their
                properties in several data sets
                * Maximal span-cores are thus well-connected stable groups of nodes, and can be considered as natural candidates when
                looking for structures having an important role in spreading processes on temporal networks.
    - [[Experiments, Results and Analysis]]
        *  We show that the
        removal of links in the most connected and stable temporal cores has a particularly strong impact on the epidemic risk
            * Our results show that processes seeded in cohesive span-cores yield in general large epidemic sizes,
            even compared with several baseline seeding strategies based on properties known to be relevant such as static centralities1
        * the spreading power tends to increase with the order of the
        span-core to which the seed belongs
    - [[Finding]]
    - [[Frequently Ask Questions]]
         - {{query: {and: [Validate] [Name of the Page]}}}
    - [[Paper Reference]]
