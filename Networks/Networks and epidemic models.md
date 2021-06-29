# tags

# note to self: no smaller detail. only big picture. smaller detail should be

# citation 
@article{keeling2005networks,
  title={Networks and epidemic models},
  author={Keeling, Matt J and Eames, Ken TD},
  journal={Journal of the Royal Society Interface},
  volume={2},
  number={4},
  pages={295--307},
  year={2005},
  publisher={The Royal Society London}
} 

# introduction

* in addition, many
methods of control, such as contact tracing or ring
vaccination, can only be accurately captured and
modelled using network-based approaches

 * the emergence of network modelling tools allows these more
 sophisticated interventions to be studied and enables
 different strategies to be tested in an artificial
 environment.

 * the work using idealized networks and pairwise
 approximations has highlighted many of the differences
 between standard random-mixing disease models and
 disease spread through networks.
     *  the utilmate goal is a set of robust network statistics that allows us to predict epidemic
         dynamics when the population structure deviates from the rnadom-mixing ideal.

* social sciences and graph theory genreally considers an understading of the disease in which case
    the network forms a constraining backgground to the tranmissiong dynamics

* disease spread of the risk of an epidemic of a given mixing network are studied in percolation theory.
    * percolation theory describes the behavior of a network when nodes or links are removed.
        * types of percolation form
            * bond percolation
            * site percolation.
        * this area of mathematics examines
        the formation of connected structures within networks.
        * the size of connectd clusters that emerge in percoluation models related to the expected
            size of an epidmeic within the network.
        * percolation models do not provide a dynamic
         description of the epidemic process
        * the concepts
        underlying percolation theory are immediately relevant
        to epidemiology, and many of these ideas and the
        tools for understanding them have been applied in
        epidemiological settings (mollison 1977; grassberger
        1983; newman & watts 1999; newman 2002; warren
        et al. 2002).

# future direction 


* gps technology + phones may allow for accerate tracking of movement of people in real itme. 
    * this would allow us to build full and comprehensive networks for many airborne disease, and
        also to track the changing networks strcuture in sever epidemic where popoulation behaviors
        radically different from the norm such as 
        * influenza pandemic
        * bioterrorist attack

# challenges

* Most of the networks discussed here have been
static—the connections have remained constant over
time
    * this should be a problem 
     Provided that the
     turnover of connections is slow relative to the timescale of the pathogen, the network will
     change little
     during the epidemic phase of infection.
         * some connections are more prone to changes such as
             * sexual partnerships, close social or fimily relationships.

* microsimulation models and partnership models are designed to allow for changes within a networks
    * these fields remain an important challegnes for the future  

* network needs to consider changes of population behavior from certian event such as outbreak.
    * these needs to be consider when designing interventions. 

# terminology
* forest-fire models
    * Forest fire model is any of a number of dynamical systems displaying self-organized criticality
    (SOC).
        * This model is defined as a cellular automaton on a grid with Ld cells. L is the side length of
        the grid and d is its dimension. A cell can be empty, occupied by a tree, or burning.
* high order network 
    * 
# dataset
# methodology
## model
# FAQs
* which network scale is this paper in?
* types of epidemics disease?
    * airborne disease, sex, by blood?

# content 
* we review the basis of epidemiological theory (based on random-mixing models) and
    network theory (based on work from the social sciences and graph theory).

* We then describe
    a variety of methods that allow the mixing network, or an approximation to the network, to be
    ascertained

* we review some of the variety of idealized network types and approximation techniques that have been
utilized to elucidate this link.

* we look to the future to suggest hwo the two fields of newtork theory and epidemiological
    modelling can deliver and improved udnerstanding of disease dynamics adn better public health
    through effective disease control

## standard epidemic theory 

