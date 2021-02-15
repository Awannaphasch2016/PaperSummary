
my model design
    sytem requirement
        the model must use as many types of network as possible
        the model must use transfer learning
            to tranfer learned knowledge about "stage" of the pandemic spread
                transfer knowledge about first wave to second wave
                transfer knowledge from one location to another location
        the model must do nodes and edges attention
            node attention 
                weight between neighbor nodes and target node
                eg GAT
            edge attention is 
                weight between target nodes and its neighbor
        the model must deal with few dataset
        the model must deal with noisy data
        
input data                 
    non-graph input
        demographics
        economics
        politics
        covid cases 
        traffic
        airplain
        news
    types of network (network dataset)
        mobility
        correlation network
        weather newtork
        social connectedness network
        colocation network 
        geographic similarity


Papers
    Model
        GNN based model
            [1], [2], [3], [4]

    dataset 
        policy dataset 
        mobility dataset
            [2], [5] 
        social connectedness (colocation network)
            [5], [6]

reference 
    [1] Examining COVID-19 Forecasting using Spatio-Temporal Graph.md
    [2] Transfer Graph neural Networks for Pnademic Forecasting.md
    [3] Spatio-temporal attention network for pandemic prediction using real world evidence
    [4] Crosslocation attention based graph neural networks for long-term ILI prediction
    [5] Combining Graph Neural Networks and Spatio-temporal Disease Models to Predict COVID-19 Cases in Germany
    [6] On the Interplay of Regional Mobility, Social Connectedness, and the Spread of COVID-19 in Germany
    [7] STAN-Spatio-Temporal Attention Network for Pandemic Prediction Using Real-World Evidence.md

