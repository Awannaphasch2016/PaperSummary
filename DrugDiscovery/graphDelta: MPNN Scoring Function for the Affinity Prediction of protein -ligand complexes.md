# Tags
MPNN/ graph/ binding-affinity/ graphDelta/ 
# citation
@article{karlov2020graphdelta,
  title={graphDelta: MPNN scoring function for the affinity prediction of protein--ligand complexes},
  author={Karlov, Dmitry S and Sosnin, Sergey and Fedorov, Maxim V and Popov, Petr},
  journal={ACS omega},
  volume={5},
  number={10},
  pages={5150--5159},
  year={2020},
  publisher={ACS Publications}
}
# introduction
# related work
* One of the graph convolutional
architectures (PotentialNet42) was trained on PDBBind 200743
and applied to the affinity prediction problem
    * use gated graph neural network architectured
        * utilized RNN for the update stage
    * PotentialNet can perform graph convolution operations for both covalent and non-covalent interactions
# standard 
* dataset
    * data from PDBbind
        * 16151 protein-ligand eomplexes derived from Protein Data Bank (PDB)
        * binding data  include
            * dissociation (K_d)
            * inhibition (K_i) constants
            * half maximal inhibitory concentration (IC_50) 
* validation
    * performance comparison
        * rmse
        * pearson correlation cofficient (r) 
        * Spearman rank correlation coefficient

# challenges
* readinf of some sdf files in database yeidls an error by rdkit
    * the most common issue is the lack of positive charge on tertiary amine nitrogen atoms.
        * it is manaully fixed using MarvinSketch 18.10.

# methods 
* task
    * design of the scoring fucntion with a possiblity to predict binding free energy for a diverse set of chemical compounds and protein targets based on subclass of graph CNN - MPNN
    * framing as a multi-task learning problem.
* preprocess
    * [[pause]] data preprocessing 
        * A smaller “refined” set (4463 complexes)
        was compiled based on the following rules: the structure
        resolution less than 2.5 Å, an R-factor less than 0.25, ligand
        should be bound noncovalently and without steric clashes (any
        distance between pairs of ligand−protein atoms is more than
        2.0 Å), pK is inside the range from 2 to 12, and complexes
        labeled only by IC50 are eliminated
    * graph construction  
        * chemical structure are naturally represented as undirected graphs
        * node  
            * atom 
            * node feature 
                * descriptor vector is used to represent atom
                    * note
                        * The good representation of an
                        atomic environment should be invariant to the permutation,
                        rotational, reflection, and translation symmetries.
                        * It is natural to prioritize local environment defining a cut-off
                        function fc(rij) (eq 2)
                        56 which smoothly decreases the weights
                        of atoms outside the proximal environment and assigns the
                        zero weight for atoms outside the cut-off distance.
                    * see table 2 in supporting information for parameters set used to computer descriptors.
                        * all possible combination of parmaete yeilded 52 descriptors of the atomic environment
                        * BPS computed for each atom type
                        of the protein environment leads to 364 environmental
                        descriptors and combined with one-hot encoded ligand atom
                        type gives 373 descriptors calculated for each atom of the
                        ligand molecule. 
                    * BPS node descriptor vector 
                        * calculated to represent the atomic environment
                            * The choice of the descriptor set which
                            reflects the atomic environment in the relevant manner was
                            influenced by a success of electron energy approximation by
                            neural network potentials
        * edges
            * bonds
* gnn 
    * readout 
        * fuzzy histrogram approach is chosen.  Kearnes et el. 41. to capture the distribution of each L features.
             node permutation invariant appraoch is the simplies way to achieve is to summarized all hidden states vectors reducing N (number of nodes )vectors of length L (number of resulting features) to one vector of length L, but it is not chosen because this pparach leads to the significant information loss.
    * choice of message, update, and readout hyperparameter were inspired by Battaglia et al 58


# FAQs
* this paper
    * what is fuzzy histogram ?
    * how is descriptor computed??
    * dataset
* general
    * what is covalent and non-covalent bond
    * are there any relationship between protein folding and bidning affinity?
