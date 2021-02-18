#table of content
* section 1
    * introcution and related work
* section 2 
    * data
* section 3 
    * lays out the ground work contribution proposed in Section 4
* section 4 
    * describe proposed model
* section 5  
    * apply the propsed approach to Germany weely data

#introduction 

#key contribution
* we proposed a trade-off between statistical/epidemiological models and machine learning model
    * statistical/epidemiological models often can't directly incroporate unstructured data source
        * including relational data that my encode human mobility 
    * machine learning  yeirld better prediction by exploiting thse data strcuture, but lack of intuitive interpretability
* purpose a novel fusion appraoch that directly combine dyadic mobility and connectedness data 
* we combine GNN and epidemiological models to simultaneously account for network-values data and talbular data. 
* we provide a forcast of weekly COVID-19 cses with disease onset at the local level of 401 federal districts in Germany
 as provided by the Robert-Koch Institute
* the primary goal our our applicatin is modeling the rates fo infections rather than the raw observed count.

#related work
* paper to read 
    * [8-9] use mobility data
    * [10] estimate the effects of non-pharaceutical intervention on COVID-19
    * [13] forecating the spread of covid nder different reopening strategies
    * [18] use mobility and aggreagted friendship networks to discover how these networks derive the infection rate on the lcoal level 
     of federal dsitrubtion in Germany
        also use colocation network 
    * [35] shows that the central indicator of the infection occurrence is the number of people with disease onset at a specific day
* [41-47] a recent trend is the cobination of neural networks with statistical regression model in various ways 

#terminnology
* about data
    * colcoation probability
    * colocation network
     * this indicate the prob of two random persons from two district to meet one another during a given week     
    * colocation matrix 
        * the probability of an arbitrary person to meet another person from the same or different district
    * social connectedness network
        * network is a soail connection between the distict via facebook friendship
        * this pairwise time constant index related to the relative friendship stregth between two districts 
        * network is weighted.
    * social connectedness index 
    * staying put   
        * weekly percentage of peopel staying put as a measure for people's compiance (Facebook users0 with 
         social distancing
        * we derive the weekly district-speicif measure by averagin daily measure provided by FAcebook.
        * In this context, 'staying put' is defined as being observed in one 0.6km x 0.6km square throughout a day 
    * disease onset
        * the disease oneset is the first time that there has been notes to be a "change" in one's usualy health 
         status with the identified signs and or symptoms being able to directly attributable to a specific disease process 
* about math
    * aleatoric uncetainty
    * zero-inflated distribution
        * distribution that allows for frequent zero-value observation.
        * it is often used as a model for the number of events in a specifict time period
    * zero-inflation probability
    * zero-inflated Poisson (ZIP) distribution
    * probability mass function (PMF)
        * is a function that gives the probability that a discrete random variable is exactly equal to some value.
        * aka discreate desnsity function
    * negative binomial (NB) distribution
    * radial basis function
    * epistemic uncetainty
    * Hessian of the negative log-likelihood        
    * deep embedding
