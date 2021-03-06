# REFERENCES
* Papers
    * already collected citation 
        * [1] Examining COVID-19 Forecasting using Spatio-Temporal Graph.md
        * [2] Transfer Graph neural Networks for Pnademic Forecasting.md
        * [3] Spatio-temporal attention network for pandemic prediction using real world evidence
        * [4] Crosslocation attention based graph neural networks for long-term ILI prediction
        * [5] Combining Graph Neural Networks and Spatio-temporal Disease Models to Predict COVID-19 Cases in Germany
        * [6] On the Interplay of Regional Mobility, Social Connectedness, and the Spread of COVID-19 in Germany
        * [7] STAN-Spatio-Temporal Attention Network for Pandemic Prediction Using Real-World Evidence.md 
        * [8] Cola-GNN: Cross-location Attention based Graph Neural Networks for Long-term ILI Prediction.md
        * [9] DeepCOVID: An Operational Deep Learning-driven Framework for Explainable Real-time COVID-19 Forecasting.md
        * [10] Steering a Historical Disease Forecasting Model Under a Pandemic: Case of Flu and COVID-19
    * haven't yet collected citation 
        * Survey 
            * [11] Forecasting Models for Coronavirus Disease (COVID-19): A Survey of the state of the art
        * paper
            * COVID-SGIS: A Smart Tool for Dynamic Monitoring and Temporal Forecasting of Covid-19
            * Estimating, Monitoring, and Forecasting the Covid-19 Epidemics: A Spatio-Temporal Approach Applied to NYC Data
            * Spatiotemporal Dynamics, Nowcasting and Forecasting of COVID-19 in the United States
            * Population flow drives spatio-temporal distribution of COVID-19 in China
            * Novel spatiotemporal feature extraction parallel deep neural network for forecasting confirmed cases of coronavirus disease 2019
            * A Spatiotemporal Epidemiological Prediction Model to Inform County-Level COVID-19 Risk in the United States
            * Time series forecasting of COVID-19 transmission in Canada using LSTM networks
            * COVID-19 Infection Forecasting based on Deep Learning in Iran
            * A Recurrent Neural Network and Differential Equation Based Spatiotemporal Infectious Disease Model with Application to COVID-19
* individuals 
    * Alexander Rodríguez
        * https://www.cc.gatech.edu/~acastillo41/
# RELATED WORK
# KEY CONTRIBUTION
# CHALLENGES
* covid19 forecasting's challenges
    * heterogenous input
    * limited dataset (low volume of dataset)
# TERMINOLOGY
# STANDARD AND BASELINE
* Model
    * GNN based model
        * [1], [2], [3], [4]
    * baseline
        * temporal 
            * RNN + Attn
                * Paper: Long Short-Term MemoryNetworks for Machine Reading
        * spatial temporal 
            * St-GCN
                * Paper: Spatio-temporal graph convolutional networks: A deep learning framework for traffic forecasting.
        * CNN + RNN
            * CNNRNN-Res
                * Paper Deep Learning for Epidemiological Predictions
* dataset 
    * policy dataset 
    * mobility dataset
        * [2], [5] 
    * social connectedness (colocation network)
        * [5], [6]


# METHODOLOGY
## techniques that other papers uses
* capture temoral info 
    * paper: Cola-GNN: Cross-location Attention based Graph Neural Networks for Long-term ILI Prediction.md
        * use multi-scale dilated convolution to capture temporal data
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
# Furthre Reading
* understand rnn model.
    * goal
        * to be aware of parameters that I can model. 
    * how to formulate rnn equation from scratch
* how does attention in time seires work?
    * what are types of attention in time series?
        * additional attention
            * reference:
                * Paper: Neural machine translation by jointly learning to align and translate

# Notes by Sections
## ToC
## Introduction

* Influenza is a seasonal virus which affects 9–45 million people annually in the United States alone resulting in between
12,000–61,000 deaths
* forcasting is ahrd because the following
    * confounding socila, biological, and demographic factors
* accurate forecast can help politician make decision 
*

# FREQUENCY ASK QUESTION 
* how does survey paper sections?
    * see other covid19 survey papers to see how sections are devided.