* compartmental models
    * the basic models describe the number of individuals
    (or proportion of the population) that are susceptible to,
    infected with and recovered from a particular disease
    * it neglected many details of the progression of infection such as response between
        individuals.
    * regardless of its simplicity, the simplification has had a long and succesful history.
    * 2 common models 
        * sir and sis 
            * sir model is used for infectious diseases that confer lifelong immunity, such as
                measles or whooping cough. h (kermack & mckendrick 1927; anderson & may
                1992; grenfell 1992; rohani et al. 2000). 
            * the sis model is
            predominantly used for sexually transmitted diseases
            (stds), such as chlamydia or gonorrhoea, where repeat
            infections are common
    * the force of infections for each individual in a community is the same.
        * it assume same transmission rate in subgroiups. 
        * different mixing rates arae expected etween the pupulation subgroups
            * eg
                * children mix more readily among themselves  than with adults
            * however, sbugroups are ignored when it is relatively too small to the whole population. 
                * less accurate.
        * formular
            $\lambda=$ transmission rate
            $x$ effective number of contacts per unit time
            $\times$ proportion of contacts infectious
            $$
            \approx \tau \times \hat{n} \times \frac{i}{n}=\beta \frac{i}{n}
            $$
                * \lambda * number of sysceptible represent the trainsmission of infection.
        * many biologically motivated modifications have
        been made to this basic framework, usually involving
        the inclusion of more heterogeneities by further
        subdividing the s, i and r classification to reflect either
            * more complex pathogen biology
            * greater structure within the host population.
        * metrix \beta is transition rate metrix of a population can be adjusted to account mixed
            rates between pair of subgroups.
    * models that incorporate network structure avoid the random-mixing assumption by assigning
        permanents contact linking pair of subgroups.
        * however, trainsition rates are often shared between nodes within subgroups.
    * network based compartmental model vs traditional compartmental model
        * network based assume fixed set contacts between individuals while random mixing is
            equvalent of edges continuously changing.

## standard network theory
* social science concerned with the reason behind the network connection rather than the properties
    of the networks structure itself. 
* network analysis has been used as an explanatory tool to describe the evolution and spread of
    ideas and innovations in societies, and observed social dynamics can often be understood through
    analysis of the social networks.. 
    * things that network analysis are often used to analyze
        * social cohension.
        * importance of individuals
            * important properties 
                * degree
                * number of path between points
            * connection made by these individuals have high social impact.
                * closely link to their role in disease spread .
* mathamatical tools 
    * adjacency matrix
        * the following useful network quantities can be derived from adjacency matrix
            * averge number of contacts per individual.
            * info of paths within networks
            * info of the amount of transitivity or clustering.
                * this is the ratio of the number of triangles within the
                network to the number of connected triples; the larger
                this number, the greater the clustering.

## Finding REAL networks
* challenes
    * data collection
        * time comsuming and error prone.
        * required personal information, and especially for sexual mixing networks, info may not be
            readily volenteered. 
        * network info
            * information of links are not clear in most case.
                * however, some links can be clearly establish such as STD, but due to social judgement,
                    received information are error prone.
            * strength of edges are not clearly identified. 

* due to challenges regarding data collection, only small networks are featured in studies.
* networks can be largely different from different epidemics. 
    * because of the follwoing reason.
        * different routes
        * some networks requires mixed networks.

### infection tracing

* types of techniques used to gather network informaiton 
    * note
        * given the same networks, different techniques may results in completely different
            networks. 
    * infection tracing
        * In this way, each infected individual is
        linked to one other from whom they caught the
        infection, and additionally, to a variable number of
        others to whom they transmitted the disease, thus
        providing a ‘transmission network’ consisting of all the
        links through which infection spread in a single
        outbreak
        * after SARS, there are more emphasis on determining the source of infeciton for each cases. 
        * link is clearly defined. 
        * pro
            * reveal a infectious patterns from a single outbreak 
        * cons 
            * costly 
        * use case 
            * use in policy making.
            * use as network evaluation 
        * properties 
            * tree like, no loops

### Contact tracing 
    * complete contact tracing
        * only source of infection are traced.
        * example
            * snowball sampling schemes
                * this is used to form epidemic network because it only concerned about the positive
                    or the infected case.
                * non-probability sampling tehcnique in which the samples have traits that are rare
                    to find.
                * sampling tehcnqieu, in which existing subject provide referals to recruits samples
                    reequired for a research study.
        * finding 
            * sexual contact networks show the importance of core groups  (high degree nodes), and
                long-distance ([[validate]]individual who travels alot?) connections in disease transmission.
        * pro
            * didentify all potential transmission contacts from a source individuals, index case.
        * con
            * links are not clearly defined. 
            * required accurate data about personal relationships.
        * usecase
            * use as control tool
                * often in the case of STD where a contact is most esily defined. 
                * to indentify asymptomatic infected individuals who can then be treated or
                    quarantined.
        * properties
            * contain many dead ends consisting of uninfected indidviduals 
                * only partial network are considered becuase only potentially infected case are
                    considered.

