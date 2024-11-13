---
date: 2024-11-05 02:50
sources: 
tags:
  - zettel
  - ai
status: literature
publish: true
---

## Source Information:

* Author(s): `Ashish Vaswani`, `Noam Shazeer`, `Niki Parmar`, `Jakob Uszkoreit`, `Llion Jones`, `Aidan N. Gomez`, `Lukasz Kaiser`, `Illia Polosukhin`
* Title of Source: `Attention Is All You Need`
* Publication Information (e.g., Journal name, date): 2023
* Link: [Attention Is All You Need](https://arxiv.org/abs/1706.03762)

## Annotations:

> [!PDF|yellow] [[Attention Is All You Need.pdf#page=1&selection=62,0,63,67&color=yellow|Attention Is All You Need, p.1]]
> > The dominant sequence transduction models are based on complex recurrent or convolutional neural networks that include an encoder and a decoder

> [!PDF|yellow] [[Attention Is All You Need.pdf#page=1&selection=63,69,65,9&color=yellow|Attention Is All You Need, p.1]]
> > The best performing models also connect the encoder and decoder through an attention mechanism
> 
> > [!PDF|yellow] [[Attention Is All You Need.pdf#page=1&selection=65,11,68,0&color=yellow|Attention Is All You Need, p.1]]
> > We propose a new simple network architecture, the Transformer, based solely on attention mechanisms, dispensing with recurrence and convolutions entirely.
> 
> > [!PDF|yellow] [[Attention Is All You Need.pdf#page=1&selection=69,0,71,18&color=yellow|Attention Is All You Need, p.1]]
> > Experiments on two machine translation tasks show these models to be superior in quality while being more parallelizable and requiring significantly less time to train
> 
> 

> [!PDF|evidence] [[Attention Is All You Need.pdf#page=1&selection=71,20,73,25&color=evidence|Attention Is All You Need, p.1]]
> > Our model achieves 28.4 BLEU on the WMT 2014 Englishto-German translation task, improving over the existing best results, including ensembles, by over 2 BLEU

> [!PDF|evidence] [[Attention Is All You Need.pdf#page=1&selection=73,27,76,32&color=evidence|Attention Is All You Need, p.1]]
> > On the WMT 2014 English-to-French translation task, our model establishes a new single-model state-of-the-art BLEU score of 41.8 after training for 3.5 days on eight GPUs, a small fraction of the training costs of the best models from the literature.

> [!PDF|note] [[Attention Is All You Need.pdf#page=2&selection=24,0,42,71&color=note|Attention Is All You Need, p.2]]
> > Recurrent models typically factor computation along the symbol positions of the input and output sequences. Aligning the positions to steps in computation time, they generate a sequence of hidden states ht, as a function of the previous hidden state ht−1 and the input for position t. This inherently sequential nature precludes parallelization within training examples, which becomes critical at longer sequence lengths, as memory constraints limit batching across examples.

> [!PDF|important] [[Attention Is All You Need.pdf#page=2&selection=54,0,68,49&color=important|Attention Is All You Need, p.2]]
> > Attention mechanisms have become an integral part of compelling sequence modeling and transduction models in various tasks, allowing modeling of dependencies without regard to their distance in the input or output sequences [ 2, 19 ]. In all but a few cases [ 27 ], however, such attention mechanisms are used in conjunction with a recurrent network.
> 
> **Problem statement that the paper suggests**

> [!PDF|187, 97, 229] [[Attention Is All You Need.pdf#page=2&annotation=5958R|Attention Is All You Need, p.2]]
> > The goal of reducing sequential computation also forms the foundation of the Extended Neural GPU [16 ], ByteNet [ 18 ] and ConvS2S [ 9], all of which use convolutional neural networks as basic building block, computing hidden representations in parallel for all input and output positions. In these models, the number of operations required to relate signals from two arbitrary input or output positions grows in the distance between positions, `linearly for ConvS2S and logarithmically for ByteNet`
> 
> The Actual Problem

> [!PDF|important] [[Attention Is All You Need.pdf#page=2&selection=96,3,98,83&color=important|Attention Is All You Need, p.2]]
> > In the Transformer this is reduced to a constant number of operations, albeit at the cost of reduced effective resolution due to averaging attention-weighted positions, an effect we counteract with Multi-Head 
> 
> Improvement the transformer is doing


> [!PDF|note] [[Attention Is All You Need.pdf#page=2&selection=107,0,109,25&color=note|Attention Is All You Need, p.2]]
> > To the best of our knowledge, however, the Transformer is the first transduction model relying entirely on self-attention to compute representations of its input and output without using sequencealigned RNNs or convolution
> 
> Transformer uses self-attention completely

> [!PDF|187, 97, 229] [[Attention Is All You Need.pdf#page=2&annotation=5961R|Attention Is All You Need, p.2]]
> > Most competitive neural sequence transduction models have an encoder-decoder structure [  5,  2  ,  35]. Here, the encoder maps an input sequence of symbol representations  (x1, ..., xn)  to a sequence of continuous representations  z  = (z1, ..., zn).  Given  z, the decoder then generates an output sequence  (y1, ..., ym)  of symbols one element at a time. At each step the model is auto-regressive [10], consuming the previously generated symbols as additional input when generating
> 
> Encoder-Decoder basics

![[Attachments/Attention Is All You Need 2.png]]

[[Attention Is All You Need.pdf#page=3&rect=190,388,425,737|Attention Is All You Need, p.3]]

> [!PDF|evidence] [[Attention Is All You Need.pdf#page=3&selection=10,0,46,4&color=evidence|Attention Is All You Need, p.3]]
> > The encoder is composed of a stack of N = 6 identical layers. Each layer has two sub-layers. The first is a multi-head self-attention mechanism, and the second is a simple, positionwise fully connected feed-forward network. We employ a residual connection [ 11 ] around each of the two sub-layers, followed by layer normalization [1]. That is, the output of each sub-layer is LayerNorm(x + Sublayer(x)), where Sublayer(x) is the function implemented by the sub-layer itself. To facilitate these residual connections, all sub-layers in the model, as well as the embedding layers, produce outputs of dimension dmodel = 51
> 
> Encoder stack

> [!PDF|evidence] [[Attention Is All You Need.pdf#page=3&selection=51,0,69,1&color=evidence|Attention Is All You Need, p.3]]
> > The decoder is also composed of a stack of N = 6 identical layers. In addition to the two sub-layers in each encoder layer, the decoder inserts a third sub-layer, which performs multi-head attention over the output of the encoder stack. Similar to the encoder, we employ residual connections around each of the sub-layers, followed by layer normalization. We also modify the self-attention sub-layer in the decoder stack to prevent positions from attending to subsequent positions. This masking, combined with fact that the output embeddings are offset by one position, ensures that the predictions for position i can depend only on the known outputs at positions less than i
> 
> Decoder Stack

![[Attachments/Attention Is All You Need 5.png]]

[[Attention Is All You Need.pdf#page=4&rect=133,545,484,727&color=evidence|Attention Is All You Need, p.4]]

> [!PDF|234, 82, 82] [[Attention Is All You Need.pdf#page=4&annotation=5964R|Attention Is All You Need, p.4]]
> > Scaled Dot-Product Attenti
> 
> Refer the heading - seems very complicated

![[Attachments/Attention Is All You Need 6.png]]

[[Attention Is All You Need.pdf#page=4&rect=209,297,404,333&color=evidence|Attention Is All You Need, p.4]]

> [!PDF|evidence] [[Attention Is All You Need.pdf#page=4&selection=111,0,111,19&color=evidence|Attention Is All You Need, p.4]]
> > Multi-Head Attentio
> 
> Refer heading - seems very complicated

![[Attachments/Attention Is All You Need 8.png]]

[[Attention Is All You Need.pdf#page=5&rect=176,605,441,659&color=evidence|Attention Is All You Need, p.5]]

> [!PDF|234, 82, 82] [[Attention Is All You Need.pdf#page=5&annotation=5967R|Attention Is All You Need, p.5]]
> > Transformer uses multi-head attention in three different ways: 
> > - In "encoder-decoder attention" layers, the queries come from the previous decoder layer, and the memory keys and values come from the output of the encoder. This allows every position in the decoder to attend over all positions in the input sequence. This mimics the typical encoder-decoder attention mechanisms in sequence-to-sequence models such as [38, 2, 9]. 
> > -  The encoder contains self-attention layers. In a self-attention layer all of the keys, values and queries come from the same place, in this case, the output of the previous layer in the encoder. Each position in the encoder can attend to all positions in the previous layer of the encoder. 
> > -  Similarly, self-attention layers in the decoder allow each position in the decoder to attend to all positions in the decoder up to and including that position. We need to prevent leftward information flow in the decoder to preserve the auto-regressive property. We implement this inside of scaled dot-product attention by masking out (setting to −∞) all values in the input of the softmax which correspond to illegal connec
> 
> Application of attention in the transformer architecture



## New Terms:

- **BLEU Score**: Number between `0 and 1` for evaluating the `quality of text` which has been `machine-translated` from `one language to another`.


## Quotes (Optional):



## Evaluation:

* Briefly assess the credibility and usefulness of the source. 
* Is the information reliable and unbiased? 
* Does it fit the scope of your research?

## Further Exploration (Optional):

* Jot down any questions raised by the source or areas you'd like to investigate further.
* Note any references cited by the author that might be relevant to your research. [[cited-source-1]] [[cited-source-2]]

