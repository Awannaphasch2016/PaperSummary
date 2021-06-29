# URL
* actual paper.
    * https://www.pnas.org/content/pnas/118/19/e2025581118.full.pdf 
* supplementary
    *
    https://www.pnas.org/content/pnas/suppl/2021/04/27/2025581118.DCSupplemental/pnas.2025581118.sapp.pdf
# note to self: no smaller detail. only big picture. smaller detail should be
* survey
    * what graph type is it belong to?
        * mini network. 
    * what are th task?
        * covid-19 drug treatment recommendation task (link prediction)

# citation
@article{gysi2021network,
  title={Network medicine framework for identifying drug-repurposing opportunities for COVID-19},
  author={Gysi, Deisy Morselli and Do Valle, {\'I}talo and Zitnik, Marinka and Ameli, Asher and Gan, Xiao and Varol, Onur and Ghiassian, Susan Dina and Patten, JJ and Davey, Robert A and Loscalzo, Joseph and others},
  journal={Proceedings of the National Academy of Sciences},
  volume={118},
  number={19},
  year={2021},
  publisher={National Acad Sciences}
}
# introduction

* drug repuroing algorithm rank drugs based on one of multipel streams of info including
    * note
        * only small subset of top candidate is validated expreimentally, hence the true predictive
            powe of the existing repurosing algorithms remains unknown.
            * To quantify
            and compare their true predictive power, all algorithms must
            make predictions for the same set of candidates, and the experimental validation must
            focus not only on the top candidates,
            as it does now, but on a wider list of drugs chosen independently
            of their predicted rank.
    * molecular profiles (2)
    * chemical structure (3)
    * molecular docking (5)
    * electronic health records (6)
    * pathway analysis (7)
    * genome wide association studies (7) 
    * network perturbation (7-15)
    * AI 
    * Diffusion State Disease 
    * network proximity 


* we implement three network-medicine drug-repurpsoing algortihsm that rely on AI, network
    diffusion, and network proximity to rank 6430 drugs for their expected efficacy agasint
    SARS-Cov-2.
    * we screend 918 drugs allowing us to evealuate the performanceo f the existing drug repurpsoing
        methodologies, and used a consensus algorithm to inceases the accuracy of hte predictions. 
    * we screened in human cells the top-ranked drugs, identifying six drugs that reduced viral
        infection , 4 of which could be repurposed to treat covid-19 

# key contribution 


# future direction
# challenges

* Given the compressed timescales, the de
novo drug development process, which typically lasts a decade or
longer, is not feasible
    * A time-efficient strategy must rely on drug
    repurposing (or repositioning), helping identify among the compounds approved for clinical use
    the few that may also have a
    therapeutic effect in patients with COVID-19

 * the lack of
 reliable repurposing methodologies has resulted in a winnertakes-all pattern, where more than
 one-third of registered clinical trials focus on hydroxychloroquine or chloroquine, siphoning
 away resources from testing a wider range of potentially effective
 drug candidates. 
    * full unbiased screening to approve drugs could identify all possible treatemnts, but its high
        cose, extended tiem line, and exceptionally low success rate.

# terminology
* explanatory subgraphs
    * it is used to summarized where in the data the pipeline seekes "evidence for their
        predictions."
    * it is a small sub-network of the entire network considered by the pipeline that is most
        influential for the prediction and contributes most to the predictive power. 
# dataset

* human interactomes and SARs-CoV-2  and Drug Target
    * note 
        * to create a drug-disease-protiens networks using dataset shown below, Largest Connected
            Components (LLC) of human proteinds that bind to SARS-CoV-2 protieins was calculated using a
            degree-preserving approach, which prevnets the repeated selection of the same high degree
            nodes setting 100 degree bins in 1000 relizations. 

    * proptien-protien interactions (PPI) data
        * note 
        * binary PPIs 
            * note
                * we used the urated list of PSI-MI IDs provided by Alonso-Lopez et al (2019) (10) for
                    differentialting binaary interactions among the several experimental methods present
                    in the literature-curated databse.
            * derived from high throughput yeast two-hybrid experiemtns (1)
            * three-dimnesional protien structures
                * 3D protien structure 
                    * Interactome3D (2)
                    * Instruct (3) 
                    * Insider (4) 
                * literature curation 
                    * PINA (5)
                    * MINT (6)
                    * LitBM17 (1)
                    * Interactome#D, instruct, Insider, BioGrid (7)
                    * HINT (8)
                    * HIPPIE (9)
                    * APID (10)
                    * InWeb (11)
                        * interatcions with curation scores greater than 0.175 (75th percentail) were
                            not considered. 
                            * all protiens were mapped to their corresponding Entre ID (NCBI), and the
                                protiends that could not be mapped were removed. 
                            * The final interactomes used in our study coninas 18505 protiends and
                                327924 interatcions (dataset 2) 
        * PPIs identified by afficnity purification followed by mass spectrometry; 
            * BioPlex (12) 
            * QUBIC (13)
            * CoFrac (14)
            * HINT, HIPPEIE, APID, LitBM17, and InWeb
        * kinase substrate interactions
            * KinomeNetworkX (15)
            * PhosphoSitePlus (16)
        * signaling interactions
            * SignalLink (17)
            * InnateDB (18)
        * regulatory interactions.
            * ENCODE consortium.

    * SARs-Cov-2 and human proteins interaction
        * data is retrieved from Gordon et l. (21)
            * we retrived interactions between 26 SARs-CoV-2 proteins and 332 humsn
                proteidns (dataset 1)

    * drug-target information
        * from the DrugBank datasbse.
            * contains 24,609 interactions between 6228 drugs and their 3903 targets, and drug target
                interactions data curated from the literature fro 25 drugs (dataset 3) 
            * we also obtianed differentially expressed genes (DEGs) from the dataset identified by
                exposure of drugs to differnet cell lines (Dataset 4)

* Lung Gene Expression (Fig 2A)
    * we evaluated gene expression in the lung by using GTEX database, considering genes with a
        median count lower than 5 transcripts ( raw coutns) as not expressd. 

* Disease Comorbidities 
    * Pre-existing conditions worsen prognosis and recovery of COVID-19 patients. Previous work showed
    that
    the disease relevance of human proteins targeted by a virus can predict the signs, symptoms, and
    diseases
    caused by that pathogen. This prompted us to identify diseases whose molecular mechanisms
    overlap with
    cellular processes targeted by SARS-CoV-2, allowing us to predict potential comorbidity patterns
    (25–27).
        * We retrieved 3,173 disease-associated genes for 299 diseases (28), finding that 110 of the
        332 proteins
        targeted by SARS-CoV-2 are implicated in other human diseases
            * using Fisher's exact test (p value > 0.05 ), the
               overlap between host proteinds target of the covid19 and 299 disease was not
               statistically significant 
            * Evaluate using network-based overlap between the protiends with 299 disease and the
                host protien target of covid19, S_vb metric (28) is used to evaluate targets v and
                gene pool associaated with disease.
                * it is found that COVID19 disease module doesn't directly overlap with any major
                    disease module. (Fig. S1 and dataset 5)
                    ). 
                    * The diseases
                    closest to the COVID-19 disease module (smallest �!") included several
                    cardiovascular diseases and
                    cancers, whose comorbidity in COVID-19 patients is well documented (29–31) (Fig.
                    S2)

# methodology
* there are 3 places where drug can be binded to proteins.
    1. direct target drugs bind either to a viral protein 
    2. bind to host protien target of the virual proteinds.
    3. bind to the host proteins
        * limit virual activity by perturbing the host subcellular network 

* task
    * covid-19 drug treatment recommendation task (link prediction)

* AI
    * GNN is desinged for COVID-19 reatedment recommenation (14)
        * nodes represent three distinct types of biomedical entities including 
            * drugs, proteins, diseases
        * edges represent four types of edges between th entiteis including
            * PPIs
            * drug-target association
            * disease-protien association
            * drug disease treatments.
        * [[validate]] it is multimodel graph 
            * 2 main components 
                * encoder
                    * a graph convolutional netwokr operating on G and producing embeddings for
                        nodes in G
                * decoder
                    * model optimziing embedding such that they are predictive of known
                        druge-disease indications.
                    * decoder takes nodes embeddings and combines them to reconstruct (predict)
                        label edges in G.
                        * decoders score is obtained from a fucntion whose goal is to assign a score
                            representing how likley it is that drugs v_i will treate disease v_j.
            * embeding from GNN leanred for nodes represnting either COVID-19 or drugs in multimodel
                graph G.
    *  pipeline 
        * goal
            * pipeline goal is to generate list of candidate drugs for COVID-19
        * all drugs embedding are obtained from decoded embedding space.
        * the pipeline search for drugs that are the vicinity of the COVID-19 disease by calculating
            the cosine distance between COVID-19 and all drugs in the decoded embeding space. (41)
        * [[validate]] KNN is used to cluster candidate drugs for COVID-19  
            * validate
                * validate this block by reading (41), but I will skip it for now 
            * 2 parameters for KNN
                * N constrianted the size of the local neighborhood each pipelien looked at in the
                    embedding space when calulating the distances
                * D controlled how tightly the piplein was allowed to pack the embeddigns togethrs.


* Diffusion State Disease 
    * Diffusion State Disease algorithm uses a graph diffusion to dreived a similarity metric for
        pairs of nodes that takes into account how similar they impact the rest of the network. 
    * similarity between a pair of node after graph diffusion is applied.
        Similarity of node pair (A,B) is expected numbers of times when random walk from nodes A visit nodes

* network proximity 
    * We calculated the proximity of the SARS-CoV2 targets to
    drug targets using the proximity (11)

# finding

* alsmot all proetien in SARS-Cov-2 LCC are also expressed in the lung tissue, potentially
    explaining the effectiveness of the virus in causing pulmonary manifestations of the disease. 
* distribution of the size of subnetworks predicted varies according to the method,
    * the AI methods have a smaller variance in the size while methods base dno proixmity tend ot
        have higher variances.

* Gene overlap of the methods involved
with subgraphs for each method. Proximity and Diffusion based methods explore the PPI in a much vast
and diverse way than the AI methods

* Methods inside the same pipeline tend to select similar genes,
the similarity of selected genes across methods is different (Jaccard Index), those genes,
interestingly, also
do not lie in similar neighborhood (similarity), meaning that not only do the genes not overlap
across
methods, but the vicinity the methods explore are also different

* In summary, we found that the SARS-CoV-2 host protein targets do not overlap with proteins
associated
with any major diseases, indicating that a potential COVID-19 treatment cannot be derived from the
arsenal
of therapies approved for a specific disease.
    * These findings argue for a strategy that maps drug targets
    without regard to their localization within a particular disease module.

# FAQs
* how to implement purposed graph diffusion? 
* what is architecutre of decoders?
    * read (41)
* what is one shot indicator vector?
    * read (38) 
* how can network be constructed in AI algorithm?
* what are steps to implement drug repurpsoing?
* what does subnetwork represents?

# content
