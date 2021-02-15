introduction
key contribution
    we proposed Saptio-Temporal Attention Network (STAN) for pandemic prediction  
        it use graph attention entwork to capture spatio-temporal trend of disease dynamics 
    we design a dynamic based loss term for enhancing long-term prediction.
    STAN outperforms traditional epidemiological models such as SIR, SEIR, and deep learning models 
     on both long-term and short-term prediction achieving up ot 87 percent reduction in MSE
related work
    epidemic/pandemic prediction model
        usually use curve-fitting or autoregression.
how the author come up with the idea
    deep learning model, SIR, and SEIR suffer sfrom 3 chllenges
        they usually build a separate model for each location 
            doesn't account for geographic proximity and interaction with near by regions
            forecast only dpendso n some obsered pattenrs from other location 
                no inter-regional interactions location are are direclty models
        existing model are built on COVID-19 case report data. These data are konwn to hve sever under reporting or other data quality issues.
        Epidemiological models such as SIR and SEIR are deterministic models.

terminology
standard and benchmark
    dataset
        patients' claims data form different coutnies and states that capture local 
         disease status and medical resource utilization
        utlizing the demographic similarity and geographical proximity between location
    model 
    evaluation
        MSE
methodology
    note: the study has been detemined by UIUC IRB as non-human subject research
    task 
        predict number of infected pateitns for a fixed preiodd into the future with tranmission dynamic of epidemiological models constraint
    dataset 
        network data
            dynamic data    
                3D tensor with location, timestamp, and dynamic features at each location
            static data 
                2D matrix includes location and the static featurs for each location
    Graph construction
        attribute gaph is formed to capture the spatio-temporal epidemic/pandemic dynamics
        we model the geographic proximity and demographic similarity beween the different locations as edges in a location graph.
             
    model architecture 
        GAT to capture the geographic trends in disease transmission
        GRU that captues the temporal disease patterns at each location
        loss function
            transmission dynamics constraint loss regularize learned node embedding.
    

experiment
frequently ask question
