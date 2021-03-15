:knowledge distillation:deep learning:transfer learning:
:covid19:pandemic:
# INTRODUCTION
* CDC has FluSight challenges. Its goal is to predict weighetd wILI thoughout the flu season in the United States.
    * COVID-19 will effect counts numbers of wILI in the future.
* the atypical nature of current (2020) 'COVID-ILI' season may be caused by multiple co-occurring phenomena. including
    * actual COVID-19 infections
    * shutdowns
    * societal lock-downs
    * changes in the healthcare seeking behaviors
# SUMAMRY
* the work is geared towards adapting a historical model to an emrgin disease scenario. 
   The work also train spatial temporal on all states at once insteaead of training model for each states separately.
# REFERENCES
# RELATED WORK
* flu forecasting
    * [Adhikari et al.2019), use statistial appraoches and trained on historical wILI data
* Epidemic Forecasting 
    * statistical approach 
        * Tizzoni et al. 2012; Adhikari et al. 2019; Osthus et al. 2019; Brooks et al. 2018
    * mechanistic approach
        * Shaman and Karspeck 2012; Zhang et al. 2017
    * ensemble approach 
        * Reich et al. 2019b
    * rely on extermal signals including
        * environmental conditions and weather reports
            * Shaman, Goldstein, and Lipsitch 2010; Tamerius et al. 2013; Volkova et al. 2017
        * social media 
            * Chen et al. 2016; Lee, Agrawal, and Choudhary 2013
        * search engine data 
            * Ginsberg et al. 2009; Yuan et al. 2013
        * combination of multiple source
            * Chakraborty et al. 2014
    * deep learning appraoch
        * (Adhikari et al. 2019; Wang, Chen, and Marathe 2019; Rodriguez et al.2020
    * model specific for situati
* Time Series Analysis 
* Transfer learning within heterogeneous domain 
# KEY CONTRIBUTION
* CALI-NET
    * the model i trained on all regions at once 
        * previous approaches have moduled each region separately.
    * transfer learning architecture which allows us to 'steer' a historical disease forecasting model to new scenarios where flu and COVID co-exist.
    * our framework enables this adaptation by automatically leanring when it shoudl emphasize learning from COVID-related signals and when it 
     should learned from historical model.
    * we embed calinetw with a rnn including domain-informed spatial constraints to capture the spatiotemporal dynamic across different wILI regions
    * we employ a knowledge distillation scheme to explicitly transfer historical WILIk knowledge to our target model in CALI-NET
        * this alleviating the effect of paucity of COVID-ILI data
# FURTHER READING
* transfer learning within heterogenous domains.
    * (Moon and Carbonell 2017)
        * proposed to learn feature mapping in a common-subspace.
    * Li et al 2019
        * proposed transfer learning bia deep lmatrix completion
    * Yan et at 2018
        * formulated this problem as an optimal transport problem using the entropic Gromov-Wasserstein discrepancy.
* Knowledge Distillation (KD).
    * 
# FUTURE DIRECTION
* Unlink our paper, most KD work has been appied to classification, efforts for adapting KD for regression have been sprse.
# CHALLENGES
# TERMINOLOGY
* inflenza like illness (ILI)
* knowledge distiallation scheme
    * [[validate]] what is it
* effect of paucity
    * [[validate]] what is it?
# STANDARD AND BASELINE
# METHODOLOGY
* task
    * wILI forecasting
* features 
    * using various signal
        * COVID line list data
        * test availablity.
        * crowd-sourced symptomatic data
        * social media
# RESULT
# FREQUENCY ASK QUESTION 

