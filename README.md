### Overview

Transformer architecture, introduced in 2017, play a key role in LLM and modern generative models. The literature lacks of a systematic mathematical treatment and it is plenty of pure optimisation-oriented 
approaches neglecting what is happening behind the scenes and the intuition of this architecture. As a consequence, the aim of this thesis is to delve into the aspects of transformers in mathematical therms. 

### Contents

In the first Chapter we analyze the architecture explaining each component in details. Then, we shift our attention to a posteriori approaches that reduce the complexity of the transformers architecture.
In detail, we explore Sparse Attention, Linear Attention and matrix factorization approaches to scale linearly the complexity. In the third chapter, we focus on the mathematical and geometrical meaning of
the attention scores formula. The experimental session (consisted of a translating task) lead us to a new formula describing at high level the attention mechanism. In simple terms, we force query and keys to attend each other in a specific form such that encode the different roles of attention heads and so telling values where to look to get the context. Not only, the complexity of the architecture is reduced and the formula allow a better explainability of what is behind the scenes.
We conclude the thesis validating the new formula, namely calculating how well the new formula for attention scores approximates the original one. Furthermore, we propose further investigation, far from the scope of this thesis, in accordance with the experiments that we have done, that would constist on studying the role of parameters w and num-pos (respectively the windows size/context and the number of words rare token attends) in the code for the validation as we believe they contain valuable information on the idiom used.
