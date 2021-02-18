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
* modelling the COVID-19 Graph 
    * formulate as regression learning task
    * node = locations
        * connected to arbitrary number of other nodes
    * edges weight corresponds to measure of human mobility between the nodes
    * multiple edges types are used
    * In spatial domain, edges represent direct location-to-location movement and are weighted 
     based on amount of inflow internal to the location.
    * in the temporal domain, edges simply represent binary connections to past days.
    * graph
        * graph has 100 stacked layers 
* task 
    * model is trained to predict the change in the number of cases on date t +1
* model
    * Architecture
        * 4 layers
            * initial embedding layers (MLP)
            * spatial aggregation
            * final prediction layer (MLP)
# RESULT
# FREQUENCY ASK QUESTION 
* what is mobility dataset?
    * mobility report is brokendown by location and siplay the change in visits 
     to places like grocery stores and parts
