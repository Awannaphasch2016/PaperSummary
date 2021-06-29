# CHALLENGES
# INTRODUCTION
# NOTE
# REFERENCES
# RELATED WORK
# REQUIREMENTS
# KEY CONTRIBUTION
# WHAT HAVE WE DONE
# CHALLENGES
# TERMINOLOGY
# STANDARD AND BASELINE
# METHODOLOGY
Above use of attention lead to conflicting result to conclude whether attention mechanism is actually helping
the model learns.
Jin, Wang and Yan at el. \cited{jin2020inter} showed conclusive result on the use of inter-series attention. 
Window slidings separate a time series into many period of fixed length.
To predict a target state time series, ACTS \cite{jin2020inter} is train to obtain inter-series attention between 
a window of the target time series, a target region, and other time series, referenced regions.
ACTS have 3 main components including: Detrending, Segment Embedding, and Inter-series attention.
One of the key contribution of the paper is detrending module.
The authors utilized holt exponential smoothing to predict level and trend of the time series and subtract the
predicted value from the actual trend resulting to capture characteristic of the curve. 
This process allow the predictive part of the model to easily learn characteristic of target time series.
After detrending process, the scales of reported numbers in residual time series are stil lquite differnet
across regions. 
Therefore, it is important to normalize residuals before embedding.
Then, conv-1D are applied to embed time-series.
The paper doesn't construct a graph for learning, however, the paper showed, during the model evaluation, that
attention from data can capture similarity between regions. 
This finding point to the future research suggesting that training models on similar epidemic time series
could improve performance.
# RESULT
# FREQUENCY ASK QUESTION
