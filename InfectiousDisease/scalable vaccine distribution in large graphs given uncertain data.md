*  #[[Research Paper]]
    - URL:
        * https://dl.acm.org/doi/pdf/10.1145/2661829.2662088
    - Citation
        @inproceedings{zhang2014scalable,
          title={Scalable vaccine distribution in large graphs given uncertain data},
          author={Zhang, Yao and Prakash, B Aditya},
          booktitle={Proceedings of the 23rd ACM International Conference on Conference on Information and Knowledge Management},
          pages={1719--1728},
          year={2014}
        }
    - Status:: [[In Progress]]
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
        * for simulated data, distribution assumptions are vastly different.
        * dominator tree simplify problem by constructing its own "dominator tree" form the original graph.
            * greedy algorithm is applied on simplified graph
    - [[Citation]]
    - [[Summary]]
        * note 
            * only apply to paper that pass first read.
        * Tags:: (Complete citation: Key Words: General subject: Specific subject:)
            * #[[Grpah Mining]], #[[Uncertainty]], #[[Immunization]], #[[Diffusion]]
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
        *  However, in reality contagions usually spread over uncertain environments and the sources of such uncertainty are
        many.
            * For example, in public health, due to the so-called
            multi-layered surveillance pyramid [39, 16, 30] at each layer
            the number of detected infections is a fraction of the infections in the layer below it. Hence the total detected infections at the top of the pyramid is a fraction of the actual
            infections in the population at the bottom.
            * Another example is the likelihood ratios used in diagnostic testing [13]. For
            each a person who gets the negative test outcome, she has
            some probability that her test was a false-negative.
            * In social media, as externals we rarely get access to the complete
            cascade. 
                * Researchers usually have access to only a uniform
                sample of cases (e.g. the Twitter API).
                * In Facebook, most
                users keep their activity and profiles private.
            * Moreover, if
            only because of the extreme velocity of social media data,
            one has to resort to using only a sample of the data. Hence
            this implies that we will have to make do with only an uncertain snapshot
    - [[Summary]]
    * [[Future Read]]
        *  Dava: Distributing vaccines over large networks under prior information. 
        * For example, in public health, due to the so-called
        multi-layered surveillance pyramid [39, 16, 30] at each layer
        the number of detected infections is a fraction of the infections in the layer below it. Hence the total detected infections at the top of the pyramid is a fraction of the actual
        infections in the population at the bottom.
    - [[Key Contribution]]
        * We formulate the Uncertain
        Data-Aware Vaccination problem, which takes into account multiple natural uncertainty models arising from
        social media and epidemiology.
        * As the problem is NP-hard
        and hard to approximate within absolute error, we develop multiple polynomial-time algorithms of varying
        efficiency
        * Finding
            - {{query: {and: [Finding][Name of this Paper]}}}
    - [[Grounded Claim]] 
    - [[Future Direction]]
        * Extending our results to more general forms e.g. distributions factorizing over groups of nodes being infected is
        interesting future work.
    - [[Standard/Benchmark]]
        - [[Data]]
    - [[Tool]]
    - [[Related Work]]
        * Most previous works (see Related Work) for controlling propagation
        have concentrated on developing strategies for vaccination
        (node/edge removal) pre-emptively before the start of an epidemic
            * While very useful to provide insights in to which
            baseline policies can best control an infection, they may not
            be ideal to help make real-time decisions as the infection
            is progressing.
    - [[Defining Equation, Notation, Terminology, Theory, and Law]]
        -[[Terminology]]
            * footprint 
                * number of infected nodes at the end
            * benefit
                * number of nodes saved
            -[[Notation]]    
    - [[How does researcher think of this research idea?]]
    - Challenges
        - [[Challenges]]
        -  {[[query]]: {and: [[Challenges]] [[Name of this paper]]}}
    - [[Approach]]
        - [[Purpose]]
        - [[Tasks]]
            * uncertain [[Data-Aware Vaccination]]
                * design vaccine distribution algorithms under an uncertain environment with known information consisting of confirmed cases as well as a probability distribution of unknown cases.
                * aka immunization/vaccination in a network in presence of already infected nodes [46]
        - [[Evaluation]]
        - [[Architecture]]
            * uncertainty model
                * In this paper, we are concerned with the scenario when
                we know the underlying contact network, but we do not
                know the exact current infected state of the network
                    * One
                    source of uncertainty is public-health surveillance [39, 16, 34,
                    30, 12, 5]. 
                        *  Generally there are three types of surveillance:
                        population-based, health provider-based and lab-based
                        * Although different types of surveillance may have different
                        probabilities to miss the truly infected person, we can simply use a set of probabilities P (over the nodes) to model
                        such uncertainty
                    * Another example is the likelihood ratios
                    used in diagnostic testing; each a person has a probability p
                    that her test was a false-negative
            * Sample-cascade algorithm
                * Since UDAV is a stochastic optimization problem, we try to apply the SAA (Sample Average Approximation) [22] framework to solve it
                * The idea is to reduce the
                stochastic optimization problem to the deterministic version
                by sampling the uncertainty distribution to generate a finite number of deterministic cases
                    * Unfortunately, as we mentioned in the previous section, even the deterministic version
                    of UDAV is NP-hard
                    * [[therea are more]] solution from [46]
                        * Hence we leverage the solution in [46],
                        which utilizes a spanning tree called dominator tree, and
                        then find a suitable sub-modular structure to solve UDAV
                        approximately
                            * first merge all the infected
                            nodes in Gi into a super node I0 (I0 is infected).
                            * Dominator tree is applied on the graph
                * [[re-written]] after obtained simplified graph (), greedy algorithm is applied.  
                * Lemma 4 shows that we need worstcase O(|V|^2) samples to get accurate estimates. Hence SampleCas does not scale to large networks.
                    * the reason for slowness of the algorithm is because an SSA algorithm is applied on all sampling graphs.
            * Expect-Max: a faster algorithm
                * We first formulate an equivalent problem which
                uses the concept of a so-called ‘expected graph’
                    * base on that, we propose two different methods Expect-Dom
                    and Expect-Eig, measuring expected benefits of vaccinations
                        *  We show that these two methods are in fact complementary, and hence then propose Expect-Max, which is
                            sub-quadratic in running time (in nodes/edges).
                * Expect-DOM algorithm
    - #[[Experiments, Results and Analysis]] #[[Finding]]
    - [[Frequently Ask Questions]]
        * this paper
            * what is expected graph?
        - {{query: {and: [Validate] [Name of the Page]}}}
    - [[Paper Reference]]
