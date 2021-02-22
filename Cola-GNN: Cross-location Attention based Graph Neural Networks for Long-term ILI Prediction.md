:dynamic graph neural network:spatial attention:

# ToC
* related work
    * influenze prediction
    * longer-term epidemic prediction
    * spatio-temporal prediction
* formulate thie researhc problem and details proposed model 
* details of experiment 
* analyze result
* summary
# introduction
* Influenza outbreaks also exhibit long seasonnality.
    * about 13 weeks in United state.
# related work
* spatio-temporal epidemic prediction
    * fields or Topics that use spatio-temporal prediction
        * societal event forecasting
        * air quality prediction
        * traffic forecasting
            * create graph input by link different sensors together 
        * social events
    * Challenges
        * Influenza data shows longer granularity (weeks) 
            * other fields mentioned are collected with inverval as low and 5 mins or 1 mins.
# key contribution
* we designed cross-location attneetion based graph neural network (Cola-GNN)
    * combine Graph structure (geolocations) and time-series features
* key contribution can be summaried as followed:
    * graph based deep learning for long-term epidemic prediction from a time-series forecasting
        * one of the first work to apply GNN to pandemic
    * investigate a dynamic location-aware attention machanism 
    * design a temporal dilated convolution module to automatically extract both short and long temporal dependencies from time-series data
        * learned features are utilized as node attributed for gnn
    * demonstrate effectiveness of attention matrix used in geographical adjacency
# Challenges
* challenges in long-term epidemic forecasting
    1.  temporal dependency is hard to capture with short-term input data
        * statistical model
            * without manual integration of seasonal trends, most statistical models fail to achieve high accuracy
    2. the influence of other locations often changes over time.  
    3. spatio-temporal model is often explored in environment that have more data (than pandemic)
# terminology
* ILI
    * influenza-like illness (ILI)
* dynamic location-aware attention machanism
# How does author come up with his/her ideas?
* limitation of existing works are as followed
    * limited long-term prediction performance
    * fails to capture spatio-temporal dependencies in data
* existing work has been focus on the following aspects
    1. Traditional causal models
        * categories 
            * compartmental models 
                * focus on mathematical model of population-level dynamics.
            * agents-based models
                * simulate the propagation process at the individual levle with contact network
            * employ disease progressions mechanisms 
                * SIR
        * challenges of traditional models
            * hard to calibrate
    2. Statistical models 
        * example
            * Autoregressive (AR) and its variants
    3. deep learning methods 
        * example 
            * rnn
        * problem
            * rnn doesn't consider cross-spatial effects in long term diesease propagation
# standard and baseline
* Data
    * epidemic related dataset from United state and Japan
# methodology
* goal
    * focus on longer term (2-15 weeks) prediction from 20 weeks of data
# result
# frequently ask question 
