
# ToC
# INTRODUCTION
# REFERENCES
# RELATED WORK
# KEY CONTRIBUTION
# CHALLENGES
# TERMINOLOGY
* message passing neural network (MPNN)
* transfer learning (TL )
* Meta Test ?
* model agonostic meta-learning?
# STANDARD AND BASELINE
* dataset
    * Data for Good program
        * Facebook ahs release several dataset in the scope of data for Good 
         program to help researchers better understand the dynamics fo the 
          COVID-19 and the forecast the spread of the disease
        * dataset is collected directly from mobile phones that have the Facebook 
         spplication installed and Location History setting enbaled.
        * the raw data contains 3 recording per days
            midnight, morning, and after noon 
        * data indicate number of people moving from one region to another at 
         that point of day.
    * cases data
        * gathered from open data listed in the github page
            * https://github.com/geopanag/pandemic_tgnn
* Evaluation
    * AVG
        * average number of cases for the specific region up to the time of the tes day
    * AVG_WINDOW  
        * average number of cases in the past d for the specific regions where d the size of the window.
    * LAST_DAY
        * number of case in the previous day is used to as predicted value of the next day
    * LSTM
        * a two layer LSTM that takes as input the sequence of new cases ina  region for the previosu weekl.
    * ARIMA
    * PROPHET
        * a forecasting model for various types of time series. the input is similar to ARIMA
    * TL_BASE
        * An MPNN that is trained on all data from three countries and the train set of the fourth
         this serves as a baselines to quantify the usefulness of MPNN+TL
# METHODOLOGY
* dataset
    * dataset is aggregated from 3 recording into 1 record. (sum all of them up)
    * we focuso n 4 european coutnries:
        * Italy, Spain, France and England.
* data preprocessing
    * we control for noisiness of the data. 
        * remove 2 region in Italy
        * remove 10 including islands in Spain.
        * do not take into account regions that had less than 10 confirmed cases in total throughout the pandemic
            * which there are in total 14 regions in Spain and 3 in Italy.
            * This is be because we assume that the scale in which this will impact will be negligible in larger scale
    * after the preprocessing, we see that for almost all regions,   the max difference encountered between consecutive days 
     is multiple times the average value of the time series
* data exploration
    * Pearson correlation
        * to exapmine time shift in foecasting 
            * ie. ranging from 1 to 14 dys ahead. 
    * overall, we can see that for most of the regions, mobility is correlated positivel with the hosrt term number of  
     cases and vice eversion 
        * same  pattern can be find for most of the regions with the exception of Spain.
* task
    * to exapmine time shift in foecasting 
        * ie. ranging from 1 to 14 days ahead. 
    * interested in short, mid, long term prediction
* graph construction
    * each country is represented as a graph
    * series of graph is created per tiem step 
    * graph is directed
    * edges 
        * edges are weighted  
        * edges capture the mobility patterns.
        * self loop is allowed. 
            * self loop = mobility behavior within the regions.
    * the mobility between regions are multiplied by the number of cases of regions for each time step
        * this provides a relative score expression how many infected individuals might have moved between nodes
        * using this, nodes can be interpreted as total cased of infected individuals
        * number of days used to computer are smooth using serveral days of data because daily data is highly irregular 
* model 
    * note: different models are trained for each value of T (time ahead to be predicted)
    * message passing neural network (MPNN)
    * MPNN
        * utlize skip connection from each layer to the output layer
        * since the nmber of the new cases is nonnegative integer, we choose the mean squared error as our loss function as
    * MPNN + LSTM
        * note: 
            * this model resemble atttempts to sptaio-temporal prediction, but instead of convolutional, it employs message passing layers.
        * MPNN + LSTM takes advatnage of the tmeporal correlation between the target and the confirmed cases in the past.
         time-series version of our model using the different snapshorts of the mobility graph.
        * sequence of representation (of each time step graph) is fed into the LSTM
        * These representation are then passed on to an output layer similar to the MPNN
    * MPNN + TL
        * note:
            differnet counties were hit by the pandemic at different imtes. 
                * eg.  
                    * there are cases where once the epidemic start developing in one country, it has already stablizied in another.
            * waves of COVID-19 pandemic should share fundamental chracteristics with thep revious ones, as it is the same virus. 
                * This is important when we have insufficient training data
            * our inuition is that a odel trained in the whole cycle or an advanced stage of the epidemic can capture patterns of 
             * its different phaes (which is information that has not yet obtained from the taret country)
        * we separate our data into tasks and propose an adaption of MAML
        additional pre-processing for MPNN + TL
# RESULT
* Experiment 1: 
    * result
        * Our error function trats all regions euqivalently, independent of the region-speicfic poupulation and the number of cases. 
            * i.e. region with 10 cases per day should not be treated the same as a region with 1000.
        * we compute the deviation between the average predicted and the actual average number of cases
            * [[re-written]] performance deviation depends on number of cases
        * one can see that ergion with the high relative error are the ones with the fewest cases. On the other hands, the reinos iwth 
         * the highest number of cases tends tohave much smaller relative error (less than  20% )
        * MPNN+TL performans the best 
        * MPNN peformans better than TL_BASE
        * TL_BASE is the best non graph baselines
# FREQUENCY ASK QUESTION 
* what is model agonostic meta-learning?

