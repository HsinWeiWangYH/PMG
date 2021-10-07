## Introduction
This page contains the Experimental Setup for the ICASSP 2022 paper.

## Abstract


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
