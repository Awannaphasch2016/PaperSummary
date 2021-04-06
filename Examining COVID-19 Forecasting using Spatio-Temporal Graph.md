# INTRODUCTION
# REFERENCES
* url
    * https://arxiv.org/pdf/2007.03113.pdf
# RELATED WORK
* paper to read
    * [1,34]
    * [31]
    * [25]
    * [10]
# KEY CONTRIBUTION
# TERMINOLOGY
* spatio-temporal GNN
    * spatio-temporal GNN model connection between nodes as a function of time and space. 
* Skip-Connections Model
# STANDARD AND BASELINE
* model
    * note: baselines do not utilize any mobility information
    * previous day
        * for previous delta, predict that delta in the number of case will be the same.
        * fro Previous CAse, we predict that delta in the number of cases will be 0
    * ARIMA
        * the model treats the time dependent dialy new cases as a univariate time series 
         that follow a fixed dynamic 
    * LSTM and Seq2Seq
        * LSTM
            * stake 2 LSTM layers and final base layer
        * Seq2Seq 
            * encoder-decoder architecture
                * encoder
                    * fully connected dense layer + GRU layer 
                * decoder
                    * inverse of encoder
                * Bahdanau attention is applied on the sequence of encode output 
                 at each decoding 
* dataset
    * the New York time (NYT) COVID-19 dataset
        * https://github.com/nytimes/covid-19-data
    * the Google COVID-19 Aggregated obility Research Dataset
    * Google Community Mobility Reports

# METHODOLOGY
* limitation of mobility dataset
    * data is limited to smartphone users who have opted into Google's Location History features
* graph construction
    * spatial graph
        * time series make a poor fit for modeling human mobility across locations.
            * mobility data is naturally represented as a spatial-graph,
                * where any individual node represents a location i that is  connected to an arbitrary number of other nodes. 
                * where edges weight correspond to measure of human mobility between the nodes.
        * node = locations
            * connected to arbitrary number of other nodes.
        * edges 
            * represent direct location-to-location movement 
            * edges weight
                * correspond to measure of human mobility between the nodes.
                * weighted based on mobility flows normlalized against the intra-flow
                    * in the other words, the amount of flow internal to the location.
    * temporal graph
        * edges 
            * in the temporal domain, edges simply represent binary connections to past days.
            * edges simply represent binary connection to past days.
* task 
    * in infectious disease modeling, we usually ahve multiple time-series sequences that represent the observables of tranmission dynamics in each location.
    * the prediction problem is uaully formulated as a regression learning task taht takes in a certain time series, and outputs a single value t+1 or future time.
        * model is trained to predict the change in the number of cases on date t +1
* architecture
    * model
        * Architecture
            * 4 layers
                * initial embedding layers (MLP)
                * spatial aggregation
                * final prediction layer (MLP)
            * GNN has 100 stacked layers 
        * algorithm 
            * for each time step
            1. temporal node embedding is computed by using past N days of the same nodes.
            2. N-hop spatial aggregation function (GNN message passing in this case) is performed.
            3. 1-2 is repeated for the next timestep.
# RESULT
# FREQUENCY ASK QUESTION 
* what is mobility dataset?
    * mobility report is brokendown by location and siplay the change in visits 
     to places like grocery stores and parts
