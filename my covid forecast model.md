# ToC
# to be classified 
* ideas to create by model
    * using "additive predictors", to incorpoarting different graph structure, 
    * "smoothing" can be used as trade off between complexity and interpretability
    * to account ffor epistemic uncertainty, deep ensemble can be used where each models are trained from scratch with a different random initialization 
# INTRODUCTION
# REFERENCES
* grouping trend 
    * trend analysis and regression models to combine trends (time series)
        * jmedium.com/analytics-vidhya/trend-analysis-and-regression-models-to-combine-trends-time-series-a41213a0014d
* clustering
    * clustering of time-seris data
        * https://www.intechopen.com/books/data-mining-methods-applications-and-systems/clustering-of-time-series-data 
    * Data-driven dynamic clusteirng framework for mitigating the adverse economic impact of COVID-19 lockdown practices
        * https://www.sciencedirect.com/science/article/pii/S221067072030593X
    * Clustering method for spread pattern analysis of corona-virus (COVID-19) infection in Iran.
        * https://www.medrxiv.org/content/medrxiv/early/2020/05/28/2020.05.22.20109942.full.pdf
    * COVID-19 ensemble models using representatie clustering
        * https://dl.acm.org/doi/abs/10.1145/3431843.3431848
    * Estimation of COIVD-19 dynamics in the differnet sttates of the Unites States using Time-series clustering
        * https://www.medrxiv.org/content/10.1101/2020.06.29.20142364v1
    * A city cluster risk-based approach for Sars-CoV-2 and isolation barriers based on anonymized mobile phone users' location data 
        * https://www.sciencedirect.com/science/article/pii/S2210670720307927
    * Applying a prospective space-time scan statistic to Examine the EVolution of COVID-19 Clusters in the State of Sao Paulo, Brazil
        * https://www.medrxiv.org/content/10.1101/2020.06.04.20122770v1
    * Randomness, information entropy, and volatility interdependencices among the Major Worlds Markets; the role of the covid-19 pandemic
        * https://www.mdpi.com/1099-4300/22/8/833
    * Fuzzy clustering method to compare the spread rate of COVID_19 in the high risks coutnries
        * https://www.sciencedirect.com/science/article/pii/S0960077920306263
    * Transmission potential and severity of COVIDD-19 in tsourth korea.
        * https://www.sciencedirect.com/science/article/pii/S1201971220301508
* transfer learning 
    * transfer learning: the dos and don'ts
        * https://medium.com/starschema-blog/transfer-learning-the-dos-and-donts-165729d66625
    * ensemble transfer learning for the prediction of anti-cancer drug response
        * https://www.nature.com/articles/s41598-020-74921-0
    * transfer learning with an Ensemble of Backgroud task
        * https://people.csail.mit.edu/lpk/papers/MarxRosensteinKaelblingDietterich-final.pdf
    * sequential transfer learning based on heirarchical clustering for improved performance in deep elarning basd food segmentation
        * https://www.nature.com/articles/s41598-020-79677-1
    * google search
        * https://www.google.com/search?q=transfer+learning+from+clustering&rlz=1C1CHBF_enUS941US941&oq=transfer+learning+from+clustering&aqs=chrome..69i57j0i22i30.5826j0j7&sourceid=chrome&ie=UTF-8 
# RELATED WORK
# REQUIREMENTS
* system requirement 
    * predicted trend should prefer smoothness.
        * This is becsue we assem infection growth is smooth and fluctuation is caused by other static/dynamic features 
    * utilize transfer learning from a group of similar states
    * group similar states together based on certain streategies.
        * clustering?
        * trend similarity?
        * features similarity.
        * rule base
            * eg. states in the same gropu must have same lockdown policy. ()
    * 
# KEY CONTRIBUTION
# WHAT HAVE WE DONE
* key contribution
    * established experimental evidence whether "similar" trend can provide useful predictive info.
* how to cluster time series?
    * ref 
        * https://nbviewer.jupyter.org/github/alexminnaar/time-series-classification-and-clustering/blob/master/Time%20Series%20Classification%20and%20Clustering.ipynb 
            * using distance between two time-series doesn't work
            *  we need to use dynamic time warping
                * goal is to find function that minimized the cumulative distnace.
                    * align time-seires that will minized the distance.
    * how to emed time-series that capture characteristic and its properties, and can be used to compared.
* can I classfified regression? 
    * how to classify trends in a time series regression model
        * ref
            * here> https://www.dummies.com/education/math/business-statistics/how-to-classify-trends-in-a-time-series-regression-model/
        * trend analysis and regression 
    * what to do when I group states together?
    * can I predict group as 1 then add differences to the trend for each states within a group.
        * ref 
            * https://medium.com/analytics-vidhya/trend-analysis-and-regression-models-to-combine-trends-time-series-a41213a0014d
                1. find linear function for each regression
                2. "combine" then using aggregated function (Combined function)
                    * such as mean between members of the group
                4. validate "properties" of the combined trend such as the following 
                    * spike
                3. apply (trend decomposition) function to go from aggregated trend to original trend.
                4. validate "properties" of the decomposed trend such as the following 
                    * spike
* different ways of forming virtual graph.
* create multi-level graph  
    * first graph is within the same time-series. (virtual graph)
    * second graph is between time-series. (normal graph construction)

# CHALLENGES
# TERMINOLOGY
* additive effect
    * when two predictors do not interact, we say that each predictor has an "additive effect' on the response.
        * More formally, a regression model contains additive effects if the response function can be written as a 
         sum of function of the predictor varialbes
* additive predictor 
    * structure additive predictor
        * representa mooth additive effectos of input features and can be reresented in a neural network.
        * it can be represented in neural network term

# STANDARD AND BASELINE
# METHODOLOGY
# RESULT
* Q1: Is DeepCovid able to anticipate trend changes?
* Q2. Does DeepCovid capture finer grain patterns?
* Q3. How does DeepCovid perform in US National short term forecasting?
* Q4. does DeepCovid's emphasis on short -term forecastin scarifice longer-term performance?
* Q5. Can DeepCovid explains its prediction to epidemiological exports for interpretation?
# FREQUENCY ASK QUESTION 

