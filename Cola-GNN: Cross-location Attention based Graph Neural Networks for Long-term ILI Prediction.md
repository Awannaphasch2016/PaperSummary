:dynamic graph neural network:spatial attention:
# REFERENCE  
* url
    * https://dl.acm.org/doi/pdf/10.1145/3340531.3411975?casa_token=Y1z6Ah7SqZoAAAAA:pqgVk23Anq9o5TiZ6BtyysPPF1uGsP8nAhT92vGPlr2NiHgt6a7xG-MWzLKLU_f2-lBAC1L02CnF4w
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
    * models
        * deep learning
            * CNN
                * it capture various important local patterns from grid data and sequence data.  
                *  [40] shows effectiveness of Dilated convolution to extract local patterns on images
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
* simulation
    * simultaating all the factors related to a flu outbreak is difficult.
# terminology 
* ILI
    * influenza-like illness (ILI)
* dynamic location-aware attention machanism
* element-wise gate 
    * adapted from "feature fusion gate [14]"
* [40]'s dilated convolution
    * which is good for extract local patterns on images.
* [21] multie-scale dilate dconvolutional module
    * consist of multiple parallel convolutional layers with the same filter and stride size but different dilation rate
            * capture short-term and long-term lcoal termporal dependencies 
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
        * Infectious Disease Weekly Report (IDWR) in Japan dataset
            * Japand-Prefectures
        * Center for Disease Control (CDC) dataset
            * Us-state
        * US-HHS (department of Health and Human Service) dataset
            * US-Regions

* Evaluation metrics
    * RMSE
    * MAE
    * Pearson's Correlation (PCC)

* baseline Models
    * Autoregressive (AR)
    * Global Autoregressive (GAR)
    * Vector Autoregressive (VAR)
    * Autoregressive Moving Average (ARMA)
    * RNN
    * LSTM
    * RNN + Attn [7]
    * DCRNN
    * CNNRNN-Res
    * LSTNet
    * St-GCN

# methodology
* goal
    * focus on longer term (2-15 weeks) prediction from 20 weeks of data
* architecture
    * 3 modules
        * location-aware attention 
            * capture location-wise interations
                * correlation of two locations can be affected by 
                    * their geographic distrance
                    * population movement
            * 2 components
                * attention coefficient matrix 
                    * RNN is applied to each nodes features to embed temporal information.
                    * An element in adjency metrix is represented by general attention coefficient 
                        * general attention coefficient is computed to measure impact of location j and i. 
                        * Normalization is applied over each row, to normalize the impact of other location on one location. 
                            * nomalization's formular is as followed.
                                * $\mathbf{a}_{i:} \longleftarrow \frac{\mathbf{a}_{i:}}{\max \left(\left\|\mathbf{a}_{i:}\right\|_{p}, \epsilon\right)}$
                                    * where $\epsilon$ is a small value to avoid division by zero, and $\|\cdot\|_{p}$ denotes the $\ell_{p}$ -norm.
                * geographical adjacency matrix  
                    * 1 for states that are neighbors otherwise 0
            * location-aware attention 
                * equation
                <!--  $$ -->
                <!--     \begin{aligned} -->
                <!--     \tilde{\mathrm{A}}^{g} &=\mathrm{D}^{-\frac{1}{2}} \mathrm{~A}^{g} \mathrm{D}^{-\frac{1}{2}} \\ -->
                <!--     \mathbf{M} &=\sigma\left(\mathbf{W}^{m} \mathrm{~A}+b^{m} \mathbf{1}_{N}{\mathbf{1}}_{N}^{T}\right) \\ -->
                <!--     \hat{\mathbf{A}} &=\mathbf{M} \odot \tilde{\mathrm{A}}^{g}+\left(\mathbf{1}_{N}{\mathbf{1}}_{N}^{T}-\mathbf{M}\right) \odot \mathrm{A} -->
                <!--     \end{aligned} -->
                <!--     $$ --> 
                    * $A^g$ is geographical adjacency matrix which indicate the connectivity of location. 1 if connected otherwise 0. 
                    * A is attention coefficient.
                    * M is an element-wise gate learned from general attention matrix that evolves over time.
                        * gate M is adapted from feature fusion gate [14]
                    * D is degree matrix defined as $d_{i i}=\sum_{j=1}^{N} a_{i j}^{g} . \mathbf{W}^{m} \in \mathbb{R}^{N \times N}$
                    * the rest are trainable parameteres
        * dilated convolution layer 
            * this is used for node attributes
            * adapted from the following
                * [40]'s dilated convolution
                    * which is good for extract local patterns on images.
                * [21] multie-scale dilate dconvolutional module
                    * consist of multiple parallel convolutional layers with the same filter and stride size but different dilation rate
            * capture short-term and long-term lcoal termporal dependencies 
            * we apply 1D CNN filter with different dilation to every row of X to capture temporal dependencies at different level of granularity
        * global graph message passing
            * combine the temporal features and location-aware attenions. 
    * graph construction
        * Edges
            * the author recognized that  there are 2 factors that could have affected the forecasting.
                1. correlation of two locations can be affected by thier geographic distance.
                    * i.e. nearby areas may have similar topographic or climatic characteristics that make them have similar flu outbreaks.
                2. non-adjacent areas may alos have potential dependeincies due to population movements and similar geographical features.
            * the author propose a location-aware attention emchanism which take into account the temporal dependencies of locations from historical data as well as geographical information.
        * 
    * loss function
        * optimize regularized l_1-norm loss via gradient descent.

# result
* attention 
    * region with higher attention score shares more similar trends, while the low attention region has a visibly different pattern
    * with the proposed methods, some non-adjacent regions also receive high attnetion values in attention matrix.
* hyperparameter
    * features size 
        * features of smaller dimension result in poor predictive performance due to limited encoding power.
        * as features dimension is larger, model performs better 
    * leadtime 
        * On US_region, Us-state, leadtime = 2,5,10,15. GRU and LSTM is not better than RNN.
            * reason might be 'overfit'
    * Number of filters
        * perform sensitive analysis on differnet number of filters and results
            * start with number of filter = 10, increase filters -> reduce performance
                * reason might be because increase filter -> more parameters -> easier to overfit due to limited number of training data.
# frequently ask question 

