# INTRODUCTION
# REFERENCES
# STANDARD AND BASELINE
* dataset
    * Google COVID-19 Aggregated Mobility Research Dataset.
    * COVID-19 surveillance data (CSD)
* models
    * autoregressive (AR)
    * autoregressive Average (ARMA)
    * LSTM (LSTM)
    * CNNRNN 
    * cola-GNN 
* evaluation
    * RMSE
    * Pearson correlation 
# KEY CONTRIBUTION
* we analyze the joing effects of social distancing guidelines and mobility pattenrs at US state levels using the integrated map of mobility flows (MF)
    * using COVID-19 surveillance data and adata on social distance guideline
* we design a dynamic mobility informed GNN that considers both temporal dynamics and cross-location co-evolution dynamics using a reccurrent message passing (RMP) module to recurrently embed information from a node's neighbors
# HOW AUTHOR COME UP WITH THIS IDEA
* a region's COVID-19 dynamics can potnetially be affected by regions where frequent travels occur between them. this resemble the core insight behind graph neural network models
    * transformation of the input node's signal can be coupled with the propagation aaof information from a nodes' neighbors in order to better inform the future hidden state of the original input
# FUTURE DIRECTION
# TERMINOLOGY
* mobility flow (MF)
    * intra-region mobility
        * from state i to state i in the next time step
    * inter-region mobility
        * from state i to state j in the next time step
* static mobility 
    * feature that doesn't change (or slight change) throughout the training period
* dynamic mobility
    * feature that change (or slight change) throughout the training period
* recurrent message passing (RMP)
    * it is deisgned to recurrently pass the hidden reporesentations from a node's neighbors to the current node. 
    * RMP vs message paassing (MP)
        * the only different is that in RMP, node in each graph contains input from lstm cell (temporal feature) from previous time steps.
            * learning processing for message passing is exactly the same.
# RELATED WORK
# CHALLENGES

# METHODOLOGY
* task 
    * state level daily new cases for 7, 14, 21, 28 days forcasting.
* preprocessing
    * feature encoding 
        * LSTM cell is used to embed temporal information for each time step to all nodes
            * edge feature vector include temoporal information from the past
            * node feature vectors include temporal information from the past
    * graph construction
        * edge 
            * edge represent mobility
        * node 
            * node represent state
* architecture
    * models variation
        * GNN-dmob (proposed method)
            * using output from RMP to represent nodes
        * GNN-adj
            * use adjacency metrics to represent nodes
        * GNN-smob
            * use static mobility to represent nodes 
                * average of mobility graphs from a certain period.
                    * [[re-written]] I assume that this is average of mobiility of each states across time.
        * GNN-att
            * inspired by GNN-adj
            * implement an attention-based model that llow the model to learn an attention matrix of all region.
    * implementation 
        * GNN-dmob GNN-smob, GNN-att, and GNN-adj
            * use a single layer LSMT for feature encoding with 16 units
            * a two layer MLP  in MP phase with 32 and 16 units
            * and a single layer GRU in UP with 16 unites.
            * batch size = 32
            * epoch = 1000
            * early stopping with apteince of 100 epochs.
            * all results are average of 5 random runs.
* evaluation
    * RMSE
        * use to measure performance of model
    * Pearson correlation (PCORR)
        * use to measure performance of model + data profiling.
# RESULT
* Prearson correlation
    * COVID-19 dynamics and human mobility are highly correlated.
        * Figure 2 shows the Pearson correlation along the weeks. 
            * we observe that mobility flow and new confirmed cases show very high negative correlation (median -0.97) for almost all states during March when most of states mandated school closure and stay-at-home orders.
    * the best performance on PCORR are evently distirbuted among the proposed models
* cola-GNN and GNN-att  are not outstanding for both short and long-term forecasting.
    * g2020usinga possible reaons is that the learned attention coefficients are outdated due to the fast evolution of COVID-19 dynamics between trainging time period and testing time period which lead to false attention by regions while predicting
        * see figure 3 ( Heatmap of Pearson correlation matrix of state level time series of new confirmed cases. )
* the purposed methods GNN-dmob explicitly project the most recent mobility pattens to the future potentially leading to bettern perofrmance.
# FREQUENCY ASK QUESTION 
