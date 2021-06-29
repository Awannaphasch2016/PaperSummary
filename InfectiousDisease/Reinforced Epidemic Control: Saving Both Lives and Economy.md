* [[Research Paper]]
    - URL::
    - Citation
        * @article{song2020reinforced,
          title={Reinforced Epidemic Control: Saving Both Lives and Economy},
          author={Song, Sirui and Zong, Zefang and Li, Yong and Liu, Xue and Yu, Yang},
          journal={arXiv preprint arXiv:2008.01257},
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

* [[Research Paper]] 
    * [[Table of Content]]
    - [[Note to self]]
        * macro network
        * task 
            * control dynamic flow of infected cases.
        * mention that spatialtemporal model can adapted for case prediction task
    - [[Citation]]
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
        * The epidemic has always been a threat to human society by exposing
        us in front of a dilemma between saving lives or economy. The
        virus infects gathering people and spreads through daily commute
        [2, 24, 31]. Controlling the spread of the virus must cut off daily
        mobility, which is a pillar of the modern economy. For instance,
        the recent outbreak of COVID-19 has caused millions of infections
        and hundreds of thousands of death tolls. The epidemic forces many
        municipal governments to issue a stay-at-home order, which is a
        Fully LockDown (FLD) policy. FLD in most cities lasts for weeks
        thus deeply hurts the economy [3]. Some municipalities try to only
        quarantine symptomatic people and their close contacts at the early
        stage of the epidemic
            * In summary,
            the vast amount of complex individual mobility and asymptomatic
            infected people prevent current epidemic-control policies from
            cutting off virus spread without hurting the economy when private
            information cannot be fully captured.

            *  However, this infected-individual-quarantine
            policy would be only implementable when governments are able to accurately
            and comprehensively trace risky people.
                * It is also unreliable when there exist many asymptomatic infected people
                    * Current
                    computer-science explorations pursue using smartphone data to infer
                    and trace highly-risky people [7, 21]
                        * However, fully tracing individual mobility and contacts requires full coverage of smartphones and
                        further raises the concern of threatening privacy [5]
                            * According to
                            an investigation by the University of Maryland and The Washington Post, around 60% of respondents either prefer not sharing their
                            private information or do not own a smart phone [28]

        * It is possible to avoid an epidemic
        outbreak by heterogeneously limiting little inter-regional mobility.

        * Furthermore, the estimation is based on the regional aggregate demand for mobility and the regional epidemic statistics. Thus, private
        data is dispensable
    - [[Summary]]
    * [[Future Read]]
    - [[Key Contribution]]
        * we in this research demonstrate that a smart epidemic control
        policy is still available even if private mobility information is unavailable.
        * we develop a dynamic control framework to avoid an epidemic
        outbreak by limiting the probability of risky mobility’s occurrence
            * instead of targeting and limiting risky individual’s mobility according to private data, our framework estimates each urban region’s
            risk of having a high infected population and uses the estimation to
            control inter-regional mobility.
            * highly-risky inter-regional mobility will be limited to suppress the probability of infected people’s
            movement.
        * we bypass the privacy concern for smart epidemic control.
            * instead of directly tracing and quarantining risky individuals,
            we suppress the risk of an epidemic outbreak by estimating
            and restricting risky inter-regional aggregate mobility.
        * we develop durleca to dynamically generate customized
        control actions for inter-regional mobility, which allows a
        smart solution for the life-or-economy dilemma of epidemic
        control.
        * we propose innovative approaches to guarantee durleca’s
        capability. we design a novel gnn architecture that can fit
        the epidemic transmission dynamics. our rl reward function
        captures the nature of the trade-off relation between epidemic
        suppressing and mobility retaining, and reflects practical requirements. we also develop two rl exploration strategies
        that appropriately incorporate epidemic expert knowledge for
        guiding and stabling policy exploration.

        - Finding
            - {{query: {and: [Finding][Name of this Paper]}}}
    - [[Grounded Claim]] 
    - [[Future Direction]]
        * In this research, we do not consider the uncertainty of mobility and
        epidemic information when DURLECA explores epidemic policies
            * It asks for future work to explore the algorithm for searching a robust
            policy when the information is uncertain.
                * A practical policy has to
                be robust even if there exist errors in the input data
    - [[Standard/Benchmark]]
        - [[Data]]
            * real-world OD dataset
                * note
                    * The government also collects information about the number and location of current discovered patients.
                    Those pieces of information are used to determine the quotas for each
                    inter-regional mobility
                    * dataset cover 24-hours OD-flows for the whole month of January 2019
                * 1 months data is repeated 24 times 
        * [[Models]]
            * EP-Fixed 
                * we
                design EP-Fixed to give a fixed quota rate Xq to all interregional mobility during the whole epidemic period
                * We set
                Xq = {0.15, 0.2} in our experiments, as we find them at the
                boundary of successfully controlling the epidemic.
            * EP-Soft
                * We design an expert baseline following Equation
                (19), which softly depends on the historical mobility loss
                and the current hospitalized population H
                to determine
                whether to lock down a region
            * EP-hard
                * Without softly depending on the historical mobility loss, an expert can reopen a region if it has been locked
                down for successive Xt days.
            * EP-lockdown
                * The most robust and conservative policy is to
                lock down the whole city until the epidemic ends. To simulate
                it, we design an expert following Equation (19
                * e until the hospitalized population becomes zero.

    - [[Tool]]
    - [[Related Work]]
        * GNN for OD-flows 
        * Deep reinforcement learning
            * In [32], DQN was also used for node
            protection against epidemic under a single objective
            * Deep Reinforcement Learning
            (DRL) has been proved to be effective for control problems that
            have a large action space [16, 19, 29]
                * DQN [19] and DDPG [16] are
                two representative DRL algorithms, proposed for discrete control
                problems and continuous control problems, respectively.
            * To enable
            the agent to find an optimal solution, later works proposed to enhance
            exploration [8, 11, 23].
            * Imitation learning is another area of RL,
            where the goal is to enable the agent to behave like a human expert
            [12]. 
                * AlphaGo proposed to start from imitation but further explore
                to outperform expert [27]
    - [[Defining Equation, Notation, Terminology, Theory, and Law]]
        -[[Terminology]]
            * Origin Designation (OD) data.
                * As the name suggests, origin-destination (OD) data represents movement through geographic space, from an origin (O) to a destination (D). Sometimes also called 'flow data,' OD datasets contain details of trips between two geographic points or, more commonly, zones (which are often represented by a zone centroid).
            -[[Notation]]    
    - [[How does researcher think of this research idea?]]
    - Challenges
        - [[Challenges]]
            * First, urban
            mobility is vast and temporally varying, making it hard to target the
            really risky mobility
            * Further, the requirements of the policy’s practicality sophisticate the design of the epidemic-control policy
                * An implementable control policy cannot continuously quarantine the same
                urban region for too long.
            * Last but not the least, the search for policy
            is difficult
                * Due to the exponentially-increasing nature of epidemics,
                the number of future infections is a highly non-convex function of
                each previous decision, making it hard to explore the policy space.
                Furthermore, the dual objectives cause the policy exploration often
                end up stuck in local optimums, which is also exacerbated by the
                non-convexity of infections
        -  {[[query]]: {and: [[Challenges]] [[Name of this paper]]}}
    - [[Approach]]
        - [[Purpose]]
        - [[Description]]
            * task
                * assumption
                    * We assume that the government periodically predicts
                    or collects aggregate demands for inter-regional mobility of every
                    Origin-Destination (OD) pair
                * The quota-distribution aims at minimizing
                the risk of epidemic break out in the foreseeable future periods while
                maximizing the mobility demands
                        
        - [[Evaluation]]
            * We set four different expert baselines to simulate different real-world expert policies and compare them with DURLECA
            on resolving the life-or-economy dilemma.
        - [[Architecture]]
            * models
                * rl components 
                    * note
                        * Note that our design enables the reward function to reflect that
                        the infection-spread-cost booms once the whole city’s hospitalized
                        population exceeds the city’s healthcare system capacity while the
                        mobility-restriction-cost skyrockets if any single region is continuously restricted for multiple periods.
                    * paramters are reward, historical mobility loss, exponential-growing penalty on the current restriction, and reward functions (which include infection-spread-cost and mobility-restriction cost term)
                    * reward requirements
                        * Reflecting the trade-off relation between infection control and
                        mobility retaining.
                        * Capturing the exponential growth of the social cost caused
                        by infection spread. The social cost is low when the infected
                        population is small. However, the social cost will skyrocket
                        once the infection population exceeds the capacity of the
                        city’s healthcare system
                        * Penalizing continuous mobility restrictions in the same region.
                        People’s tolerance for mobility restrictions is limited. Thus,
                        the reward function has to include a growing penalty for
                        continuously restricting the same region.
                    * 
                * flow gnn 
                    * graph is directional. 
                        * mobility into the region and mobility of people who stay in the region are accounted when compute nodes hidden states.
                        * epidemic dynamic transmission is separated into two stages: mobility-happened sub-step and infection-occurred sub-step.
                            * The two stages occur repeatedly in circular sequence.
    - [[Experiments, Results and Analysis]]
        * RQ1: Can DURLECA resolve the life-or-economy dilemma?
        * RQ2: Can DURLECA adapt to both early intervention and late
        intervention?
        * RQ3: Can DURLECA be generalized to different cities and different diseases?
    - [[Finding]]
    * [[Frequently Ask Questions (FAQs)]]
        * this paper
            * how is dual objective used in reinforcement learning?
            * how to incorporate human expert?
        - {{query: {and: [Validate] [Name of the Page]}}}
    - [[Paper Reference]]
        * this paper 
            * what is mobility simulation?
                * what is current
        * general
            * OD flows

