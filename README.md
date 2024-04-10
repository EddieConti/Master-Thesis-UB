### Overview

Transformer architecture, introduced in 2017, play a key role in LLM and modern generative models. The literature lacks of a systematic mathematical treatment and it is plenty of pure optimisation-oriented 
approaches neglecting what is happening behind the scenes and the intuition of this architecture. As a consequence, the aim of this thesis is to delve into the aspects of transformers in mathematical therms. 

### Contents

In the first Chapter, after introducting the topic, we analyze the architecture explaining each component in details from both a theoretical and intuitive point of view. Subsequently, we shift our attention to a posteriori approaches that reduce the complexity of the transformers architecture. In detail, we explore:
* Sparse Attention,
* Linear Attention, 
* Matrix factorization.
Those approaches allow us to scale linearly the complexity of transformers.

In the third chapter, we focus on the mathematical and geometrical meaning of the attention scores formula
$$ Softmax\Bigl(\frac{QK^T}{\sqrt{k}}\Bigr). $$
$ Softmax((QK^T) / sqrt(k)) $
The experimental session (consisted of a translating task) lead us to a new formula describing at high level the attention mechanism:
$$
I_nP+\tilde{E}, \qquad P,\tilde{E} \in \mathbb{R}^{n\times n}, \quad P \in \Sigma.
$$
In simple terms, we force query and keys to attend each other in a specific form such that encode the different roles of attention heads and so telling values where to look to get the context. Not only, the complexity of the architecture is reduced and the formula allow a better explainability of what is behind the scenes. In mathematical terms, we can think of this formula as projecting the attention scores matrix onto the space 
$$
\mathcal{X}=\{ B+E_{rr}\,\, \text{such that}\,\, B,E_{rr} \in \mathbb{R}^{n \times n}\}
$$
where $B$ is a band matrix of fixed bandwidth $w<<n$ and $E_{rr}$ is a sparse matrix. We then prove that this space is a convex, closed, non-empty subspace of $\mathcal{M}_n(\mathbb{R})$ which is an Hilbert space with the norm
$$
|A|:=\sum_{i,j} |a_{i,j}| \qquad a_{i,j} \in A.
$$
This allows us to say that the projection on this space is well-posed and unique. We conclude the thesis validating the new formula, namely calculating how well the new formula for attention scores approximates the original one. Furthermore, we propose further investigation, far from the scope of this thesis, in accordance with the experiments that we have done, that would constist on studying the role of parameters w and num-pos (respectively the windows size/context and the number of words rare token attends) in the code for the validation as we believe they contain valuable information on the idiom used.

### Folders

* In the folder code experiments it is possible to find all the code regarding the transformer and the experiments carried out. The file matrix_functions contains several useful function to generate sturctured matrices and Attn_approx contains the validation experiments computing how much well we are approximating the original formula. The file matrix_list is pickle file in which we saved the attention score matrices arising from the experiments. The visualization of all the experiments can be seen in the inside folder Attention visualization.
* The folder Images contains all the images used to better understand papers and intuition.
* The folder papers contains all the papers we used to provide foundations to our research and also to understand the state of art in literature.
* The PDF file is the text file of the thesis.
 
  