* about model 
    * additive effect
        * when two predictors do not interact, we say that each predictor has an "additive effect' on the response.
            * More formally, a regression model contains additive effects if the response function can be written as a 
             sum of function of the predictor varialbes
    * additive predictor 
        * structure additive predictor
            * representa mooth additive effectos of input features and can be reresented in a neural network.
            it can be represented in neural network term
    * distributional regression
        * a modeling approach  
        * in constrast to other regresssion appraoches that (do only related the mean of an outcome ariable to certain features, 
         distributional regression also accounts for the uncertainly of the data distribution, known as aleatoric uncetainty
    * semi-stuctured deep distribution regression
    * SDDR 
        * combines neural enworks and structued additive distibutional regression by embedding the statistical regression in 
         the neural network and ensure the identificability of the reression model part.
        * SDDR extend the additive prediction of each distributional parametres with its 'structured effect' to laten features
            ,so called, 'unstructured effects' taht are learned by one or more DNN
        * to disentangle the structured model parts from the unstructured parts, and orthogonalization cell is used to ensure 
         identifiability of the structured model effect 
             


#standard and benchmark
* dataset
    * Facebook data on human mobility and connectedness 
        * [28]
        * spatial data from Data for Good program 
            * it is on the NUTS 3 level
            * encompass n = 401 federal districts
            * collected from mobile phoen location traces of FAcebook users that opted in the Location Histroy setting 
                 on the mobile Facbook app
    * data on the pandemic's state from Robert-Koct-institue.
        * Time-series of daily COVId-19 infections
* models
    * baseline model
        * mean of a sliding window apprach applied to the given training data set (MEAN)
            * mean of last week for each of the subgroups = prediction 
                * 4 subgroups includes age, gender, etc
    * statistical baseline model 
        * generalized additive model (GAM)
            * inspired by work from [18], which modeling the mean of a negative binomial distribution using various smooth predictors and 
             tensor-product splines.
    * state of the art machine learning baseline
        * XGBoost (gradient boosting tree.)
    * deep learning baseline 
        * valina deep learning (multi-layer)
    * GNN baseline
        * GNN 
* Evaluation         
    * MSE score


# methodology
* data preprocessing
    * Facebook data on human mobility and connectedness 
        * to quantify the social and mobility pattenrso nthe regional level, we use data on friendship ties, colcoation probability
         ,adn district-specific data on the proportion of peopl staying put provided by Facebook.
    * Robert-Koct-Instritue dataset
        * we obtain the number of people with symptom onset and registered cases of COVID-19 grouped by age, gender and federal district 
         (NUT-3 level) for each day
        * we observed that mainly people aged between 15 and 58 years are actice users of FAcebook 
        * we limit our analysis to corresponding age groups, namely, people with age between 15,35 and 36,59
        * we impute the missing values by learning a proabilistic model of the delay between disease onset and registration dat.
            * the data of disease onset is not known in about 30% of the cases.
            * we sampled form the estimated distribution of delay times.
        * we compute population density
        * we use population density compute ratio between infected population and total population
            * In this settings, one can assuem that not the count but rate of infections in a specific district and group carries vital information
* Network contruction 
    * colocation network
        * we obtain for each week a colocation matrix
        * we transform it to tabular data
            * followed [18]
        * we use the Gini index to measure the concentration of meeting  patterns of districts
            * higher values translate to a restricted meeting pattern within a district
            lower value suggest rather disffused social beahvior 
* social connectedness network
    * utilizing information from a snapshot of all facebook connections within Germany of April 2020
    * we derived a Social Connectedness Index
* model 
    * effect smoothness can be achieved by a specifically designed network regulatization term
    * we make use of semi-structued deep distributiona lregression [SDDR, 48]
    * Combining network values and spatio-temporal disease data
        * we present out hypbrid modelign appraoch to forecast weekly district-wise OCVID-19 cases based on structured and unstructued data sources described in section 2.
        * neural network formulation 
            * distributional assumption
                * we considered time window over a low-infection phase diruing which 20-30% of the observations reported no cases.
                * this phase is delimited by two primary infection waves
                * we use zero-inflated  distribution
                    * our goal is to build a model that can adequately predict high numbers as well as zero observation.
                        * which are common during low-infection seasion 
                    * the distribution is characterzed by the mean of the count component and the zero-inflation probability
                * by incorpoarting the point mss distribution, the model can capture excess rate of zero observatio.
                * zero-inflated distribution is used to relate structured data and network data together as its parameters.
                    * zero-influated distribution yeilds distributional and structural assumption
                * to garantee correct domains of the model parameters, we transform these predictors via its fixed transformation function. 
                    * this penalization can be seen as a trade-off between complexity and interpretability [58]
            * additive predictor 
                * Inspired by SDDR [48], we estimate additive effect of tabular features on the prarmeters characterzing the zero-inflated distribution using 
                 a single neuron hidden layer.
                * as proposed by various statistical COVId-19 modeling approaches [18,57],we learn these strucuted effects with an appropriate regularization to enforece
                 smoothness of non-linear effects.
                * the additive predictors can be defined in terms of both unstructured and structure features.
                    * In the structured data, we use district-specific features.
                    * for unstructure part of the network, we compute district's embedding node by exploiting time-constant district population attributes and edge attributes
                        * for our application, these attributes encode geographic connecedness bewteen districts and social connectedness
            * Orthogonalization
                * Identifiability is crucial to our analysis because some features is shared bewteen the structured and unstructued effect.
                    * MDS-embeddings component
                    * GNN component
                * we do this by projecting GNN embedding to its orthogonal vector which is used instead of original GNN embedding
                * structure and unstructure effects are combined as a sum of linear orthogonalized embedding effects and the structure predictos
            * different exposures in count regression
                 * distribution is adjusted for population size by adding a constant offset term to the ocncatenated linear predictor 
                    * for more info on this procedure related to zero inflated models, refer to [59]
        * proposed COVID-19 models specification
            * we reprarmeterize the distribution in term of 1 aditive predictor
                * this proved to help numberical stability
            * Graph Neural network
                * we use model proposed in [60] because it can handle edge attributes and relatively large graphs.
    * Uncertaintey quantification
        * epistemic uncertainty 
            * we can derive epistemic uncertainty of parts of the model throught its connection to statistical model
            * we note that especially the conditioning on GNN neglects some dditional variance in the paraters estimates but still allows us 
             to get a feeling for the network's uncetainty
            * to account for the epistemic uncertianty of the GNN, we use deep ensemble [64]
                * it is known to result in reliable uncertainty estimates.
                * In this context the epistemic unceratinty acn be estimated by computing the standard error of the prdictions of an ensemble of models, 
                 each trained from scratch with a different random intialization 
            * we compute the standard errors of all predictors from (10 different runs with different random initialization)
        * Aleatoric uncertainty. 
            * our model account for aleatoric uncertianty by modeling all the distiubtional parameters of the zero-inflated count distirution explicitly.
    * model training 
        * loss fnction
            * under conditional independence, features weights can be learned by minimizing the sume of negative log-liklihood contribution for 
             all observation.
        * penalization
            * to avoid ovefitting and estimate smooth additive effects in the structured part of our model, we add a quadratic penalty term.
                * we regularize weight in the network that correspond to smooth strctre effects.
            * penalization is controlled by indvidual complexity parameters that we incorporate in the penalty matrics. 
            * These matrices are block-diagonal matrices that are dervied by the chosen basis functions in the structured model parts. 
            * we donot penalize the count parameters or GNN model aprts. For that we only use Orthogonalization. 
* Evaluation
    * to enable a meaningful comparison, we corrected all benchmark modle outputs for the differeing exposures by incorpoarting an offset in same 
     * way as explains

#Experiment 
* Experiment 1: forecasting performance
* Experiment 2: Model interpretation
    * result
        * we analyze partial efect of its structued additive part by focusing on two instances of our models that are trained with data until calendar 
            * week 30 and 44. 
                * both are picked to show performance during high and low.
        * Effect of Gini coefficient  
            * high standardized gini coefficeint translate to metting behavior that is more dispersed than the average of all districts. 
                * Therefore, low standarded gini coefficient (less mobility than average) leads to lower infection rates
            * incorporated penalty term sccessfully regularized the bivariate effect term to be a linear effect in the direction of percentage of people staying put.
        * Epistenmic uncertainty
            * the higher the infection rate was tin the previous week, higher the rpedictions are the upcoming week
                * [18] identified this feature as a principal driver of the structured model part of our model

#frequently asked question
* does the facebook user's data represent the actual population?
    * what is the age distibution of Facebook user?
    * what is the differences between facebook activity of people of the different age branket?
* in distributional regression, what does 'effect type' mean?
* what is semi-structure deep distributional regression?
    * what is the use case of it? when to use it ?
* negative binomail distribution vs poisson distribution?
    * negative binomial is often chosen over the Poisson becuase it is more flexible by allowing to account for overdispension.
* what is spline function        
* offset?
    * [[re-wrriten]] it is refered often in the modle but i am not sure what is it


