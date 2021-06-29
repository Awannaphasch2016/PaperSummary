# to be classified 
* ideas to create by model
    * using "additive predictors", to incorpoarting different graph structure, 
    * "smoothing" can be used as trade off between complexity and interpretability
    * to account ffor epistemic uncertainty, deep ensemble can be used where each models are trained from scratch with a different random initialization 
# CHALLENGES 
* time series transfer learning 
    * with time series it is harder to find a useful hierarchy or set of intermediate representations
        that generalize across to different problems.
    * A second challenge with multivariate time series forecasting is that many times the problems have a
        different number of feature time series
# INTRODUCTION
# NOTE
* transfer learning 
    * early layers in the model learn more general patterns whereas the later layers learn the more task 
        specific features.
    * transfer learning for time series 
        * We do have certain components that people traditionally decompose time series into such as 
            seasonality, trend and remainder
# REFERENCES
* article
    * time series + deep leanring 
        * https://igodfried.medium.com/
        * hands-on + theory 
            * https://machinelearningmastery.com/transfer-learning-for-deep-learning/#:~:text=Transfer%20learning%20is%20a%20machine,model%20on%20a%20second%20task.&text=Common%20examples%20of%20transfer%20learning,your%20own%20predictive%20modeling%20problems.
* graph
    * theory 
        * Relational inductive biases, deep learning, and graph networks
            * https://arxiv.org/pdf/1806.01261.pdf
* grouping trend 
    * trend analysis and regression models to combine trends (time series)
        * jmedium.com/analytics-vidhya/trend-analysis-and-regression-models-to-combine-trends-time-series-a41213a0014d
* here> clustering
    * here> article
        * here> how to apply k-means clustering to time series data
            * here> https://towardsdatascience.com/how-to-apply-k-means-clustering-to-time-series-data-28d04a8f7da3 
    * paper
        * algorithm 
            * k-shape: efficient and accurate clustering of time series 
                * http://www1.cs.columbia.edu/~jopa/Papers/PaparrizosSIGMOD2015.pdf
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
    * ref 
        * finished 
            * sequential transfer learning based on heirarchical clustering for improved performance in deep elarning basd food segmentation
                * https://www.nature.com/articles/s41598-020-79677-1
            * transfer learning with an Ensemble of Backgroud task
                * url
                    * https://people.csail.mit.edu/lpk/papers/MarxRosensteinKaelblingDietterich-final.pdf
                * note
                    * this approach of transfer learning with and Ensemble of Background task. 
        * unfinished
            * paper 
                * here> APPLIED TIME-SERIES TRANSFER LEARNING
                    * https://openreview.net/pdf?id=BklhkI1wz
                * LEARNING TO CLUSTER IN ORDER TO TRANSFER ACROSS DOMAINS AND TASKS
                    * https://arxiv.org/pdf/1711.10125.pdf
                * survee on transfer learning (2009)
                    * https://www.cse.ust.hk/~qyang/Docs/2009/tkde_transfer_learning.pdf
                * Paper: Reconstruction and Regression Loss for Time-Series Transfer Learning
                    * explore creating a specialized loss function that helps to facilitate positive 
                        transfer through a decoupling process
                    * use initial model to extract general features in conjunction with the reconstruction loss
                        before using a time series specific model for forecasting
                    * challenges
                        * this technique is limited to the single variate time sereis.
                * transfer learning: the dos and don'ts
                    * https://medium.com/starschema-blog/transfer-learning-the-dos-and-donts-165729d66625
                * ensemble transfer learning for the prediction of anti-cancer drug response
                    * https://www.nature.com/articles/s41598-020-74921-0
                * A novel transfer learning framework for time series forecasting
                    *
                    https://www.sciencedirect.com/science/article/pii/S095070511830251X?casa_token=XeHctaNXsO4AAAAA:fcXv_RxjJ9l3bRtLokOAT37veRSnvOBtsttcR5H0ETjo1o4-Rm08q7tN1KF2eP8hfgr06Wh3PaY
                * connected paper search 
                    * https://www.connectedpapers.com/search?q=APPLIED%20TIME-SERIES%20TRANSFER%20LEARNING
            * video
                * youtube search
                    * https://www.youtube.com/results?search_query=transfer+learning+time+series
                * conference 
                    * https://www.youtube.com/watch?v=VYpAodcdFfA
                    * https://www.youtube.com/watch?v=XIpui7lvjEg
            * article 
                * here> transfer learning for time-series prediction
                    * here> https://towardsdatascience.com/transfer-learning-for-time-series-prediction-4697f061f000
                * flow forecast
                    * https://towardsdatascience.com/transfer-learning-for-time-series-forecasting-51f023bc159c
            * others
                * google search
                    * https://www.google.com/search?q=transfer+learning+from+clustering&rlz=1C1CHBF_enUS941US941&oq=transfer+learning+from+clustering&aqs=chrome..69i57j0i22i30.5826j0j7&sourceid=chrome&ie=UTF-8 
