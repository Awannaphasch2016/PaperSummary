* reference
    * url:
        * medrxiv.org/content/10.1101/2020.09.28.20203109v1.full.pdf
# INTRODUCTION
# RELATED WORK
* current work can be classified into two categories
    * statistical
        * most of the existing statistical approaches for epidemic forecasting are developerd for influenza forcasting
            * eg 
                * (Adhikari et al.2019)
    * machanistic?
        * mechanistic approach model the underlying disease transmission over the population  contact network under various assumptions using the following
            * ordinary differential equation
                * eg
                    * ( Zhange et al. 2017)
            * agent based models 
                * eg 
                    * ( Venkatramanan et al. 2018)
        * pro/cons
            * good for long-term 'what-if' scenario generation
        * dataset
            * weather data 
                * (Volkava et al. 2017)
        * challenges 
            * real-time forecasting
                * as complexity of model increases, number of data source being used increases
                    * given this constraint, it is not trivial to extend these model to include various other data signals
                        * such as social media data
* ensemble
    * good ensemble needs diverse perspective (Reich et al. 2018; Ray et al. 2020)
* baseline model 
    * short-term forecasting model
        * the utility of statitical models (Homdahl and buckee 2020)
# KEY CONTRIBUTION
* DEEPCOVID is the first purely data-driven deep learning (DL) model for real time pandemic forecasting in the COVID19 Forecast Hub (Reich et al. 2020)
* DEEPCOVID is used by official to forecast on CDC website and FiveThirtyEight website
* key contribution
    * G1. coping with heterogeenous, scare and noisy data
    * G2. bring a completmentary forecasting perspective
    * G3. Excellence in short-term forecasting
    * G4. Enable communication to domain-expert
# FUTURE DIRECTION
* there are still open question for forecastin in lower-level granularities, where some signlas are more bursty.
    * state and county level
