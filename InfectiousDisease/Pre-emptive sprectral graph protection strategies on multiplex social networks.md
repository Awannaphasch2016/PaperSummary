*  #[[Research Paper]]
    - URL: https://appliednetsci.springeropen.com/track/pdf/10.1007/s41109-018-0061-8.pdf
    - Citation
        * @article{wijayanto2018pre,
          title={Pre-emptive spectral graph protection strategies on multiplex social networks},
          author={Wijayanto, Arie Wahyu and Murata, Tsuyoshi},
          journal={Applied network science},
          volume={3},
          number={1},
          pages={1--24},
          year={2018},
          publisher={SpringerOpen}
        }
    - Status::
        - Tags::
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
        * put multiplex graph in the survey paper
        * for each methods in related work
            * categorized methods by network types, task.
                * task
                    * different assumption
                        * SIS, SEIR, SIHR
                            * using same SIS, addition assumption may be critical.
                    * simulation vs real data.
                    * small data vs large data.
                    * high resolution data vs low resolution (aggregated data)
        * add definition of multiplex into survey
    - [[Citation]]
    - [[Summary]]
        * note 
            * only apply to paper that pass first read.
        * Tags:: (Complete citation: Key Words: General subject: Specific subject:)
            * #[[Multiplex networks]] #[[Graph mining]] #[[Epidemic contagion]] #[[Node immunization]] #[[Multilayer networks]] #[[real network]] #[[SIS]] #[[Epidemic]] #[[graph protection]] #[[influence maximization]] #[[influence blocking maximization]] #[[Data-Aware Vaccination]]
        * [[Use case: What is take away knowledge that you can use in your work?]
            * the paper has provided evidence that multilayer framework can be proven to be effectively when applied in graph protection in static graph.
        * [[Related work: what are referenced papers that closely related to the paper?]]
            * model that solve the same problem
                * We find that MULTIPLEXSHIELD is scalable for large graphs and gives more effective protection compared with other competing
                methods such as Acquaintance Vaccination (AV) (Wang et al. 2015), Targeted Immunization Method (TIM) (Buono and Braunstein 2015), SpreadingDegree (Zhao et al. 2014) and
                            Random Immunization (Zuzek et al. 2015; Wu et al. 2016; Zhao et al. 2014).
        * [[Data: what is data characteristic?]]
            * directed and undirected small multi-layer dataset of equivalent sparsity.
        * [[Technique: what are technique used in the paper?]] 
            * Using Random walk normalized Fiedler vector to iterative mechanism to diffusion transmission.
                * Random walk normalized Fiedler vector are picked over symmetric
                normalized fielder vector  (laplacian) because  The author
                argues the reason for chosing randomw walk to determine Fiedler
                vector was that the resulting Fiedler vector was consistency
                across various graph structure and the vector maximize
                similarity within cluster when graph partition is performed.
                Furthermore, the author adds that symmetric normalized Fiedler
                vector provide no additional benefit to random walk normalized
                Fielder vector.
                    * $$\mathcal{L}_{s y m}:=D^{-1 / 2} \mathcal{L} D^{-1 / 2}=I-D^{-1 / 2} A D^{-1 / 2}$$
                    * $$\mathcal{L}_{r w}:=D^{-1} \mathcal{L}=I-D^{-1} A$$ 
        * [[Context: what's the context for the paper]]
            * [[Application Domain]]
                * note
                    * basically "task" but expand to include whole domain application (use case).
                * task objective is graph protection. 
            * [[Problem: What are exact problems that it solve?]]
                * it showed experimentally that multilayer network (currently under used) can be useful for static graph protection.
            * [[Hypothesis]]
                * methods that are based on multilayer network should be more
                accurate than methods based on single layer graph as single
                layer graph is a coarse approximation of reality and that
                multilayer network is the most accurate and generalized way to
                model real social network.
            * [[Methodology results]]
                * the purposed multilayer methods performed better than its baseline single graph methods.
            * [[what idea does the paper expand further?]]
            * [[Concept: what's the key contribution of the paper]]
                * note 
                    * concept answers 'what' paper does to solve the problem.
                * it justify effectiveness of using random walk normalized Fielder vector over symmetric normalized Fielder vector.
                * it proved that graph protection in multilayer network is NP-hard.
                * it shows possibility experimentally that multilayer has potential to be more effective while retained simplicity of algorithm. (major change is seen in graph construction not algorithmic design)
            * [[Implemntation: how does the paper implement thier core idea?]]
                * note
                    * implementation answers 'how' paper solve the problem.
                    * 'implementation' doesn't refer to the exact implementation, rather 'implementation' refers to 'how' authors materialize their core ideas. (key contribution)
                * it uses node-aligned multilayer network to represent real social network. 
            * [[Significance (to the field; in relation to your own work):]]
            * [[Relevance: How is this relevant to you own work?]]
                * note
                    * make note only when you are working on something.
                    * explain your goal and what you are working on, then explain what can be helpful.
            * [[Visual: Important Figures and/or Tables (brief description; page number):]]
        * [[criticisms of the work]]
    * [[any other thoughts/comments]]
    - [[Introduction]]
        * Constructing effective and scalable protection strategies over epidemic propagation is
        a challenging issue. It has been attracting interests in both theoretical and empirical
        studies. However, most of the recent developments are limited to the simplified
        single-layered network
            * . Multiplex social networks are social networks with multiple
            layers where the same set of nodes appear in different layers. Consequently, a single
            attack can trigger simultaneous propagation in all corresponding layers
                * Therefore,
                suppressing propagation in multiplex topologies is more challenging given the fact
                that each layer also has a different structure
        * Real-world networks reveal the existence of multiple levels relationships. For instance,
        in social networks, an individual can possess membership of several communities which
        range in different functionalities from intimate (e.g., families, friends, clubs) to more serious (e.g., businesses, schools)
            * In social networks, one can categorize edges based on the
            nature of the relationships (i.e., ties) or actions that they represent (Kivela et al. 2014).
            Reducing a social system to a network in which actors are connected in a pairwise fashion
            by only a single type of relationship is often a crude approximation of reality.
            * Furthermore,
            the current insights in complex network analysis does not only consider networks as isolated graphs, but also characterizes how a network interacts with other networks and how
            this interaction affects epidemic spreading that occur on top of them (Kivela et al. 2014).
    - [[Summary]]
    * [[Future Read]]
        * multiplex network 
            * Kivela M, Arenas A, Barthelemy M, Gleeson JP, Moreno Y, Porter MA (2014) Multilayer networks. J Complex Netw
            2(3):203–271
            * Epidemic outbreak for an sis model in multiplex networks with immunization
        * model that solve the same problem
            *             * We find that MULTIPLEXSHIELD is scalable for large graphs and gives more effective protection compared with other competing
                        methods such as Acquaintance Vaccination (AV) (Wang et al. 2015), Targeted Immunization Method (TIM) (Buono and Braunstein 2015), SpreadingDegree (Zhao et al. 2014) and
                                    Random Immunization (Zuzek et al. 2015; Wu et al. 2016; Zhao et al. 2014).

    - [[Key Contribution]]
        * We formalize the problem of suppressing propagation spreading in multiplex network by
        allocating protection resources throughout the different network layers. We define the
        Multiplex Graph Protection Problem as a discrete combinatorial optimization
        * We also
        introduce that the problem is NP-Hard. To the best of our knowledge, we are the first to
        analyze the hardness of this multiplex graph protection problem.
        * Furthermore, we also
        specify two different protection scheme to consider different epidemic spreading scenario
        in multiplex networks.
        * We develop an effective and scalable algorithm to suppress the epidemics spreading on
        multiplex networks, called MULTIPLEXSHIELD
            * We find that MULTIPLEXSHIELD is scalable for large graphs and gives more effective protection compared with other competing
            methods such as Acquaintance Vaccination (AV) (Wang et al. 2015), Targeted Immunization Method (TIM) (Buono and Braunstein 2015), SpreadingDegree (Zhao et al. 2014) and
            Random Immunization (Zuzek et al. 2015; Wu et al. 2016; Zhao et al. 2014).
            * We also show that
            MULTIPLEXSHIELD is scalable with respect to the changing of graph size in terms of
            number of nodes and edges, which means it is suitable for large size graphs.
        - Finding
            - {{query: {and: [Finding][Name of this Paper]}}}
    - [[Grounded Claim]] 
    - [[Future Direction]]
    - [[Standard/Benchmark]]
        - [[Data]]
            * real multiplex network datasets
                * Florentine Families consists of 2 layers (marriage alliances and business relationships)
                describFlorentine Families consists of 2 layers (marriage alliances and business relationships)
                describing Florentine families in the Renaissance (Padgett and Ansell 1993).
                * Krackhardt HighTech is the multiplex social network between managers of a
                high-tech company consists of 3 kinds of relationships (Advice, Friendship, and
                “Reports to”) (Krackhardt 1987).
                * Vicker 7thGrader is the multiplex social network of 29 seventh grade students in a
                school in Victoria, Australia (Vickers and Chan 1981).
                * Lazega LawFirm dataset is the multiplex social network consists of 3 kinds of
                (Co-work, Friendship and Advice) between partners and associates of a corporate law
                partnership (Lazega 2001).
                * Physicians Innovation is the dataset representing the multiplex social network of a
                sample of physicians in 4 US towns: Illinois, Peoria, Bloomington, Quincy, and
                Galesburg (Coleman et al. 1957).
                * C.Elegans represents the multiplex neuronal network of the nematode
                (“Caenorhabditis Elegans”) which consists of 3 layers corresponding to different
                synaptic junctions: electric (“ElectrJ”), chemical monadic (“MonoSyn”), and polyadic
                (“PolySyn”) (Chen et al. 2006).
                * Kapferer TailorShop is the dataset of interactions in a tailor shop in Zambia (then
                Northern Rhodesia) over a period of ten months. Layers represent two different typesing Florentine families in the Renaissance (Padgett and Ansell 1993).
                * Krackhardt HighTech is the multiplex social network between managers of a
                high-tech company consists of 3 kinds of relationships (Advice, Friendship, and
                “Reports to”) (Krackhardt 1987).
                * Vicker 7thGrader is the multiplex social network of 29 seventh grade students in a
                school in Victoria, Australia (Vickers and Chan 1981).
                * Lazega LawFirm dataset is the multiplex social network consists of 3 kinds of
                (Co-work, Friendship and Advice) between partners and associates of a corporate law
                partnership (Lazega 2001).
                * Physicians Innovation is the dataset representing the multiplex social network of a
                sample of physicians in 4 US towns: Illinois, Peoria, Bloomington, Quincy, and
                Galesburg (Coleman et al. 1957).
                * C.Elegans represents the multiplex neuronal network of the nematode
                (“Caenorhabditis Elegans”) which consists of 3 layers corresponding to different
                synaptic junctions: electric (“ElectrJ”), chemical monadic (“MonoSyn”), and polyadic
                (“PolySyn”) (Chen et al. 2006).
                * Kapferer TailorShop is the dataset of interactions in a tailor shop in Zambia (then
                Northern Rhodesia) over a period of ten months. Layers represent two different types
                of interaction, recorded at two different times (seven months apart) over a period of
                one month (Kapferer 1972).
                * CS Aarhus is the multiplex social network consists of five kinds of online and offline
                relationships (Facebook, Leisure, Work, Co-authorship, Lunch) between the
                employees of Computer Science department at Aarhus (Magnani et al. 2013).
        * [[Evaluation]]
            * effectiveness
                * percentage of survived nodes of graph at the nd of epidemic 
            * scalability
                * dependends on graph size (nodes and edges) and different budget size
        * [[Models]]
            * note
                * all of the model are based on multiplex network
            * Random Immunization
            * Acquaintance Vaccination (AV)
            * Targetted Immunization Startegies (TIM)
            * Spreading Degree
    - [[Tool]]
    - [[Related Work]]
        * note 
            * To summarize, none of these literatures focused on the study of suppressing the
            epidemic spreading via pre-emptive spectral graph protection in multiplex networks.

        * [[Graph Protection]]
            * Most of the recent work in graph protection focused on the single-layered graph
            and does not provide much consideration on multiplex topologies.
                *  In single-layered
                graph protection scheme, there are two common approaches: pre-emptive and postemptive protection
                    * pre-emptive protection
                        * matrix perturbation 
                            * Two pre-emptive algorithms have been proposed, called NetShield
                            (Tong et al. 2010) and Netshield+ (Chen et al. 2016) which employ the properties of
                            matrix perturbation to find a set of nodes to be immunized (Tong et al. 2010).
                        * taking into account the role of infection flow, graph connectiviity, and out-degree centrality
                            * In 2017, GraphShield method was
                            proposed by taking into account the role of infection flow, graph connectivity, and outdegree centrality (Wijayanto and Murata 2017)
                    * post-emptive protection
                        * Meanwhile, some approaches to postemptive graph protection also have been proposed in (Zhang and Prakash 2014; 2015;
                        Song et al. 2015). Zhang and Prakash (2014; 2015) introduced DAVA and DAVA-fast,
                        two polynomial-time heuristics algorithms
                            * NIIP (Song et al. 2015) extracts a maximum directed acyclic graph from the graph then performs a Monte Carlo simulation
                            to estimate the distribution of k over each time point t given the probability of a
                            healthy node being infected

                * multiplex graph protection
                    * note 
                        * All of these works on multiplex graph protection assumed that the infection would
                        start from a random node, which called random attack
                            * In contrast, our work enhances
                            this assumption by also investigating the more powerful type of attack, targeted highdegree attack.random
                    * random immunization 
                        * Zuzek et al. investigated
                        random immunization method to protect k random functional nodes (Zuzek et al. 2015;
                        Wu et al. 2016; Zhao et al. 2014). Wang et al. proposed acquaintance method which
                        selects a set of random neighbor of a randomly chosen node (Wang et al. 2015)
                    * degree base node protection 
                        * Buono et al employed top k high-degree nodes for protection, termed Targeted Immunization Method (TIM) (Buono and Braunstein 2015).
                             Zhao et al. introduced
                             an improvement of TIM, called Spreading Degree (Zhao et al. 2014).
                    * method comparison based paper 
                        * , two
                        independent work investigated several protection methods and concluded in favor of
                        Explosive Immunization (EI) and Simulated Annealing (SA) methods (Osat et al. 2017;
                        Zhao et al. 2017). 
                            * Explosive Immunization (EI)
                                * The former method removed all the vertices the gradually reinserted
                                to the network but aiming to prevent the formation of the giant connected component
                                (GCC), until a stage where the GCC formation is inevitable. To add a new node, each
                                node is measured and then chosen by a predefined kernel function. A major disadvantage
                                of this method is that its total iteration get computationally costly, especially for large size
                                network (Osat et al. 2017)
                            * Simulated Annealing (SA) methods 
                                * The later method reintroduced one type of a traditional metaheuristic, which unfortunately not scalable and required a significant amount of running
                                time to converge (Nourani and Andresen 1998; Du and Swamy 2016). Thus, both of EI
                                and SA are not promising for large size network application.

        * [[influence maximization]]
            * The influence maximization task in multi-layered topology shares a similar goal with
            ours. It aims to find a set of vertices to control the influence propagation in the
            network.
                *  However, while the influence maximization task aims to maximize the influence spreading (Nguyen et al. 2013; Zhang et al. 2016; Zhang and Zhang 2015),
                the graph protection tries to encounter and limit those spreading process.
            * reduced network 
                * lossless
                    * Nguyen
                    et al. (2013) demonstrated a coupling scheme to reduce the multiplex graphs into a
                    single layer graph by maintaining the influence properties, therefore applying influence maximization task in the reduced network
                * lossy
                    *  Despite the benefit of that lossless
                    coupling scheme, Zhang et al. (2016) introduced a lossy coupling scheme of multiplex influence maximization to overcome the running time and memory consumption
                    issues.
        * [[influence blocking maximization]]
            * He et al. (2012) introduced the influence blocking maximization (IBM) problem to elaborate the competitive influence propagation in social networks under the competitive
            linear threshold (CLT) model
            * 
    - [[Defining Equation, Notation, Terminology, Theory, and Law]]
        -[[Terminology]]
            * center
                * We consider nodes that having the highest degree centrality role as centers.
            * bridges
                * We also assume nodes with
                the highest value of connectivity, measured by random walk normalized Fiedler vector
                (von Luxburg 2007), as bridges
            * task 
                * minimum k-union (MinKU) problem
                    * , we are given a set system with s sets and
                    have to select k sets to minimize the size of their union
                * [[there are more]] Data-Aware Vaccination (DAV)
                    * NP-hard proven by Zhang and Prakash (2014)
                * IBM problem 
                    * He et al. (2012) introduced the influence blocking maximization (IBM) problem to elaborate the competitive influence propagation in social networks under the competitive
                    linear threshold (CLT) model propagation of its opposing counterpart as much as possible by strategically selecting a set
                    of seed nodes to initialize its own influence
                        * IBM problem is another type of competitive
                        influence maximization under the constraint of opposing effect of each party’s influence.
                            * For instance, when a negative rumor spreads in the social network about an institution,
                            the institution needs to respond quickly by choosing other seed nodes to inject positive opinions about the institution.
                                * The positive opinions spreading are expected to fight
                                against the negative rumor. 
            -[[Notation]]    
        
    - [[How does researcher think of this research idea?]]
    - Challenges
        - [[Challenges]]
            *  our approaches may have limitations which rely on two essential assumptions: static network and pre-emptive protection
            scheme
                * static network 
                    * Firstly, we assume that the underlying network structure is static and remains
                    unchanged as the contamination spreading arises However, real-world social networks
                    evolve dynamically with some users joining and leaving the networks, and relationships
                    among users being formed and removed over time.
                * non-adaptive to infection budget 
                    * we spend all the available budget prior any infection occurs. Despite its effective
                    prevention, in existing large social networks such as Facebook and Twitter, protecting a
                    particular set of nodes adaptively against the occurring contamination is more realistic.
                    Instead of determining the set of protected nodes in a single time point, we can gradually
                    select a node to respond adaptively the new incoming contaminant which changes over
                    time.
        -  {[[query]]: {and: [[Challenges]] [[Name of this paper]]}}
    - [[Approach]]
        - [[Purpose]]
        - [[Tasks]]
            * Given a multiplex graph, such as a
            social network, and k budget of protection resources, we aim to protect a set of nodes
            such that the percentage of survived nodes at the end of epidemics is maximized
                * We define the
                Multiplex Graph Protection Problem as a discrete combinatorial optimization
            * 2 types of tasks
                * random nodes attack scenario
                * high-degree nodes attach scenario
            * multiplex [[graph protection]] problem 
                * it is NP-hard because MinKU (which is NP-Hard) can be think of as aan instance of multiplex graph protection problem in SIS model with beta = 1 and gamma = 1, and the number of layer L = 1.
        - [[Evaluation]]
        - [[Architecture]]
            * Thus, the protection scheme in multiplex networks can be classified into two basic
            classes: multiplex-based and layer-based node protection schemes. Figure 1 illustrates
            this classification
                * layer-based node protection scheme
                    * where each protected node is uninfectable by
                    its neighbors in a certain layer and meanwhile, its corresponding nodes in other
                    layers still can get infected by their neighbors
                        * This scheme can approximate the
                        situation when the protection means an isolated state from infection spreading
                        (Wu et al. 2016; Zhao et al. 2014). Thus, the isolation is only applicable in such layer.
                            * For instance, in a multiplex social network of neighborhood and colleague relationship, a person who is isolated from his/her office will lose connections to all of
                            his/her colleagues, but still likely keeps connected with his/her neighbors. Thus the
                            person is still infectable by his/her neighbors
                            * Another example, for a certain type disease without any proven
                            vaccination, one student may got instructed to wear face mask at school. But, he/she
                            may still got the disease from his/her neighbors.
                * Multiplex-based Node protection scheme
                    * where each protected node is uninfectable
                    during the contamination spreading in all corresponding layers. This scheme is most
                    suitable for multilayer graph where each individual nodes are in the same certain
                    awareness (Wu et al. 2016; Zhao et al. 2014). Thus, giving a protection to a certain
                    node will change its states of corresponding nodes in all layers
                        * [[re-written]] infected person is isolated in hospital
            * The goal of our work is to develop an effective and efficient method that is scalable
                    for protecting multiplex networks.
                    * Firstly, we allocate a novel nodes importance ranking
                    score which combines the benefit of algebraic connectivity and degree centrality of graph
                    structure
                    * 
            * This node score consists of the corresponding random walk normalized Fiedler vector of nodes in graph, degree value, and
            layer-wise epidemic stochastic propagation rate.
            * We use SIS model in our work. In SIS
            propagation model (Gray et al. 2011), we calculate the stochastic propagation rate from
            the ratio between the infection probability of one node to infect its neighbor and the
            recovery probability of infected node. This rate represents the strength of propagation
            and exhibits how quick the epidemics will spread. Prakash et al. (2011) showed that the
            strength of propagation in SIS model, as well as in SIR, SIRS, and SEIR model depends on
            this rate
            * Multiplexshield
                * goal 
                    * disconnecting spectral clusters of graph.
                * node ranking
                    * we introduce this ranking based on three objectives.
                        * [[bridges]]
                            * Firstly, we aim to determine the nodes having the role as bridges connecting sub structures or spectral clusters in graph
                            * Inspired by the benefit of algebraic connectivity of
                            graph, graph partitioning task and spectral clustering problem, we propose the random
                            walk normalized Fiedler vector to find such nodes in multiplex graph.
                                * We clarify our proposal of involving the random walk normalized Fiedler
                                vector as follows. (reasons why random walk is chosen)
                                    * Graph partition point of view
                                        * mincut problem
                                            * 2 common objective function has been proposed to improve the partition quality 
                                                * RatioCut
                                                * NCut
                                    * Statistical consistency
                                        * Looking at the statistical consistency differences between the two normalized Fiedler
                                        vector of Lrw and Lsym,
                                            * von Luxburg (2007); von Luxburg et al. (2008) investigated the
                                            spectral clustering algorithms results of Lrw and Lsym.
                                                * However, the eigenvectors of Lsym are additionally multiplied
                                                with D1/2, which might lead to undesired convergences.
                                                * Empirical results of spectral clustering are also in favor of Lrw.
                                                * As using Lsym does not have any computational benefits,
                                                selecting Lrw is more preferable.
                                * Regular and irregular graph applicability
                        * [[center node]]
                            * We assume
                            that this role can be determined based on the highest degree centrality value of nodes
                            * . Regard to the directed multiplex networks, the outdegree centrality is preferable. Outdegree centrality counts the number of
                            neighbors that a certain node can infect
                        * layer-wise epidemic stochastic propagation rate
                            * We propose to calculate the layer-wise stochastic propagation rate from the
                            ratio between the infection probability of one node to infect its neighbor and the recovery
                            probability of infected node. This rate represents the strength of propagation and exhibits
                            how quick the epidemics will spread
                                * SIS
                                    * In multiplex network, stochastic propagation rate of layer-wise epidemic
                                    spreading is defined by β/\gamma
                                        * \beta = infection probability
                                        * \gamma = recovery probability

    - #[[Experiments, Results and Analysis]] #[[Finding]]
    - [[Frequently Ask Questions]]
         - {{query: {and: [Validate] [Name of the Page]}}}
    - [[Paper Reference]]
