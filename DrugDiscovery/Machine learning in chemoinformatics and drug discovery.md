# Tags
drug-repurposing/ GNN/ network/ survey/ [[In Progress]]

# URL
# note to self: no smaller detail. only big picture. smaller detail should be
# citation
@article{lo2018machine,
  title={Machine learning in chemoinformatics and drug discovery},
  author={Lo, Yu-Chen and Rensi, Stefano E and Torng, Wen and Altman, Russ B},
  journal={Drug discovery today},
  volume={23},
  number={8},
  pages={1538--1546},
  year={2018},
  publisher={Elsevier}
}

# introduction
* One of the primaryapplication areas for machine learning in drug discovery is helpingresearchers understand and exploit relationships between chemi-cal structures and their biological activities or SAR [2]. For instance,given a hit compound from a drug screening campaign, we mightwish to know how its chemical structure can be optimized toimprove its binding affinity, biological responses or physiochem-ical properties
* application 
    * QSAR (quantitativecularFingerprinte structure-property relationship) and QSRP
        *  develop artificial intelligence programs that accurately predictin silico how chemical modifications might influence biologicalbehavior [3]
        * given known compund properties, the chemical features can be used to train machine learning models
    * toxicity
    * metabolism
    * carcinogenesis


# Standards and baseline
# related work
# future direction
# challenges
# terminology
* structure-activity relationship (SAR)

# dataset
# methodology

* ![chemoinformation analysis using machine learning](https://cdn.mathpix.com/snip/images/7cn92zxGc4vM5lo5sY03Tx-q3nNVFaK7n25V29CGnBA.original.fullsize.png)

* chemical graph theory
    * chemical graph 
        * [10] purposed serveral variations of chemical graphs
        * represents atomic connectivity using a vond adjacency matrix or topological distance matrix which support the computation of several topological indices useful for chemiinformations modeling [12]
    * chemical pseudographs or reduced graph 
        * it use multiple edges and self-loops to capture dtailed bond valence information.
    * application
    * method
        *  they proposed an equa-tion that combined pseudograph vertex degree derived from theadjacency matrix with two key parameters from the completegraph to model the electronegativity of 30 elements from themain group of the periodic table [10]
        * More recently, Fourchesand Tropsha developed the advanced dataset graph analysis(ADDAGRA) approach. In this work, they combined multiplegraph indices from bond connectivity matrices to compare andquantify chemical diversity for large compound sets using chemi-cal space networks in high-dimensional space. The study showedthat the ADDAGRA approach could uncover shared chemicalspace between chemical databases to improve SAR analysis [13].

# finding
# FAQs
* this paper
    * what are models that applied on graph data?
* general
    * how many types of drug discovery are there?
    * how many types of drug screening are there? 