### Diary-based studies
    * diary-based studies. 
        * those taking part are shown with open circles.
            * [[validate]] eg. survey?
        * a diary-based studies subjects reecord contacts as (or shortly after) they occur
            * different from snowball sampling tehcnique in that it shifts the work-load from the
                researcher to the subject and allowing a large rnumber of individuslas to be sampled
                in details. 
        * network often results in a large nubmer of unconnected sub-entwroks ,each one representing
            the presonal network of a few indidviduals.
        * usecase
            * sensors can be used instead of self-reporting (survey)
                * eg
                    * A form of diary-based study is currently occurring
                    in the livestock industry in the UK (National Audit
                    Office 2003)
        * cons
            * subjects may not project accurate information because it is not control by
                researchers.
            * constructed networks are less accurat.
        * challenges
            * Although, almost all links can be traced, the lack of unique identifier means that often links from different indidviduals
                cannot be conneced.

## the use of simulated networks 
* network is generated based on rate (susceptible is infected)
* related work  
    * STD network simulation
        * network highlights imporatance of 
    * network of airborne disease outbreak
        * cons 
            * requires the estimation of many params
            * there are no simple way to ascertain the sensitibity of the epidemiological resutls to
                the details of the networks structure. 
                * vulnerable to questions of 'what if' towards certain bias such as culture
                    * idealized networks and analytical tools ahve been developed that can reveal
                        the elements of the network structure that are important determinants fof
                        epidmiec dynamics.
        * pros 
            * its robusts.
                * it allows a direct estimation of the variability between epidemics. 
        * paper 1
            * require
                * required network of social connection.
            * generated by computer simulation to conform observed social characteristice.
            * roles and activility are assigned to agents 
            * it it used to emphasis on tranmission within households and family groups.
        * paper 2
            * 

## idealized neworks
* [[re-written]] idealized networks often are analyzed to explain observed spreading behavior or
    epidemic.
    * once pattern is found to be similar to one of the idealized networks,
        information/methodologies from studies of  idealized networks can be transfered.
        * example
            * short path lengths suggest that the spatial
            spread of disease is likely to be rapid
                * effective
                containment is therefore liable to require drastic
                restrictions on population mixing behaviour.

* each of these idealized networks can be defined the following properties to simplify and making
    explicit the many and complex processes involve the network formation within real population.
    * how individuslas are distributed in space (socially and geographically) 
    * idealized network simplified complex processes involved in the newtork formaiton within real
        populations.

### random network
* motivation 
    * Analytical results derived from the study of
    simple networks can allow us to develop an intuitive
    understanding of the effects of more complex social
    structures on disease spread.

* In random networks, the spatial position of individuals is
irrelevant, and connections are formed at random
(Bolloba´s 1985)

