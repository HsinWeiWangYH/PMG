## Introduction
This page contains the Experimental Setup for the ICASSP 2022 paper.

## Abstract
End-to-end (E2E) neural modeling has emerged as one predominant school of thought to develop computer-assisted language training (CAPT) systems, showing superior performance over conventional pronunciation-scoring based methods. However, current E2E neural methods for CAPT are faced with at least two pivotal challenges. On one hand, most of the E2E methods operate in an autoregressive manner with left-to-right beam search to dictate the pronunciations of an L2 learners. This however leads to very slow inference speed, which inevitably hinders their practical use. On the other hand, E2E neural methods are normally data greedy and meanwhile an insufficient amount of nonnative training data would often reduce their efficacy on mispronunciation detection and diagnosis (MD&D). In response, we put forward a novel MD&D method that leverages nonautoregressive (NAR) E2E neural modeling to dramatically speed up the inference time while maintaining performance in line with the conventional E2E neural methods. In addition, we design and develop a pronunciation modeling network stacked on top of the NAR E2E models of our method to further boost the effectiveness of MD&D. Empirical experiments conducted on the L2-ARCTIC English dataset seems to validate the feasibility of our method, in comparison to some top-of-the-line E2E models and an iconic pronunciation-scoring based method built on a DNN-HMM acoustic model.

##  Dictation Model 
###  Baseline
- Encoder
The encoder modules of our Dictation Models were composed of twelve Conformer-based components (each of which is constructed using four-head attention), 2,048 linear-layer hidden units and 256 output units. 

    Details are as follows：
```
    num_blocks: 12
    attention_heads: 4
    linear_units: 2048
    output_size: 256
    cnn_module_kernel: 15
```
- Decoder
The decoder module of our Dictation Models consisted of six Transformer-based components (with four-head attention) and 2,048 linear-layer hidden units. 

    Details are as follows：
```
    num_blocks: 6
    attention_heads: 4
    linear_units: 2048
    dropout_rate: 0.1
```

###  Proposed
- Encoder
The encoder modules of our Dictation Models were composed of eight Conformer-based components (each of which is constructed using four-head attention), 1,024 linear-layer hidden units and 128 output units. 


    Details are as follows：
```
    num_blocks: 8
    attention_heads: 4
    linear_units: 1024
    output_size: 128
    cnn_module_kernel: 15
```
- Decoder
The decoder module of our Dictation Models consisted of four Transformer-based components (with four-head attention) and 1,024 linear-layer hidden units. 

    Details are as follows：
```
    num_blocks: 4
    attention_heads: 4
    linear_units: 1024
    dropout_rate: 0.1
```

##  Pronunciation Model 
- Transformer ( for phone embedding sequence ) 
    Details are as follows：
```
    num_blocks: 6
    attention_heads: 4
    linear_units: 2048
    output_size: 60
```
- GRU ( for utterance-level embedding ) 
    Details are as follows：
```
    num_layers: 1
```