# CHALLENGES
* data module challenges
    * Challenges
        * C1. data collection
            * multiple source data. 
                *( different format 
        * C2. selection of signals
            * select signals that describe the different facets of the diesases spreads
            * to enable epidemiological observations about our prediciton, this selection has to be driven by appropriate rationale.
        * C3. Temporal misalignment
            * multiple source data have termporal misalighnment
                * eg
                    * hospitals ahve 1-2 weeks lags before reporting data
        * C4. Spatial misalighnment
            * some records are reported at specific spatial granularity 
                * it is non-trivial to converse to higher geographical levels.
        * C5. missing values
            * most prominently, our forecasting target (incidence hospitializations,) has not been reported in 11 states including  
                * CD, DC, TX, IL, LA, PA, MI, MO ,NC, NV, DE
* prediction module challenges
    * C1 Data Sparsity
        * extracgin enough information from the few available data point to ensure generalization forecasts is a challenging problem
    * C2. Robust point and proprobabilistic forecasting 
        * how do we principally tranlate data noise to forecast uncertainty?
        * how do we ensure taht our approach is robush to noise and other data issues such that ensure relaiable point and probabilitstic forecasts?
    * C3 Temporal consistency between the forecasts
        * due to data sparsity we cannot hope to train deep network enforcing temporal consistency such as LSTM and GRU
            * how to design a neural architecture, which has few enough parameters to train from sparse data while ensuring temporal consistency betwen the forecasts?
* Explainability Module challenges
    * policy differs from state to state
        * hence, the data signals that we collect have differnet meaning and usability at different time and regions. 
            * the challenges here is to ensure that our framework is able to generate forecast explainable with respect to the data signlas and enable analysis of 
             signal streangth over differnet geographies and periods
# HOW THE AUTHOR COME UP WITH AN IDEA?
* DEEPCOVID architecutre is constructed with the goal of being adopted by official from the start
# KEY CONTRIBUTION
# TERMINOLOGY
* temporal misalignment
# STANDARD AND BASELINE
* evaluation metrics
    * MAPE
        * to measure performance of our point estimate
    * measuring performance from a probabilistic perspective 
        * see paper
# METHODOLOGY
*  task
    * forcast target are as followed
        * incidence and cumulative weekly deaths
        * incidence daily hospitalization
    * goal is to predice next k values of forecasting target
* architecture
    * 3 modules 
        * data module
            * handling of moisy data form the learning process
            * solution ( or how challenges are addresses)
                * C1. 
                    * we developed a data extraction program personalized for each data format to convert them all to a standard format 
                * C2. 
                    * search for signals from epidemiological perspactive
                    * 5 types of signlas ( for more information see table 1)
                        * Line list
                        * Testing
                        * Crowdsourced symptomatic
                            * description
                                * collected from individuals using Kinsa digital thermometers at home (Miller et at. 2018)
                            * Signals
                                * Digital thermometer readings.
                        * Mobility
                        * Exposure based
                        * Social Surveys
                * C3. 
                    * we address weekly/daily inconsistency, signals require different treatment depending on their nature
                        * weekly hospitalizationrate have been recorded as percentages, so we use weekly value as daily value because weekly value cant be convert to daily
                * C4. 
                    * to provide a state-wise forecast model, we tranformed the signla record state-wise by aggregating and de-aggregating, respectively.
                        * [[validate]]
                            * no clue what they mean 
                        * therefore, it is important to consider the population of such geographic regions.
                * C5. 
                    * we had realted signals such as hospitalization and ICU patients.
                        * we inferred missing values by leveraging these signals and making reasonable assumptions ( such as effect of people's recovery and dealth in one week)
                            * such as 
                                * effect of people's recovery and death in one week
        * prediction module
            * use deep learning because it is flexible
            * there was 1 month of menaingful (non-zero) data at the start of the CDC task (April 2020)
            * we opted to use a FNN with autoregressivie inputs to incorporate short-term dependencies in the time seires 
            * solution  
                * C1.
                    * we have to avoid overfitting due to Data sparsity
                * C2 
                    * to address C2 "Robust point and proprobabilistic forecasting"
                        * we want data-based uncertainty not model-based unceratinty
                            * so for each future incidence target, we obtain one single prediciton per bootstrap smaple so that we obtain a set of M predictions 
                             representing uncertainty in data (lines 7-10 in Alg.1) 
                        * apply batch normalization to alleviate initialization problem
                            * we also run the same optimization for several times and select the one that leas to lowest loss in the (training) data.
                * C3 
                    * to address C3 "Temporal consistency between the forecasts"
                        * we capture temporal correlations between consecutive forecasts by training on week k to predict week k + 1
                        * for predicting cumulative deaths, once we get incidence preidctions, we convert them to cumulative ones by aggregating the point prediction. 
                            * we found taht this give consistent and stable performance
        * explainability module
            * once we have insight aobut our predictions, we will ahve feedback llop to imporve performance
            * we investigate by using data ablation 
                * we then check if the contribution of the signal is statistically significant with respect to the model with all signals
                * 2 types of references can be made based on whether or not ground truth is availabel
                     1. based on available groud truth  
                     2. based on means of prediction
                * we also use two-sample t-test with null hypothesis.
                    * if signal failed to reject, it will be be removed from the ranking output

 
# RESULT
* note: 
    * testing and mobility data signals were most important for predictive performanceo average
* Q1: Is DeepCovid able to anticipate trend changes?
    * Deepcovid is able to anticipate important changes in trends several weeks ahead
* Q2. Does DeepCovid capture finer grain patterns?
    * Deepcovid is able to capture finer grained reporting patterns
        * In forecastin daily hospitalization
            * P1: drop during weekends
            * P2: rise on Monday, and continue stable durign weekdays
* Q3. How does DeepCovid perform in US National short term forecasting?
    * beat baseline (compare aginst the official ensemble of all contributing models in the COVID-19 Forecast Hub including DeepCovid) in 1-2 weeks ahead prediction
* Q4. does DeepCovid's emphasis on short -term forecastin scarifice longer-term performance?
    * it doesn't sacrified short-term forcasitng with longer-term performance
    * state level performance is mixed. (some good, some bad) 
        * this is indicative that there are still open question for forecastin in lower-level granularities, where some signlas are more bursty.
* Q5. Can DeepCovid explains its prediction to epidemiological exports for interpretation?
    * yes
        * eg
            * second peak is mainly caused by mobility
# FREQUENCY ASK QUESTION 
* what is CDC requirement for covid19 model forcasting?
