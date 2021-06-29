# note to self: no smaller detail. only big picture. smaller detail should be
* this is a example of dialy-based contact network. (Mezzo network)s)
# citation
@article{mallory2021influenza,
  title={Influenza spread on context-specific networks lifted from interaction-based diary data},
  author={Mallory, Kristina and Rubin Abrams, Joshua and Schwartz, Anne and Ciocanel, Maria-Veronica and Volkening, Alexandria and Sandstede, Bj{\"o}rn},
  journal={Royal Society open science},
  volume={8},
  number={1},
  pages={191876},
  year={2021},
  publisher={The Royal Society}
}
# introduction
* the papers categorized models into the following
    * idealized model
    * data-driven model
        * network strcutre in homw, work, and social settings is intrinsically different.
            * note
                * this extended network (combining different networks) do not  preserve many
                    context-specific features.
            * home are small, fully clustered and distrint;
            * work networks are made up of establishments of various size that sparely connect household 
            * social networks are highly connected and, as such, serve to bridge between more isolated homes
                and workplace.

* we presents a context-specific modelling approach for  generating artifical networks that maintain
    some of the kye feautres of the interactions recorded in a diary-bad survye. 

# Key contribution 
* addressing some of the challenges associated with the limited and incomplete natures 
    * 
# standard 
# dataset
* [10] Warwick data
    * 
    The Warwick survey data is a a record of the person-to-person interactions of 49 volunteer
    participants over the course of 14 non-consecutive days. The volunteers, consisting of students and
    a record of the person-to-person interactions of 49 volunteer
    conversational
    interactions on the specified days. These encounters were categorized based on proximity (casual or
    skin-skin) and context (home, social, work/school, shop, travel or other). The resulting record
    contains a total of 8661 encounters among 3529 people, made up of the survey participants and the
    other individuals they interacted with. Following the terminology in [10], we will refer to the
    survey
    participants as egos and the secondary individuals they encountered as alters

# Future Read

* We note that we do not expect to recreate the double-peak curves observed in some of the seasons
    represented in figure 8, since the dynamic responses in our model are not influenced by factors
    such
    as cognition of epidemic spread (as in [11]).
    * [11] use heterogenoeous graph modeling appraoch to describe flue virus tranmission in a
        population of hospital patient and an agent-based model incorrating many unknown paramters. 

# related work
* analytica and computation for idealized networks 
    * [1,2,4,5]
* accurate nteworks of social encoutners by making use of real-word data
    * [6-11]
    * various types of real worlds data ahve been used
        * [6-9] focus on traits fo individuals.
            * note
                * lots of information about nodes, but no informationa bou tedges.
            * Yang et al.[6]
                * census data,
                * travel log
                    * for personal charactertistics
                * daily activity patterns to individual.
            * Bian et al [7]
            * [8-9]
        * tracking daily interactions of individuals
            * note
                * rich edges informaation may remove hte need to make assumptiosn that all
                    indivdiuals interact wheneve rthey are in the samepl ace and time  as in [6-9] 
            * [10]
# future direction
* [[re-written]] study on larger network + study differnet socail interacetiosn. (edges?)
    * in the future, it will be interesting to sutdy disesea spread on large nteworks and future test
        hwo social inteeractions in differnet contexts affect epidemic dynamics.
* incorporate more realistic dynamic resposnese to disease onset into the current model framwork.
* explore the effects of seasonality on disease dyanmcis in differnet ineteratciont context in our
    networks.
# challenges
* dialy-based study 
    * due to error prone data collection methods, it is important to understnad how daily-based data
        can be extended and completed to produce larger networks that preserved the esstial social
        structure present in the data 

* the paper use small survey that was collected in a specific location and setting.
    * 3000 individuals.

* limitation of the purposed methods.
    * it cannot recover the double-peak epidemic size sdisplayed in serveral flu seasons.
        * [[re-written]] study of larger epidemic size may satisfy the double peak
            * the author mention that it would required knowledge of how the dynamic response to the
                disease varies with time and epidemic size. [11]

# terminology
# methodology
* network construction
    * howe network construction
        * assumption
            * individuals interact with all memebers of their shared household.
        * edges weight = frequency value of each household.
        * algorithms 
            1. Sample from the home degree distribution of the Warwick data to obtain a target degree n.
            2. Generate a clique of size n + 1.
            3. Assign an interaction weight to each edge in the home unit by sampling from the appropriate home
            frequency distribution of the Warwick data: the distribution for n ≤ 8 or for n > 8.
            4. Add the new home unit to the existing network and repeat from Step 1 until 3000 nodes are
            generated. (We adjust the size of the final home unit added to reach the desired number of nodes
            in the network.)
    * social network constuction
        * we seek to capture this more connected, less clsutered character in our extended social
            sub-networks.
        * generate our social sub-network in three steps
            * contruct social units of 38 nodes each.
            * each social unit, we assign the nodes a degree from 0 to 36 in a uniform manner.
            * randomly select popular nodes and connect them to high-degree individuals in other
                social units. 
            * shuffle some connections between nodes to bring the average local clustering
                coeffcient down to value reported in [17,18] in anology to small world model (19)
    * work/school netowkr constuction
        * property
            * long right tials
                * characteristic of power-law distribution and often captured using network-growth
                    models involving preferencial attachment [20,21]
        * We build our extended work/school sub-network using preferential attachment motivated by the
        structure of the work environment itsel
        * warwick data aonly concerns a single work unit, namely the University of Warwick.
        * we do not direcly used degree distribution from  warwick data to detemrien the size of our
            work units because it is university not work unit.
            * degree distribution is extracted from data on business size in Conventry, UK.
* by removing the edges in one or moere of these usb networks, we acn study how their diffeernet
    featurse imapct diseas speading.  

# finding 

* the papers finds similar characteristic  
    * disease spreads most frequently at work but remains localized unless other interactions are present
    (§4.2);
    * social interactions are responsible for the wider spreading of an epidemic (§4.2);
    * dynamic responses to infection can substantially reduce epidemic size (§4.3);
    *  individuals with influenza are most likely to reduce their work and social interactions (§4.4);
    and
    * staying home from work or school has the strongest impact on reducing the severity of an influenza
    outbreak (§4.4).

* Interactions at work have the highest contribution to disease spread until the final days:
* Excluding social interactions has the highest impact on disease transmission:
* Considerably reducing interactions at work leads to a smaller epidemic size and duration of
    infection:
    * interactions from selected context is removed after infection.

* Reducing social and work interactions yields epidemic dynamics on similar scales with flu season
    data
    * including large changes in the patterns of work interactions lead s to a good predifion of the
        start of the peidmiecs during the 2016-2017, and 2018-2019 season, both characterized by low
        to moderate flu activity.
        * Our model therefore
        suggests that strategies involving reductions in work interactions after flu onset may have
        the largest
        impact in avoiding severe influenza seasons.
        * Our results also indicate that, as expected,
        individuals are
        likely to change their social and work interactions shortly after they contract the flu

* We note that we do not expect to recreate the double-peak curves observed in some of the seasons
    represented in figure 8, since the dynamic responses in our model are not influenced by factors
    such
    as cognition of epidemic spread (as in [11]).
    * [11] use heterogenoeous graph modeling appraoch to describe flue virus tranmission in a
        population of hospital patient and an agent-based model incorrating many unknown paramters. 

* Although our minimal SIR modelling approach
does not reproduce all of the features of realistic epidemic dynamics in figure 8 (such as double
peaks
or onset of the epidemics), our simulations are similar to real influenza epidemics in terms of
outbreak size and duration

* the models apply on bacterial meningitis (short-term immunity)
    * dynamic evolution compares well to meningitis outbreak data from the WHO. [31]

* result from shopping and travel (weekend behavior) context are not included in the main study
    because, including it produce almost identical to the full network resutls. 
    * a small percentage of interactions in the Warwic data [10] is in context of shopping and travel.
        * it is sampled from the travel and shop degree distributions.
        * it is constructed as all-to-all coupling of nodes in cluster
            * based on the idea tha tgroups of
                individuals travlelling or hsoppign together are small and fully clustered.

# model
# FAQs
* how is network constructed?
    * different social context 
        * home network etc.
* what are impacts of the purposed method (use of social context)?
    * see finding sections. 
* how to control spread given the network?
