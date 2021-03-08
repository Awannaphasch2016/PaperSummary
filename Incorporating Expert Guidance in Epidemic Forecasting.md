# INTRODUCTION
# FURTHER READING 
* expert guidance
    * [17]
* read the following model (I need to find paper for each paper) that compete in CDC FluSight prediction challenges
    * note
        * I selected the following because they perform among the best.
    * CU2
    * KBSI1
    * UMN

# REFERENCES
* github
    * code is provided.
# RELATED WORK
* machanistic 
    * note
        * machanistic apparoaches preidct influenza b urden using simulation and aggregation of large epidemiological models
        * these model required a lot of calibration and hence are limited by their parameters to generalize well and fit the data [20]
        * as human mobility is high, flu activity rapidly increases in the following weeks. 
            * this cannot be modeled using standard mechanistic epidemiological model [21]
    * [24,34]
* statistical approaches 
    * note
        * statistical approaches 'over-correct' and exaggerate the termporary 'dip'
    * [1,5]
* guided prediction framework
    * The Seldonian optimization frame-work [27] discussed earlier presents general framework for expert guided prediction framework
    * based on  Seldonian framwork, Meteview et al [19] proposed Robinhood, an algorithm for faireness in a bandit setting.
# KEY CONTRIBUTION
* incorporating expert guidance helps our approach outperform the baselines while maintaining accuracy.
    * 'Guided EpiDeep' is the only method to show desireable behavior while also getting the lowest error.
* our contributions are as follows
    * Novel methods for incorporating expert guidance.
        * We explore a novel problem & adapt a successful framwork to obtain domain-based consistency ( and guidance), and performance 
            extensive experiments to show properties of the framwork 
    * Flexible user interaction framework
        * the framework adapts to the user's requirements.
# HOW AUTHOR COME UP WITH THIS IDEA
* as human mobility is high, flu activity rapidly increases in the following weeks. 
    * this cannot be modeled using standard mechanistic epidemiological model [21]
* statistical approaches 'over-correct' and exaggerate the termporary 'dip'
* the 'smoothness' of the forecasts is well-motivated from the epidemiological consideration s as well. 
* epidemiological expert's domain knowledge can be brought to bear upon influenza forecasting.
* goal of the paper 
    * note
        * none of the existing apporahces is able to tackle these challenges.
    * how to design a general framework for any influenza statistical forecasting model to ingest and leverage expert guidance.
        * designing a general frame work to incorporate guidance allows existing approaches to include expert guidance.
    * hwo to ensure that the framework is easy to use and generates useful feedback to the user?
* some auxiliary knowledge that expert knowledge can help.
    * it is well known that the christmas holiday season in the US has specific impact on the flue spread 
        * which cannot be captured by regular-mechanistic epidemiological models [21]
        * an expert notices that predictions of current statistical models are not 'smooth'
            * i.e. they change alot week-week and over-correct during this time 
            * hence, s/he may want to more accurately forecast influenza incidence during the Holiday season incorporating the smoothness property.
* feedback loop interation between expert and model provided opens possibilities to fruitful interactions as the expert may explore with different beahviors and tolerances to find the most suitable ,and even test 'what-if' scenarios
* mechanistic epidemiological models reveal the following
    * the epidemiological curves tend to be smooth with a single peak [25]
        * hence, we expect epidemic influenza season to be genearlly smooth.
    * usually, incidence are low in the beginning of th eseason, they gradually rise till the peak is observed and then decline near monotoically..
    * smoothness also helps in orrecting the drop obersrved in the influenza activity during the holiday season. 
        * which arises due ot the artifact of data collection
# FUTURE DIRECTION
# CHALLENGES
* surveillance data collected (using ILINet) has the following properties
    * composite of multiple sources
    * is non-uniform
    * and is biased in many domain specific ways.
* challenges are as followed
    * how to design a general framework for any influenza statistical forecasting model to ingest and leverage expert guidance.
        * designing a general frame work to incorporate guidance allows existing approaches to include expert guidance.
    * hwo to ensure that the framework is easy to use and generates useful feedback to the user?
# TERMINOLOGY
* chrismas effect
* math
    * Seldonian optimization framework [27]
# STANDARD AND BASELINE
* data 
    * the CDC releases influenza surveillance data
        * referred to as weighted influenza-like illness (wILI), each week for every region.
* model
    * EpiDeep [1] as the base-model upon which the guidance is to be enforced. 
# METHODOLOGY
* task 
    * CDC FluSight challenges
* architecture
    * following [27], we ensure that our approaach optimizes the objective while not violating the constraints and it generlaizes 
        to other unseen data with high confidence.
    * requirment
        * model properties
            * P1. promote one or more desirable behaviors during trianing 
            * P2. Have a mechanism to guarantee tolerance on deployment
            * P3. Be flexible to any generic ad-hoc guidance and be compatible with state of the art epidemic forecasitng models
            * P4. provide feedback to users if guidance could not be incorporated.
        * preidctions are smooth is a desirable property
        * to ensure that region with poor surveillance systme do not suffer more financial/health burden regional equaity in the quality of forecast is required.
    * model
        * EpiDeep [1] as the base-model upon which the guidance is to be enforced. 
    * loss function 
        * see paper
    * expert guidance types 
        * Direct guidance
        * automatic guidance
    * experiment intereaction 
        * our framework provides three knobs
            * data 
            * model
            * tolerance.
                * usecase 
                    * the expert can interact with the system by varyin gthe vlaues correspoinding to the knobs
                    * if the model retuns NDF, it is an indication for the user to either ocnsdier the guidance provided or to vary the knobs.
                    * an expert can also change data by deciding to exclude some historical seasons that are prepventing the guidance provided from bing.
# RESULT
# FREQUENCY ASK QUESTION 
* is there a way to measure quality of surviellance data?
