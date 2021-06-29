# Tags
drug-repurposing/ GNN/ network/

# URL

# note to self: no smaller detail. only big picture. smaller detail should be

* the only thing I can write here is that the paper provided evident that GNN perform well on drug discovery set.

# citation

@inproceedings{cheung2020graph,
  title={Graph Neural Networks for COVID-19 Drug Discovery},
  author={Cheung, Mark and Moura, Jos{\'e} MF},
  booktitle={2020 IEEE International Conference on Big Data (Big Data)},
  pages={5646--5648},
  year={2020},
  organization={IEEE}
}

# introduction
* Recently,
research has found that using graph neural network (GNN)
models, given enough data, can perform better than using humanengineered fingerprints or descriptors in predicting molecular
properties of potential antibiotics.

* The scientific community has united to combat the growing
COVID-19 pandemic. At the time of writing, there are more
than 200 vaccines in development, 12 have begun large-scale
(phase 3) clinical trials, and 2 have shown to be 95% effective
(Pfizer and Moderna) [1]

* Given the urgency of the situation,
vaccine development and approval has been accelerated from
the general timeline of 10-15 years [2]
    *  Part of this acceleration is made possible due to the
    development of artificial intelligence (AI).

* step of drug discovery 
    * The first stage of this process is drug discovery, whereby scientists typically spend 2-5 years to identify vaccine candidates
    [2].
        *  Instead of testing most drugs in vitro in the lab, scientists
        are able to leverage computational methods to screen potential
        drugs in silico, saving a lot of time and physical resources, as there are over 1 millions compounds to test

# Standards and baseline 
* models
    * We have set
    the baseline to be edge-based message passing and tried
    using atom-based message passing, adding extra features
    (RDKit-2D), undirected message passing, and for the smaller
    dataset, optimized over all hyperparameters.
# related work

* drugs discovery ( graph classification)
    * Graph neural networks (GNNs) have shown promising
    results for drug discovery applications [7], [8].
* Drug-target interaction (DTI) framework
    * Drug-target interaction (DTI) is one of the most important
    steps in the drug discovery stage
        * . It characterizes the binding
        of chemical compounds to the protein targets.
    * Drug
    screening identifies ligand molecules that can bind to specific
    proteins, whereas drug repurposing finds new therapeutic uses
    of existing and available drugs.
       *  

* predicting desirable molecular properties for drugs.
* More recently, it is shown that using deep learning, given
enough data, can result in superior performance for antibiotic
drug discovery [3]. For extensive reviews of AI applied to drug
discovery, see [4], [5].

# future direction

# challenges

# terminology

# dataset

# methodology
* topology adaptive graph convolution network (TAGCN)
    * use the polynomail filter coefficients  
    * update with GRU


# finding
* MPNN is better than TAGCN 
    * not sure why they include TAGCN in the report as well.

# FAQs

# content