# RELATED WORK
* Article: transfer learning: the dos and don'ts
    * In general use [[differential leraning rate]], because, in practce, there are too many options to freeze
        layers.
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

* see numerai forum for the following topic
    * clustering
    * regression 
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


## Step by Step
1. Graph based Learning
    * description
        * this process learned from graph input.
2. clustering + grouping process
    * description
        * this process is done for each time step.
    2.1 rule-based grouping
        * description
            * if there are 2 rules where first rule has 3 categories, and second rule has 4 categories, then there will be
                2 levels where the first level have 3 nodes. and second level has 3*4 nodes (12 nodes)
        * example
            * is lockdown policy apply?
            * is vaccince distributed?
    2.2 clustering grouping
        * description
            * clustering is applied after rule-based grouping
        * types of similarity examples
            * trend similarity
            * virtual nodes similarity
            * node embedding similarity
3. aggregating + decomposed aggregate.
    * note
        * this process satisfy smoothness requirements of the model.
    3.1 aggregating process
        * description
            * aggregate similar trend into 1. Inuitively, it is trying capture intrinsic trend of infection
                growth from group of similar cases.
        3.1.1. applying rolling mean on each trend.
        3.1.2. apply means to each group.
        3.1.3. (optional) validate that aggregating is succesful by checking if trend properties are retained.
            * note
                * this can be done to gain intuition, but it is not a part of predictive model.
            * examples of trend properties are
                * spike
                * whether or not trend obey certain event.
    3.2. decomposed
        * description
            * model is trained on "group" trends then transfer learning is applied to "member" trend within a group.
            * intuition here is to transfer "infection growth" of similar case (learned from group trends) and learn to adapt to target trend.
        3.2.1 train model on group trend
        3.2.2 applied transfer learning to members within the same group.
             * description
                  * this step will predict individual trend.

## MY MODEL DESIGN
### sytem requirement
    * the model must use as many types of network as possible
    * the model must use transfer learning
        * to tranfer learned knowledge about "stage" of the pandemic spread
            * transfer knowledge about first wave to second wave
            * transfer knowledge from one location to another location
    * the model must do nodes and edges attention
        * node attention 
            * weight between neighbor nodes and target node
            * eg GAT
        * edge attention is 
            * weight between target nodes and its neighbor
    * the model must deal with few dataset
    * the model must deal with noisy data

### possible input data
    * non-graph input
        * demographics
        * economics
        * politics
        * covid cases 
        * traffic
        * airplain
        * news
    * types of network (network dataset)
        * mobility
        * correlation network
        * weather newtork
        * social connectedness network
        * colocation network 
        * geographic similarity


# RESULT
* Q1: Is DeepCovid able to anticipate trend changes?
* Q2. Does DeepCovid capture finer grain patterns?
* Q3. How does DeepCovid perform in US National short term forecasting?
* Q4. does DeepCovid's emphasis on short -term forecastin scarifice longer-term performance?
* Q5. Can DeepCovid explains its prediction to epidemiological exports for interpretation?
# FREQUENCY ASK QUESTION 
* when to model product to predict rate of change (roc), new cases, number of total case?
    * what is the covid19 kaggle competition predicting target?
* what is calibration?
* how to apply transfer learning on the same task but different scale? 
    * features from smaller scale combined to create feature of the larger scale
* transfer learning from simulated dataset

