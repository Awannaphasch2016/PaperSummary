# note to self: no smaller detail. only big picture. smaller detail should be 
* read from the paper itself
# introduction
* extreme lockdown is shown to be veryfeffective to slow down the spread of SARS-COV2
    
# terminology
* cc = confirmed cases
* dc = new confirmed cases
    * we pro-process each of them into two series:
        * one contains values only when thre is restriction policy undergoing
            * cc_res and dc_rest
        * another only contains value when thiere is no restriction policy
            * cc_nores and dc_nores
* state demographics embedding
# how the author come up with their ideas?
* problem with using SIR and the nature of reported data
    * ODE 
        * ODE deals with continuous dynamic, but, in reality, data is reported periodically
            there are also delay in reporting the case
    * SIR
        * SIR doesn't take in account factors like the following
            * improved immunity
            * improved medical response
                * law policy which could effect the spread
        * absence of environmental factors
            
# dataset
# methodology
* environment factors which govern
    * epidemic evolution process (exogenous factors) Or 
        * Dominant factors of the transmission
            * disease characteristics
            * higher prob in regions with dense propulation dist. 
            * restrictive order issued by the local government
                * we use restriction of the local daily life 
                    * ie. the stay at home order or its equivalencies
                        as an aggregated represetnation of the local restriction level
                        stages of the restriction influence time-varying transmission
                            of COVID19
                                * note: this is different from compartmental model that assume a constant 
                                    transmission factor \beta
            * we use [[enplanement per capital]] [16] to capture the active level of human interactions
                * enplaned = passenger boarding plane at a particular airport 
        * vulnerable propulation groups and descriptivefactors
            * we included ages strucutre as an importnat demographics category
                ages people are in general more vulnerable to the virus
            * we includes the population with high risk [10] as an input feature of modeling
                physical condition of individual influence probability of infector
                    * eg
                        * poor respiratory condition experience higher risk of being infected. 
    * revela the social impact of COVID19 from essential perspective
        * smoking-gun factors for social impact analysis
            * social factros
                * higher prob of positive testing rate is in poorer neighborhoods where 
                    * large number of people reside together (more density)
                * higher prob in neighborhood with large black or immigrant population
                * people in porrer neighborhood are less likely to be tested
            * we select several socioeconomic chracteristics.
                * GDP per capital
                * local race compositions
# model
* dataset
    * 2 class of input
        * the epidemic time series.
            * including both confirmed case and deceased cases.
        * environmental socioeconomic factors including
            * local population density
            * local GDP per capital
            * local age structure (fractions of 6 non-overlapping age groups)
            * local race structure (fration of 7 differen race categories)
            * high risk population
            * local annual enplanements per capital
            * local restructive order level
    * source of data (1,4,10,16,25,26)
        * covid19 case data
            * case data is from the CovidNet project [26].
        * state restriction policy  
            * poligy information is collected from "the Coronavirus Outbreak" forum on the New York Times
        * population and density
            * we have used population data from the U.S Census Bureau [25]
        * population with higher risk
            * population in each state with higher risk to develop sever symptoms are estimated in [10]
        * age structure data
            * age structure data built by the Kaiser Family Foundation [1]
        * race structure data
            * race strucutre data is collected from the COVID Tracking project? [4]
        * annual enplanements data
            * collect data from all states except D.C from the U.S. Department of Transportation [16]
        * gross domenstic product per capita
            * we collect the data from the united states census bureau [25]
* modeal 
    * we use GRU
        * double-channel strucutre in GPU module 
            * a sequential data point would enter channel-1 if there is a restruction policy 
             on the corresponding data, otherwise, enter channel-2
        * gates 
            * environmental factors and epidemic time series data are 
             interact with each other via various GRU gates
        * architecture 
            * GRU 3 stacked layers with 100 dimensio hidden states
    * hyper-parameters searching 
    * preprocessing
         * environmentl factors produces interpretable weights on each input dimension 
            embedding representation of environmental factors is taken as "the initialization 
             of the hidden state in the GRU model" (this process is called "kick-start" mechanism)
    * task
        * Goal: 
            1. predict the epidemic evolution
            2. understanding of the interplay between environmental factors and the local epidemic outbreak. 
        * Prediction of the Epidemic Evolution
            * training data is transofrmed into sequence-to-point pairs
            * prediction power are demonstrated in two ways
                1. 1-step-ahead prediction
                    serverl states are removed from training set
                    performance are tested on removed states (no historical data known at all)
                2. Long-term prediction from an auto-regressive process.
                    train 1-step-ahead in training data
                    predict long term prediction in test data
# result
        
* Relevant of Environmental factors
    * to reveal interply between environemental factors and the epidemic evoltion, 
     we analyze relavance of each input factors to the dynamics 
    * Frobenius norm is used to examine relevance of each embedding vector
        
        
# frequently ask question 
* what is relevance index?
* how does SIR being implemented with deep learning techno?
