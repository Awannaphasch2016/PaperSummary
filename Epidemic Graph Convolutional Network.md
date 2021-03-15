# INTRODUCTION
# REFERENCES
# TERMINOLOGY
* Independent Cascade Model (ICM)
* Linear Threshold Model (LTM)
* local sampling
    * diffusion rate depends on neighbor nodes
* global sampling
    * [[re-written]] all connected nodes (nodes in a graph's component) must have non-zero global measure value.
# RELATED WORK
* Graph Nodes sampling
    * local sampling
        * local smapling is to pick s neighbors uniformly 
        * [22] first proposed.
            * fixed number of nodes are sampled from the directed neighbors of node v_1.
            * the aggregation process is performed over the sampled neighboring nodes insteead of all nodes neighbors.
    * global sampling 
        * [9] was the first to proposed.
            * set of nodes is sampled saccpording to some global imporatnce measure. 
                * [[re-written]] all connected nodes (nodes in a graph's component) must have non-zero global measure value.
            * nodes that nodes are still aggregating from its directed neightbors, but only those neighbors that have been globally smpled. 
* epimeic and diffusion modeling
    * epidemic model
        * SIS (paper only focus on this)
        * SIR
        * SIRS
    * diffusion process
        * Linear Threshold Model (LTM)
            * the process of becoming activated requires that a given percentage of a nodes neighbors are also currently activated.
            * Given an initial set of active nodes and a thrshdole (either globally or per node) the process of LTM is similarty to ICM but instread requires nodes to only activate when enough of their neighbors are activated
        * Independent Cascade Model (ICM)
            * the following process continue until no more atication are possible
                * In ICM, when a node become active, it is given a chance to activate its inactive nighbour in the next step and succeds with a probability whih is independent of the history.
                    * but if it fails, it cannot make any future attempts to activate it's neighbors.
# KEY CONTRIBUTION
* we fuse local and global nodes sampling from difussion modeling and epidemic modeling.
    * we hardness this understanding to fuse together the benefits of smpling from both a local and global while alleviating some of the inherent issues found in both through th euse of ta low-dimensional approximation for the path based Katz simialrity measure. 
* Propose the use of both local and global smapling methods together in a principled appraoch that utilized a low dimensional approximation of Katz simialrity measure to overcoem some of the challenges associated in each method
* we anlayze relation between current GCN samplign methdos to that of classificcal epidemic and diffusion models
    * we then harness this knowledge towards constructing our proposed Epidemic Graph conolution Network (EGCN) framwork
# HOW AUTHOR COME UP WITH THIS IDEA
# FURTHER READING
# FUTURE DIRECTION
* we also note that for some grpahs such as social networks, if given information cascades ( eg. retweets pathways on Twitter) , we could use that information in addition to structural nodes similarity, but we leave this as one future work.
# CHALLENGES
* node sampleing from graph 
    * local sampling
        * eg 
            * GraphSage, ICM
        * local sampling methods are still open to potential imporvements, 
            * desiring a principled distrubtion to sample nodes from their local neighborhood.
                * this could  potentially allows the avoiance the challenges of using a cloa lsampling such as 
                    * eg 
                        * acoiding noisy connections
                        * reduce the number of needed samples (ie. smallers)
                        * having a more informed aggreation beyond assumign all neibhors are equal.
        * required to sampled from a large set of nodes
            * this results in a n exponenetial expandsion of the nodes that are required to aggregated from in term of s (whcih is not necessarily the samei n all layers) 
            * sampling uniformly  at random is susceptible to both noisy connections and any potential adversarial links
                * which has recently become a popular topics of interest in the GCN domain [3,12, 41,48,49]
        * ICM 
            * it is more likley that nodes are becoming activated in real network diffuciosn cascasdes from more similar enighbors as compared to unifromly at random.
            * in ICM, noisy link that do not interect much will results, in a probability between them being very low (even approaching zero)
    * global sampling
        * eg 
            * FASTGCN
        * the premise of this model is to independntly performance a global smapling for each layer of the GCN.
            * potential drawback of this methodology of sampling sit taht winin larger networks problems could arise since inherently many nodes in a minibatch might not connect to a gvien sleected subset of global importnat nodes.
                * in real-word graph, many nodes not connected to globally important nodes, this methods should result in biased training process.

# STANDARD AND BASELINE
# METHODOLOGY
* task
    * nodes calssification
* Graph node sampling 
    * categorization
        * local sampling
            * ICM
        * global sampling
            * SIS
                * diffusion rate is fixed to certain recovery rate and infect rate.
            * FastGCN
                * both the infected nodes and globally sampled nodes in FastGCN, are being sampled according to their global imporatce in the network although somewhat differnetly defined.
* architecuture
    * it is desired to not only guarantee possilbe nodes to aggregate from, but further more to have a principled weighed according to the nodes local neihborhood and not only a global measure.
        * best to combined the two together.
    * using node similarity 
        * requirement 
            * it needs to be a global simialrity measure such taht in the global smpalign we can still ahve a non-zero similarity for many nodes
            * it also needs to be both computationally feasible in both terms of time and space.
        * katz similarity measure is selected for this paper but other node similarity algorithm can be used if it satisfy the requirement 
        * the similarity, wil lbe used to performa weighed averaging over the nieghbor of a node.
        * local sampling
            * select top neghbor by ranking with node simialrity value.
        * global sampling
            * we ustilize the similarity to resolve the issue of having nodes in the minibatch either not having many connections to the globally imporatn set of nodes, or lacking many  conenctions.
                * we can utilize the simialrity to performa a full aggration over all the sample globl nodes accrding to a weighteaverage basedo nthe nodes imility to each of the sample nodes (even if a direct lin kbetween them doesn not exist).
            * for computational efficiency we restrict the search for the top-s most similar nodes to be among the first order neighborhood of the targnode.
                * however, for global sampling, we need to coputer the simialrity from each nodes in our minibatch to the nodes tha are globally sampled.
                    * since, they wil lbe dynamically changing during the trianging (ulike the local fixed smapled set)
            * implementation
                * cache can be used to further improve the efficiency by not having tto recompute similarity socored by computign the ismialrity from each nodes to sa smalle number  of globally imporatnt nodes ( as they are the ones more likely to be sampled)
# RESULT
* compared to GraphSage
    * base on our findings we can observe that our local sampling niehhborhood  is smaller thatn that of GraphSAGE, but yet we are still able to oiutperform
        * this implies that hte use of a fixed top-k neighbors accridng to similarities (while also performing a weighted average) helps EGCN to imporve performance.
* comapred to FastGCN
    * on the larger dataset, we observe that this is wehre we find the largest imrpovement
        * which is likely due ot the glboal smapling challenges we ahd discused regarding appling global sampling on larger network
* base on Figure 5, both the local and glboal sampling/aggregation are meansing ful and that togethe they achieve the best performanec 
    * [[re-written]] values of trade off is between 0 and 1 which implies that it takes advatage of both local and global simialrity
# FREQUENCY ASK QUESTION 
