# NOTE
* It seems that this is one of the earlier papers that use graph input.
    * it doesn't use mobility release by Google or Facebook to quantify mobility value.
# ToC
# INTRODUCTION
# SUMMARY
# REFERENCES
* url
    * https://arxiv.org/ftp/arxiv/papers/2008/2008.04215.pdf
# RELATED WORK
* epidemic/pandemic prediction model
    * usually use curve-fitting or autoregression.
# HOW THE AUTHOR COME UP WITH THE IDEA
* deep learning model, SIR, and SEIR suffer sfrom 3 chllenges
    * they usually build a separate model for each location 
        * doesn't account for geographic proximity and interaction with near by regions
        * forecast only dpendso n some obsered pattenrs from other location 
            * no inter-regional interactions location are are direclty models
    * existing model are built on COVID-19 case report data. These data are konwn to hve sever under reporting or other data quality issues.
    * Epidemiological models such as SIR and SEIR are deterministic models.
# KEY CONTRIBUTION
* we proposed Saptio-Temporal Attention Network (STAN) for pandemic prediction  
    * it use graph attention entwork to capture spatio-temporal trend of disease dynamics 
* we design a dynamic based loss term for enhancing long-term prediction.
* STAN outperforms traditional epidemiological models such as SIR, SEIR, and deep learning models 
 * on both long-term and short-term prediction achieving up ot 87 percent reduction in MSE
# CHALLENGES
# TERMINOLOGY
# STANDARD AND BASELINE
* dataset
    * patients' claims data form different coutnies and states that capture local 
     disease status and medical resource utilization
    * utlizing the demographic similarity and geographical proximity between location
* model 
* evaluation
    * MSE


# METHODOLOGY

## note: the study has been detemined by UIUC IRB as non-human subject research
* task 
    * predict number of infected pateitns for a fixed preiodd into the future with tranmission dynamic of epidemiological models constraint

* preprocessing
    * network data
        *{ dynamic data    
            * 3D tensor with location, timestamp, and dynamic features at each location
        * static data 
            * 2D matrix includes location and the static featurs for each location
    * Graph construction
        * attribute gaph is formed to capture the spatio-temporal epidemic/pandemic dynamics
        * we model the geographic proximity and demographic similarity beween the different locations as edges in a location graph.
        * attribute graph
            * attributed graph capture the spatio-temporal epidemic/pandemic dynamics.
                * we model the geographic proximity and demographic similarity between the different location as edges in a location graph
            * node
                * static features
                    * latitude, longitude, population size, population density, 
                * dynamic features
                    * number of active cases, current number of hospitalization and ICU stays due to COVID19 
                        * ICU stays is extracted from claims data according to the Centers for Disease Control and Prevention guidline.
            * edges
                * edges are based on the idea that disease transmission pattens hightly depend on crowd mobility. 
                    * In the other word, crowd mobility is proportional to population size and is inverse proportional to distance.
                    * this also assume that a pair of nodes have high mobility rate, we expect that the nodes have the similar disease spread rate.
                    * [[re-written]] It is worth mentioning that edges are not directed which seems to defeated the purposed of capturing human mobility.
                    * our process includes a nedge with a large weight between such as pair of nodes.
                * the edges are constructed based on geographical proxmity and the population sizes of the nodes (i.e. location)
                * we designate the weight of an edge between nodes i and j as <equation> where p is population size of a node, d is the geographical distance between \alpha, \beta, and r are hyperparameter.
                    * equation 
                        * $$w_{i j} \propto p_{i}^{\alpha} p_{j}^{\beta} \exp \left(-\frac{d_{i j}}{r}\right)$$
            
* model architecture 
    * GAT to capture the geographic trends in disease transmission
        * We use the latest valuesfrom historical data within a sliding window to construct the graph.
    * GRU that captues the temporal disease patterns at each location
    * loss function
        * transmission dynamics constraint loss regularize learned node embedding.
# RESULT
# FREQUENCY ASK QUESTION 