* type 
    * type 1 
        * in most tractable versio nof the rnadom network
            * node degree is fixed.
    * types 2
        * connect 2 nodes with probability p.
        * properties
            * Poisson degree distribution.
            * mean number of contact = probaiblity * ( # population -1)
        * SIR 
            * [[validate]] 
            the epidemic
            dynamics for this particular network are analogous to a
            an SIR epidemic in a randomly mixed population
            (Barbour & Mollison 1990).

* properties
    * lack of clustering
    * short average path length
    * The dynamics of diseases on
    random networks can be studied as a simple branching
    process (Diekmann et al. 1998), from which it is found
    that both the early growth rate of the disease and the
    final epidemic size are reduced when compared with the
    random-mixing model.
        * the reason for growth rate reduction are.
            * note
                * two process are shared by all epidemics on networks (strength may vary)
            * local
                * since node degree is fixed, as more people are infected, each infected nodes have less
                    probaility to infect its neighbors.
            * global
                * as more people are infected there are less number of total susceptible contacts.

### Lattices
* motivation 
    * lattice model spreading pattern resemble infection spread across  sptailly extended lanscape 
    where wave-like progression is common (Mollison 1977; Grenfell et al.
    2001). 
        * these property caused by highly localized nature of transmission
        * inclusion of long-range connections (described as
        ‘sparks’ or ‘lightening strikes’ in forest fire models) can
        lead to colliding waves and a much more rapid spread of
        infection through the system.

* properties
    * localized nature of connection are highly cluster
    * long average path length
        * takes many steps to move between two random selected individuals.
    * In common with all networks, lattice models show a
    reduced initial growth of infection compared with
    random-mixing models, although this effect is much
    stronger than in the random networks because the
    spatial clustering of contacts causes a more rapid
    saturation of the local environment.
    * wave-like spread of infection
        * from an initial seed, infection spreads out in a
            roughly circular manner
    * self-organized criticality
        * a property of dynamical systems that have a critical point as an attractor.
            * Their macroscopic behavior thus displays the spatial or temporal scale-invariance
            characteristic of the critical point of a phase transition, but without the need to tune
            control parameters to a precise value, because the system, effectively, tunes itself as
            it evolves towards criticality.
        * power-law scaling 

* example
    * The dynamics of forest-fire
    models are considered examples of self-organized
    criticality, whereby critical behaviour and power-law
    scalings exist for a wide range of parameter values (Bak
    et al. 1990).
         * In particular, the frequency distributions of
         both epidemic sizes and epidemic durations obey a
         power-law

### small-world networks 
* Disease spread through small-world networks has
received considerable attention from both a theoretical
and more applied context
    * small-world largely resemble actual social network (Milgram 1967; Travers & Milgram 1969).
        * Both clustering of connections and long-range transmission events are likely to
        be significant factors in disease spread; therefore, smallworld networks are an important
        epidemiological
        concept.
        * The high level of clustering
         means that most infection occurs locally, but short path
         lengths mean that epidemic spread through the network is rapid and disease is unlikely to be
         contained
         within small regions of the population (Watts &
         Strogatz 1998).
        * example
            * collaboration networks of scientific authors (Newman
            2001) and the co-star networks of film actors (Watts &
            Strogatz 1998)
            * On a much smaller scale are gene and
            neural networks, which display the high clustering and
            low path lengths associated with the small-world model
            (Watts & Strogatz 1998).

* considering random (highly unstructure) and lattice network (highly strucutre) as 2 extremes,
    small-world networks are inbetween.
    * small-world can be formed by adding a small number of random connections to a lattice.
        * Even with a few
        long-distance links, there are significant changes in
        epidemic behaviour
            * Nevertheless, because these long-range links are rare, the
            transmission of infection remains predominantly localized, so strong saturation effects
            and wave-like
            epidemics are still observed.

* methods
    * Percolation theory has been applied
    to small-world networks to calculate threshold parameter values at which epidemics can take
    place,
        * demonstrating that random long-range connections
        within the network can dramatically increase the
        likelihood of an epidemic (Moore & Newman 2000)

* properties
    * high clustering.
    * low average short path.

### spatial networks
* pros 
    * most flexible
        * it is possible to gneratea wide variate yof networks randing from small-world arrangement
            ot glboally connected random networks.  (Eames & Keeling 2002;
            Read & Keeling 2003; Keeling 2005)
* probability of forming edges between 2 edges are a function of distance
* properties
     * Spatial networks
     generally show a reasonably high degree of heterogeneity, with the degree distribution often
     being approximately Poisson
### Scale-free networks
* it is often the
case that many individuals have a small number of
neighbours, while a few have significantly more
connections

* example
    * This property was initially observed for worldwide Web connections (Albert et al. 1999), but has
     also
     been reported in power grid networks, graphs of actor
     collaborations (Baraba´si & Albert 1999) and networks
     of human sexual contacts (Liljeros et al. 2001).
    * in the SARS epidemic, a significant proportion of
    all infections were caused by super-spreaders (Riley
    et al. 2003).
    * In the preferential attachment model of Baraba´si &
    Albert (1999), the existence of individuals of arbitrarily
    large degree means that there is no level of random
    vaccination that is sufficient to prevent an epidemic
    (Albert et al. 2000; Lloyd & May 2001; Pastor-Satorras &
    Vespignani 2001).
         * In contrast, when there is some
         upper limit imposed on the degree of individuals
         (Rozenfeld et al. 2002), or when a scale-free network
         is generated by nearest neighbour attachment within a
         lattice (Warren et al. 2002), it becomes possible to
         control infection through random vaccination
     * Targeted vaccination in scale-free networks is extremely
     efficient: the dominant role of super-spreaders means
     that the vaccination of only a few of these individuals
     can be sufficient to prevent an epidemic (Albert et al.
     1999; Lloyd & May 2001; Pastor-Satorras & Vespignani
     2001), reinforcing standard public-health guidelines.

* probability of forming edges of a targer node are directly proportional to number of its neighbors.



 * Super-spreaders and core groups play a pivotal
 role in the spread and maintenance of infection.
    * 2 important effects
        * the spreader  have greater risk of infection
        * the spreader have more change of transmit disease to many others.

* Small
worlds, random networks and lattice models display
little variation in neighbourhood sizes, while spatial
networks generally have degree distributions that are
approximately Poisson

### Eponential random garph models 
* properties
    * low clustering
        * since connected individuals are unlikely to
        share a neighbour
    * low path length
    * binomial degree distribution.
    * probability of connection between two nodes is independent of the connection between any other
        pair of distict nodes. 
        * this allows analyze that analyze local node given a global network properties as prior
            knowledge.
            * Techniques such as Markov Chain
            Monte Carlo can then be used to create a range of
            plausible networks that agree with a wide variety of
            information collected on network structures even if the
            complete network is unknown (Handcock & Jones 2004;
            Robins et al. 2004; Snijders 2001)

## Pairwise approximations
* the idealized networks attempt to recreate actual tranmission dynamic of interest, hence, are deisgned
    to focus on certain aspect of the pouplation mixing behaviorus
    while ignoring the rest
    * certain aspect including 
        * low pathlenghts,
        * heterogeneouds degree distribution 
        * etc.
    * some observed networks fall into serveral of the idealized world and scale-free
        characteristics.
    * [[re-written]] Idealized network is a bottom up approach while pairwise is a top-down appraoch.
        * Idealized newtork create a network based on a strong assumption of what network should
            look like to
        * pairwise on the other hands only attemps to observe low-order network while ignoring
            higher-order structure.
  
* pairwise attemps to model the spread of infeciton on generic networks where higher-order structure
    has been ignored. 
    * Rather than modelling a network of interactions in its entirety, pairwise models, as the name
    suggests, examine the various types of connected pairs
    found within a population
    <!-- * how ever, pairwise model can be adapted to allow for clustering -->
* motivation of pairwise approximiation methods are SIS model
    * it is a rewrite of SIS infection terms that focus on pairwise connection between susceptible
        and infected individuals.
* [[re-written]] pairwise approximation consider number of pairs types rather than individuals 
    * within pairwise approximation formulation, the numbers of differnet paris types are included as
        variables rather than approximated in terms of the numbers of individuals.
* parameterization of the pairwise model required knowledge of the distirbutino of pair tpyes in the
    population. 
    * it uses matrix from mean-fields models. 
* pro
    * the methods doesn't care about complete network as long as all pairs are well identified.
    * easier than simulationt to rapid parameterize and analyzes as it allowing some rigorous
        results to be proved.
* properties
    * the methods capture the correalations between neighbouring individuals that emerge in the
        system. 

* [[validate]] localized depletion of sysceptibles that is the main difference betwen random-mixing, netowrk
    models, and pairwise methods include this explicity.
* usecase
    * fade-out and critical community size for childhood infections evolution of pathegoen virulence
    * spread and control of sexually transmitted disease in heterogeeous population.
    * it was used for foot and mouth epidemic in the UK

## EMERGENT NETWORK
* note
    * emergement network should be useful for deep leanring tasks since they combines mroe than 1
        types of relationships.
        * combining between micro and mezzo?

* All of the approaches described thus far have assumed
that there is some structure behind social interactions;
this structure, the mixing network, determines the
relationships that are permitted and the individuals capable of tranmitting infection to each other.

* emergent network is simply new types of networks.
    * partnership models 
        * it has been used to model STD. 
        * capture historical connection + more like randomly mixing models
            * two individuals can potentially interacts, but to imporve predominantly monogamous
                partnerships.
            * it is interested in the field of network because if all parnerships over some times period
                are recorded then a network of historical connections emerges. 
        * partnership models can be used to test network properties that are epidemiologically
            important such as 
            * number of partnerships , concurrent relationships or network position.
        * For instance, in the modelling approach of
         Ghani & Garnett (2000), an individual’s risk of both
         acquiring and transmitting infection was found to
         depend primarily on the number of partners but was
         also strongly affected by partnership concurrency and
         distance from other individuals within the network.
        * different network properties emphasized different things. 
            * network size or degree  
                * determiens the likelihood of an individual acquiring infection.
            * number of path.
                * significant determinants for importance of an indivdidual as a spreader of
                    infection. 

