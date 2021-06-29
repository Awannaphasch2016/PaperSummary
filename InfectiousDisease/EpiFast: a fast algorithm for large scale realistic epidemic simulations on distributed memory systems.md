*  #[[Research Paper]]
    - URL:
    - Citation
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
    - [[Summary]]
    * [[Future Read]]
    - [[Key Contribution]]
        * We propose a parallel algorithm, EpiFast, based
        on a novel interpretation of the stochastic disease propagation in a contact network. We implement it using a masterslave computation model which allows scalability on distributed memory systems.
        * EpiFast supports representation and reasoning
        about complex interventions and public policies. It can handle sophisticated interventions to allow realistic case studies.
        This distinguishes EpiFast from classical simulations based
        on percolation theory [17, 21].
        * EpiFast represents a novel
        interpretation of epidemic simulations. It is significantly different from the usual multi-agent based discrete event simulations. By using a simpler (yet realistic) disease model and
        restricting the set of interventions that can applied, EpiFast
        can use a pre-constructed contact network and avoid scanning agent activities in each step while delivering similar
        results with comparable details.
        * the EpiFast algorithm is scalable on almost any
        distributed memory system
        o Finding
            - {{query: {and: [Finding][Name of this Paper]}}}

    - [[Grounded Claim]] 
    - [[Future Direction]]
    - [[Standard/Benchmark]]
        - [[Data]]
    - [[Tool]]
    - [[Related Work]]
    - [[Defining Equation, Notation, Terminology, Theory, and Law]]
        -[[Terminology]]
            -[[Notation]]    
    - [[How does researcher think of this research idea?]]
    - Challenges
        - [[Challenges]]
            
            *  Scale and heterogeneity of social contact networks. For
            example, a social contact network spanning the New
            York region is comprised of approximately 20 million
            individuals. The contact patterns and individual attributes are highly heterogeneous. As a result interprocess communication patterns and load balancing
            are non-trivial.
            * The contact networks are dynamic and coevolve as a
            result of actions taken by individuals and interventions by public health officials. This implies that nonadaptive schemes for efficient partitioning will most
            likely not be efficient.
            * Use of these simulations in practical settings requires
            execution of a large number of replicates for a given
            combination of independent parameters. More importantly, a typical case study involves searching an extremely large parameter space that is best searched
            using adaptive designs. Factorial designs are practically impossible in such situations
        -  {[[query]]: {and: [[Challenges]] [[Name of this paper]]}}
    - [[Approach]]
        - [[Purpose]]
        - [[Tasks]]
        - [[Evaluation]]
        - [[Architecture]]
            * Models 
                * properties 
                    *  (i) large populations consisting of millions of individuals and their heterogeneous details, (ii) dynamic interactions between the disease propagation, the individual
                    behaviors, and the exogenous interventions, as well as (iii)
                    large number of replicated runs necessary for statistically
                    sound estimates about the stochastic epidemic evolution.
                    We find that EpiFast runs several magnitude faster than
                    another comparable simulation tool while delivering similar
                    results.
    - #[[Experiments, Results and Analysis]] #[[Finding]]
    - [[Frequently Ask Questions]]
        * what is multi-agent discrete event simulations?
        * what is the epidemic simulation problem?
        - {{query: {and: [Validate] [Name of the Page]}}}
    - [[Paper Reference]]
