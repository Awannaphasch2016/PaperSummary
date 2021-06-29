*  #[[Research Paper]]
    - URL: 
        * paper
            * https://appliednetsci.springeropen.com/track/pdf/10.1007/s41109-019-0122-7.pdf#page=31&zoom=100,149,700
        * github 
            * https://github.com/christa60/defsi
    - Citation
        @inproceedings{wang2019defsi,
          title={DEFSI: Deep learning based epidemic forecasting with synthetic information},
          author={Wang, Lijing and Chen, Jiangzhuo and Marathe, Madhav},
          booktitle={Proceedings of the AAAI Conference on Artificial Intelligence},
          volume={33},
          number={01},
          pages={9607--9612},
          year={2019}
        }
    - Status:: [[Finished]]
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
        * Tags:: [[multi-agent based simulation]] [[Theory Guided Data Science]] [[ILI prediction]] [[time series prediction]] (Complete citation: Key Words: General subject: Specific subject:)
        * [[Use case: What is take away knowledge that you can use in your work?]]
            * I can use the idea of simulating data with multi-agent based simulation to help predict.
            * The paper uses multi-agent based simulation approach to generate more data which deep learning model learn to predict it.
        * [[Related work: what are referenced papers that closely related to the paper?]]
            * EPIFAST
            * Theory Guided Data Science
        * [[Data: what is data characteristic?]]
            * noisy time series data with limited amount.
            * provided for county and state level.
        * [[Technique: what are technique used in the paper?]] 
            * multi-agent based simulation
            * input from 2 branches 
                * note
                    * using 2 branches is not always better. 
                        * using current year data sometimes outperform using both branches.
                * first input is ILI data of the current year
                * second input is same section of ILI data of the past d years.
        * [[Context: what's the context for the paper]]
            * [[Application Domain]]
                * note
                    * basically "task" but expand to include whole domain application (use case).
            * [[Problem: What are exact problems that it solve?]]
                * predict ILI daily cases which is time series data.
            * [[Hypothesis]]
                * the paper assume that using multi-agent based simualation that are driven by epidemological theory can provide data that deep learning can benefit from learning.
            * [[Methodology results]]
                * the purposed method is better than baseline.
            * [[what idea does the paper expand further?]]
                * use more "theory guided" idea including behavior of agents.
                * can transfer learning benefit from simulated data?
            * [[Concept: what's the key contribution of the paper]]
                * note 
                    * concept answers 'what' paper does to solve the problem.
                * using theory guided method such as multi-agent based simulation to generate data that deep learning can benefit from learning.
            * [[Implemntation: how does the paper implement thier core idea?]]
                * note
                    * implementation answers 'how' paper solve the problem.
                    * 'implementation' doesn't refer to the exact implementation, rather 'implementation' refers to 'how' authors materialize their core ideas. (key contribution)
            * [[Significance (to the field; in relation to your own work):]]
                * it shows that simulation methods can help deep learning in time series prediction. 
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
        * simulation methods 
            * similar work to solve epidemic case prediction
            * Causal methods have
            recently been introduced to enable high-resolution forecasting (Yang, Karspeck, and Shaman 2014; Nsoesie et al. 2013;
            Zhao et al. 2015)
                * They estimate the parameters of the underlying disease model from the surveillance data. Then ILI
                incidence prediction is made from the output of simulations
                using the identified disease model
            * the agent-based simulator EpiFast (Bisset et al. 2009).
            * s. For AdapLSTM, weather factors are considered
            for post adjustment of LSTM outputs. As stated in (Venna et
            al. 2017), the weather factors are estimated using time delays
        * new paradigm of modeling 
            * Theory Guided data science  (TGDS)
                * In a recent independent effort, Karpatne
                et al. (Karpatne et al. 2017) formally conceptualized the
                paradigm of theory-guided data science (TGDS) that seeks
                to exploit the promise of data science without ignoring the
                treasure of knowledge accumulated in scientific principles
    - [[Key Contribution]]
        * To the best of our knowledge, DEFSI is the first to combine a realistic multi-agent model with deep learning for
        epidemic forecasting
        * This motivates our
        work to address the shortcomings of data driven and causal
        models by using synthetic data generated by epidemiological theories in conjunction with observed data to improve
        epidemic forecasts.
        * DEFSI enables accurate high-resolution forecasting with flat-resolution observations as inputs.
        * DEFSI
        proposes a two-branch neural network model for ILI forecasting.
            *  It combines within-season observations (observed
            data points of the current season that characterize the ongoing epidemic) and between-season historical observations
            (observed data points from similar weeks of the past seasons
            that characterize general trends around the current week)
        * DEFSI constructs region-specific training datasets at multiple spatially fine-grained scale with low costs. We initialize
        region-specific simulations with realistic parameter settings
        learned from the corresponding surveillance data
        * Extensive experiments on ILI incidence forecasting for two states
        of the USA show that DEFSI achieves comparable/better
        performance than the state-of-the-art methods at state level.
            * For high-resolution forecasting at county level, DEFSI significantly outperforms the comparison methods.
        o Finding
            - {{query: {and: [Finding][Name of this Paper]}}}
    - [[Grounded Claim]] 
    - [[Future Direction]]
        * A direction for future work is to further investigate the use of synthetic data generated by social, epidemiological and behavioral theories in conjunction with observed data to improve epidemic forecasts.
    - [[Standard/Benchmark]]
        - [[Data]]
        * [[Model]]
            * neural network methods
            * statistical methods
            * agent-based causal models
    - [[Tool]]
    - [[Related Work]]
    - [[Defining Equation, Notation, Terminology, Theory, and Law]]
        -[[Terminology]]
            * flat-resolution
                * In this paper we use flat-resolution forecasting to denote the forecasting of ILI incidence with the same resolution as the surveillance data;
            * high-resolution
                * high-resolution forecasting to denote the forecasting with a higher geographical resolution than provided in surveillance data. 
            -[[Notation]]    
    - [[How does researcher think of this research idea?]]
    - Challenges
        - [[Challenges]]
            * A challenge in high-resolution disease forecasting is
            the lack of surveillance data at a finer spatial scale
                * Even for a few states where county level surveillance
                data is available, training ANN methods for them is difficult due to the small size of the data
                * The
                data driven methods suffer from this limitation, including statistical methods such as ARIMA (Benjamin, Rigby,
                and Stasinopoulos 2003), ARGO (Yang, Santillana, and
                Kou 2015; Yang et al. 2017) and artificial neural networks (ANN) methods such as Long Short Term Memory
                (LSTM) (Volkova et al. 2017; Venna et al. 2017; Wu et al.
                2018). 
            * A challenge in high-resolution disease forecasting is
            the lack of surveillance data at a finer spatial scale
            * Another challenge to the epidemic forecasting domain is
            the generalization and physical consistency of data driven
            models due to the paucity of representative samples in nature
                * . Meanwhile it is difficult for causal models to represent complex processes that are not conceptually well understood using known scientific knowledge.
        -  {[[query]]: {and: [[Challenges]] [[Name of this paper]]}}
    - [[Approach]]
        - [[Purpose]]
        - [[Tasks]]
            * requirement 
                * high-resolution ILI incidence forecasting based on ILI
                surveillance data of coarse resolution.
                * multi-step forecasting
        - [[Evaluation]]
        - [[Architecture]]
            * In DEFSI, the training dataset is used to estimate disease parameter space, while for other comparison methods, it is used for training forecasting model directly.
            * data simulation 
                * goal 
                    * s. The purpose is to use simulations to create training data
                    as similar as possible to the surveillance data observed in the
                    real world.
                * The idea is to
                model the non-linear relationship between the past higher
                level (state) ILI incidences and the future higher (state) and
                lower level (county) ILI incidences with a deep neural network. 
                    * With a multi-agent model, individual or household
                    level behavior can also be modeled as well as the public
                    health intervention measures changing the disease dynamics. 
                * 2 synthetic training data are created.
                    * vaccine-case
                        * include vaccine intervention data for simulation..
                    * basic-case
            * models
                * 3 major components 
                    * [[there are more]] Disease Model parameters space construction.
                        * data about the following parameters are collected.
                            * Transmissibility
                                * We compute season attack rate ar (i.e. fraction of population getting infected in the season) of each historical season for the target state and its neighbor states (i.e. geographically contiguous states). 
                            * Initial Case Number
                                * ILI incidence of the first week of each season for the target states and its neighbors. 
                            * Vaccine Intervention 
                                * We assume that the state level vaccine schedule is the
                                same as the nationwide schedule.
                                * collect 6 vaccineation schedules of the past six influenza season in USA

                    * Synthetic training data generation.
                        * use SEIR
                        * In this work, we adopt the agent-based simulator EpiFast (Bisset et al. 2009)
                            * The outputs are individual level
                            infected cases with the infected days of a simulated season.
                            * They can be aggregated to any temporal and spatial scale,
                            such as daily (weekly) state (county) level ILI incidence.
                        * Vaccine intervention IV (i.e. quantity of vaccines applied to
                        the population and the timing of the application) is applied
                        in our simulations
                    * [[there are more]] Deep neural network training and forecasting.
                        * use 2 kinds of observations
                            * Within-season observations
                                * ILI incidence from previous a weeks of the current season. 
                            * Between-season observations 
                                * same week from the past b seasons.
                * training data from simulation 
                    * for each run, sampled data is simulated to generate state and county level weekly incidence, called "synthetic epicurve." 


    - #[[Experiments, Results and Analysis]] #[[Finding]]
    - [[Frequently Ask Questions]]
        * what does the paper mean by multi-agent system?
            * see EPIFAST
        * how is two predictive branches related to flat and high resolution?
            * Not really related. 
                * two branches are deep learning design to achieve maximum performance. 
        * how is county and state raw data used in simulation?
        - {{query: {and: [Validate] [Name of the Page]}}}
    - [[Paper Reference]]
