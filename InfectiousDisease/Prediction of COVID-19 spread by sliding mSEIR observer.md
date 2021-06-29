# note to self: no smaller detail. only big picture. smaller detail should be
* I have doubt about validation process of this paper.
    * no data preprocessing were done to make the training and test set more similar. 
        * training mostly have positive rate of change, test mostly (if not all) have negative rate of
            change.
            * training and test set doesn't really resemble each other. is this evaluation process
                legit?
# citation
@article{chen2020prediction,
  title={Prediction of COVID-19 spread by sliding mSEIR observer},
  author={Chen, Duxin and Yang, Yifan and Zhang, Yifan and Yu, Wenwu},
  journal={Science China Information Sciences},
  volume={63},
  number={12},
  pages={1--13},
  year={2020},
  publisher={Springer}
}
# further reading
* the network epidemiology models [13, 14]

* Wang et
al. [23] proposed a network inference model, which can reduce the individual-based network
into a subpopulation network without loss of information, and incorporated the power-law
distribution prior and
data prior for better performanc
    * It extended the widely accepted susceptible-infected-removed (SIR)
    model to a metapopulation SIR model.

* many recent researches
have been conducted to predict and control epidemic spreading in social systems via a network
analysis
strategy [25–29

# introduction

* Infectious
and infected individuals are all proactive individuals whose behaviors have a serious impact on the
development of the disease, and they also adapt to changes in the external situation

* refer to modern social network properties as explaination for global epidemic.
    * the small-world network feature of our living society makes the radius of the spread of
    diseases or rumors bigger and bigger, which makes it easier to spread diseases [5,6]
    * On the other hand, the
    real society network has a high clustering coefficient. 
        * Concerning disease spread, contact
        between families
        and communities accelerates the speed of transmission and expands the scope of transmission [7,
        8]
        * "Influenza spread on context-specific networks lifted from interation-based diary data"
            provides furthre evidence on it 

* social network has a small-world features

# Key contribution
# related work
* Concerning disease spread, contact
between families
and communities accelerates the speed of transmission and expands the scope of transmission [7,
8]

* Recently, many epidemiological models have been proposed to reveal the spreading
dynamics of virus and disease in different population structures, such as the compartment models
[12] for
small-scale, well-mixed populations, and the network epidemiology models [13, 14] for individuals
with
complex contact relationships in a regional population.

* For epidemic spread in large-scale spatial regions,
the most widely adopted model is the metapopulation model, which refers to a group of separated
subspecies of the same species connected by an interacting network
    * Concerning large-scale epidemic
    outbreaks, such as the global spread of influenza, the dynamics can be simulated for the
    transmission of
    pathogens through a metapopulation network [15], in which the cities in different countries are
    described
    as subpopulations, and human flows between cities are modeled as edges connecting subpopulations
    * The
    metapopulation model has been successful in the study of large-scale pandemic spread
        * For instance,
        previous studies [16,17] used the worldwide cite global aviation networks to analyze the
        spread of SARS
        and H1N1 in the global urban population

The data of the mobility network of mobile phone users are
investigated [18] to analyze the malaria transmission process in Kenya

# standard 
* evaluation 
    * sliding windows of the same size
    * MSE
        * for loss function 
    * MAPE
        * for performance metric
# future direction
# challenges
 * However, because the access to
 the detailed flow data for all cities in the world and even in a country is usually impossible in
 practice,
 most of these previous studies can only use coarse-grained flow data to establish epidemic
 transmission
 networks between cities, under the assumption that all contacts and infections between individuals
 are
 homogeneous in the same city
    * With the fast development of metropolis around the world, the social
    structure within the city becomes more and more complex, and the assumption of homogeneous
    mixing
    of the population within the city is no longer valid

* Also, it is not clear whether the physical network can
approximate the general infection network of all different diseases, which further limits the
application
value of the exhaustive existing methods
    * Therefore, the method that can achieve fine-grained urban
    infectious epidemic spread analysis without the need for detailed empirical data on resident
    mobility
    is still ideal

* Deterministic models based on differential equations are difficult to
systematically simulate the virus propagation process effectively in both cyberspace and real
physical
world [19–21]. 
    * In recent years, thanks to the fast development of AI techniques and the network science
    tools, revealing the evolutionary rules of such complex systems has become traceable.
        * For instance, Fraser
        et al. [22] judged the pandemic potential of H1N1 with limited data and made an early
        assessment of
        transmissibility and severity of the outbreak of international spread, and viral genetic
        diversity
        * Wang et
        al. [23] proposed a network inference model, which can reduce the individual-based network
        into a subpopulation network without loss of information, and incorporated the power-law
        distribution prior and
        data prior for better performanc
            * It extended the widely accepted susceptible-infected-removed (SIR)
            model to a metapopulation SIR model.

* many recent researches
have been conducted to predict and control epidemic spreading in social systems via a network
analysis
strategy [25–29]

# terminology
* trust region reflective algortihm
# dataset
# methodology
* research study assumption 
    1. total population is constant
    2. reported cases of confirmed, cured, dead data are accurate.
    3. Patients are not infectious during the incubation period.
    4. there are no super-spreaders.
    5. recovered individual cannot be infected again.
* task 
    * predict number of real case.
* data preprocessing 
    * data of recent 10 and 20 days aresplit as the test set in prediciton, the rest is training
        set
        * sliding window of length 5 is applied, to predict next day.
    * LSTM
        * min-max normaizliation is appleid to be between 0 and 1.
* model
    * LSTM 
        * task
            * the model outputs S,E,I,R at each time step, but the goal is only to predict number of
                infected cases (I)
        * loss function optimize MSE
        * 100 epochs and batch size is 16
        * [[validate]] how are S, E, I, R involving in minimize MSE?
    * SEIR 
        * note
            * number of E(t) isn't equal to number of reported S.
        * task 
            * to predict infection cases.
        * [[validate]] I am not 100 percent sure how the model use objective function. There are 2
            objective functions that were mentioend in the paper. I believe that I need to
            understand how [[trust region refelctive algorithm]] works, because optimization
            formulars suggest to me that one of them is global and another one is local.
            * $$
            \min _{\Theta} \max _{\forall i}\left\{\frac{I\left(t_{i},
            \Theta\right)-\hat{I}\left(t_{i}, \Theta\right)}{I\left(t_{i}, \Theta\right)},
            \frac{R\left(t_{i}, \Theta\right)-\hat{R}\left(t_{i}, \Theta\right)}{R\left(t_{i},
            \Theta\right)}\right\}
            $$
                * parameters (\theta)
                    * E(0) is initial value of the exposed number.
                        * hyper parameter.
                        * it is assigned by random number given a range.
                    * \beta is contact rate
                    * \sigma is incubation rate
                    * \gamma is recovery rate
        * input parameter initialization
            * predicted E_1, predicted S_1, I_1, R_1, \theta_0 are initialized
            * predicted values in the sliding window are calculated based on the initial
                parameters:w
        * trust region reflective algorithm is used to obtain suboptimal parameters \theta.
    * modified SIER
        * separate infection rate into infection rate during incubation period and normal contact
            infection rate
            * [[validate]] [34] shows that 12.6 % of the repoerts indicated that pre-symptomatic tranmission
                existed. 
                * IN the other word, modified SIER doesn't assume 0 percent infection rate during
                    incubation.
        * [[re-written]] though, performance of modified SIER is better than SEIR, the improvement
            is not as significant, hence, the author choose SIER for mSEIR to avoid potential
            overfitting caused by additional parameters.
            * they figure assumption that the incubation period is not infectious will not have muct
                impact on the prediction results.
    * mSEIR
        * consider mobility of urban population and the interactions of the inter-city populatino flow.. 
        * newtork construction 
            * node
                * S, E, I, R represent the population of the subregions n.
            * edges
                * interaction strength is defined as h_nm which may be correlated to the average
                    population flow from n to m.
                * edges are directional as mobility flow is not symmetrics.
        * the modification allos susceptibale crowd in the n-th subregion to be converted to the
            exposed in three portential ways as followed.
            1. The internal propagation in subregion $n: \beta \cdot S_{n} I_{n}$.
            2. The infected people in subregion $m$ with the number of $\frac{h_{m n}}{P_{m}} \cdot
            I_{m}$ come to subregion $n$ with the probability of $\beta$ to spread to the
            susceptible person $S_{n}$.
            3. The susceptible people in subregion $n$ with the number of $\frac{h_{n m}}{P_{n}}
            \cdot S_{n}$ come to subregion $m$, and are infected with a probability of $\beta$ by
            the infected people $I_{m}$.
        * [[re-written]] only country adjacent to region (Hubei Province and Yangtze River
            Delta) is selected for analysis and prediction.
            * [[validate]] population 
        * [[re-written]] I think they assume constant population. I am not sure.

    * evaluation
        * sliding windows of the same size 

# finding
* LSTM performance
    * it is accurate for short-term prediction.
    * it fails to predict the long-term evolution.
    * MAPE value for the prediction of 10 and 20 days are 10.8% and 30% on average, respectively
    * [[re-written]] error increases over time.
* SIER  
    * It is observed that by introducing more parameters, the predicting results may be
    better; thus, it would be easier to cause overfitting.
    * Because the infectious number of patients during the
    incubation period is quite small, the results of both the SEIR and modified SEIR models do not
    have
    much difference
    * using larger window size, the sensitivity of the prediciton becomes weak. 
        * however, smaller window size will result in an overfitting prediction.
    * MAPE of the 21-day prediction is 8.15 percent on average.
* modified SIER
    * as the training data set becomes larger, MAPE values gradualy decrease and then indivate and
        accurate predicting result.
        * [[re-written]] added training data were at timestamp close to the peack of the curve, and
            large error were during begining of the downward slope.
* modified SIER vs SIER
     * At the beginning, the prediction results of the modified SEIR
     model are better than the traditional SEIR model, but the increase of the number of parameters
     is more
     likely to cause overfitting, resulting in poor prediction results sometimes. 
* mSIER
    * by using small window size in the method, we may sensitiely acquire the infelction point of
        the trend of COVID-19.
# FAQs
* this paper
    * what is the architecture of the experiment?
    * why predict with lstm performance produce bad results? 
    * for mSEIR, does it compute S,E,I,R of connected states simutanously or separately?
* general 
    * how to account for super spreader in network when modeling network?
