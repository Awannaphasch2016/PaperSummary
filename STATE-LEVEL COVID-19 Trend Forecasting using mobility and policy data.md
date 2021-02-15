introduction

key contribution
    focus on stat-level daily new cases of COVID-19 in the US

related work
    compartmental model
    machine learning model
        weibull fitting to fit the nationwide epidemic curve wihtout considering any exogenous factors
        GRU-based framwork for state-level prediction 
            use static behavior
        GNN-based appraoch for country-level COVID-19 forecasting 
            google's human mobility data across all countries in the US are represented as a single large-scale spatio-temporal graph
            doesn't consider other significant external factors
        DeepCOVIDNet
            divided country-level weekly rises of confimed COVID-19 cases into 4 coarse categories
            based on the DeepFM framwork
            use the demographic statistic and cross-county mobility data provided by SafeGraph to make coarse-level prediction

terminology
    state 
        in the paper state only refers to DC states
    DIS policy
        mobility information
    intercept term 
        represent the baseline transmission rate of the corepsonding state
            this represent tranmission rate under normal mobility and conditions before the pandemic
        baseline is highly related to each state's demographic

standard and baseline
    dataset
        COVID-19 daily confirmed case data        
        State-level mobility data
            the state-level travel statistics are daily aggreagtes of residents movments based on their mobile phone data
             and provided information about population mobility
            A trip was counted if a person stayed away from home for more than 10 minutes
            the daily trips were grouped into 11 cateories based ontheir travel distrance
                eg 
                    distance n-m category
                        trip within the range of n-m miles
                    staying at home category
            abnormality activities across the US around the later summer 2020 when school start and in early November 2020 
             when the election was held
                These abnormality must be pre-processed
                the detected outlier of sample are more than 3 deviation away from the median
        state restriction policy
            note: binary value features
            mask waring policy
            restaurant opening policy
        state-level demographic information
            state-level demographic information
                local population density
                local age structure (non-overlapping age groups)
                local race strucutre (differnt race categories)
    evaluation 
        RMSE
            it estimate the relative deviation from the local COVID-19 trend
        RALE (relative accumulated log error)
            it captures the relative deviation from the accumulate cases within m days

methodology
    dataset
        policy
            50 states issued the restaurant policies
            34 states issued the public mask policies
        MObility data
            'stay at home' category normalized by state population
            others are normalized by state population not staying at home
            each category ws done by subtracting the median pre-pandemic mobility value and then dividing the maximal pre-pandemic mobility value
    pre-processing
        data is smooth by using EMA of the previous 3 days
    hyperparamter 
        hyperparamters are realted to the following factors
            incubation time
            the efficiency of the state healthcare
    models
        regression model
        calibration the forecast
            reason to do calibration
                the regression model assuem stationary relationship between the transmission rate variable and the features. (population mobility and policies)
                reporting  error associated with daily confirmed cases and the accumulated prediction error can gegenrate the predictions of the daily cases.
        differences in baselines tranmission rate may possible due to the state-level demographic


result
    note that large volatility in the confirmed daily cases due to delay in reporting rather than the weak 
     performance of the corresponding model 
    frequency of significnat factors to be significnat within states. (from highest to lowest)
        mask policy
        stay at home
        resturant policy
        DIS 0-1
        DIS 1-3
        DIS > 500 
        DIS 250-500
    frequency short-distance travels and cross-state travels promote the spread of COVID-19
    demographic interpretation of the state-level biases in COVID-19 transmission
        model is trained separately for each state

frequency asked question
