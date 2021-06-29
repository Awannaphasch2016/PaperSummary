# STATUS
* incomplete. stop at the begining of "StemGNN Block" section
# Citation

    * @article{cao2021spectral,
      title={Spectral temporal graph neural network for multivariate time-series forecasting},
      author={Cao, Defu and Wang, Yujing and Duan, Juanyong and Zhang, Ce and Zhu, Xia and Huang, Conguri and Tong, Yunhai and Xu, Bixiong and Bai, Jing and Tong, Jie and others},
      journal={arXiv preprint arXiv:2103.07719},
      year={2021}
    }

# INTRODUCTION
# REFERENCES
* url
    * https://papers.nips.cc/paper/2020/file/cdf6581cb7aca4b7e19ef136c6e601a5-Paper.pdf
# TERMINOLOGY
* Gated Recurrent Unit (GRU)
* Spectral Sequential (spe-Seq) cell
* Graph Fourier Transform (GFT)
* Discrete Fourier Transform (DFT)
* residual ocnnections
* skip-connection
# RELATED WORK
# KEY CONTRIBUTION
* Spectral Temporal Graph Neural Network (StemGNN) is designed for multivariate time-series input.
# HOW AUTHOR COME UP WITH THIS IDEA
# FURTHER READING
# FUTURE DIRECTION
# CHALLENGES
# STANDARD AND BASELINE
# METHODOLOGY
* architecture
    * latent correlation layer
        * note
            * sometimes we do not have a pre-defined graph structure as prior, we can leverage the 
                self-attention 
                mechanims to learn latent correlations between multiple time-series automatically.
                * in this way, the model emphasized task-specific correlations in a data-driven fashion.
        * input is fed to GRU layer
            * calculate hidden state corresponding to each timestamp t sequentially
        * last hidden state of GRU is used as temporal embedding of the entire time-series
        * weight matrix is calculated by self-attention
            * weight matrix = adjacency matrix
    * stemGNN 
        * stemGNN is a stack of stemGNN block with skep connections
            * residual connections are employed to stack multiple stemGNN blocks to build deeper models
            * there are 2 stemGNN blocks.
                * the second block tried to approximate the residual between the ground-truth 
                    values and the reconstructed values from the first block. 
        * stemGNN block
            * Graph Fourier Transform (GFT) capture interseries relationships.
                * GFT is also multivariate time-series.
                    while GFT does not learn intra-series temporal relationship explicitly.
            * Spe-Seq Cell is used on the output of GFT to learn temporal pattern in the frequency domain.
                * it aims to decompose each idnidvual time-series after GFT into freuqcny basis.
                    and lean features representation on them.
                * it consist of 4 componenets in order
                    * Discrete Fourier Tranform (DFT)
                        * Discrete Fourier Transform (DFT) learn the representation of the input time-series
                            on the trigonometric basis in the frequency domain
                            * which captures the repeated pattern in the periodic data or the auto-correlation 
                                features.
                    * 1D convolution
                    * GLU
                    * Invesr Discreate Fourier Transform (IDFT)
                        * Next, IGFT is applied on the sum to obtain the jth channel Z_j of the output
                            * where Z is output embedding
            * inspired by [19],
                * we use learnable parameters to represent basis vectors V and a fully-connected 
                    layer to generate basis expansion coefficient \theta base on Z.
                    * Y = V * \theta
            * there are 2 output "branch"
                * forecasting branch
                    * to forecasting future values
                * backcasting branch
                    * to reconstruct history values.
                    * backcasting branch helps regulate the functional space for the block to represent
                        time-series data.
                        * [[re-written]] this represents output of the block (whose input is a graph)
                            as time-series.
        * Spectral Graph convolution (GConv)
            * Spectral Graph convolution is ocmposed of 3 steps
                1. the multivriate time-series input is projected to the spectral domain GFT.
                2. The spectral representation is fileterd by a graph convolution opertor with 
                    learnable kernels.
                3. Inverse Graph Fourier Transform (IGFT) is applied on the spectral representation 
                    to generate final output 

# RESULT
# FREQUENCY ASK QUESTION 
* how does self-attention mechanism works?
    * eg Query-Key-Value used in transformation
* what is Graph Fourier Transform (GFT)? 
* what is residual connections?
* what is skip connection?
