# Transformer from "Attention is all you need" for language translation

## Project description
My own implementation of the Transformer proposed in the paper [Attention Is All You Need](https://arxiv.org/abs/1706.03762). I applied the Transformer to translate sentences from Portuguese to English. 

## Implementation
[Jupyter Notebook](https://nbviewer.jupyter.org/github/vgkortsas/Transformer/blob/master/Transformer_language_translation.ipynb)

## Requirements
A full list of the requirements is given [here](https://github.com/vgkortsas/Transformer_language_translation/blob/master/requirements.txt). The Python and deep learning library versions are:
- Python 3.5.5
- TensorFlow 1.15.0

## Some comments on the importance of the Transformer
### Challenges of the encoder-decoder model ***with*** attention
<img src="https://github.com/vgkortsas/Transformer/blob/master/images/attention2.png" width="500">


The **encoder-decoder architecture with attention** has the following challenges:
* The sequential nature of RNNs/LSTMs results in **lack of parallelization**.
* **Increased computational complexity** of computing a separate context vector for every step of decoder.
*  The **difficulty of learning long-range dependencies** in the network. 
This does not refer to the dependency between the encoder and decoder sequences, since this has been handled by the attention mechanism in encoder-decoder sequences. It is related with the fact that the attention model **ignores the attention information inside the source sentence and the target sentence**.

### Transformer
<img src="https://github.com/vgkortsas/Transformer/blob/master/images/transformer_full.png" width="600">
Transformer is a novel network architecture that aims to solve sequence-to-sequence tasks, while handling long-range dependencies with ease. It is an architecture for transforming one sequence into another one with the help of two parts (Encoder and Decoder), but it differs from the previously described/existing sequence-to-sequence models because it is based solely on attention mechanisms without any use of LSTMs or RNNs. 

The novel idea of the Transformer is to extend the attention mechanism to the processing of input and output sentences themselves as well. In addition, instead of going from left to right using RNNs and feeding the encoder one word at a time, the Transformer allows the encoder and decoder to see the entire input sequence all at once, directly modeling these dependencies using self-attention. 

Quoting from the paper "The Transformer is the first transduction model relying entirely on self-attention to compute representations of its input and output without using sequence-aligned RNNs or convolution". Here, “transduction” means the conversion of input sequences into output sequences.  

#### Advantages of the Transformer
The Transformer has the following advantages over the sequence to sequence models with attention:
*   **Parallelization:** The transformer allows the encoder and decoder to see the entire input sequence all at once, directly modeling these dependencies using self-attention.
*   **Long-range dependency:** Self-attention allows to handle dependencies between input or output tokens themselves.

#### Disadvantages of the Transformer
If the input does have a temporal/spatial relationship, like text, some positional encoding must be added or the model will effectively see a bag of words.

## References
*   [Attention Is All You Need](https://arxiv.org/abs/1706.03762)
*   [Seq2seq pay Attention to Self Attention: Part 2](https://medium.com/@bgg/seq2seq-pay-attention-to-self-attention-part-2-cf81bf32c73d)
*   [Why do Transformers yield Superior Sequence to Sequence(Seq2Seq) Results?](https://medium.com/saarthi-ai/transformers-attention-based-seq2seq-machine-translation-a28940aaa4fe)





