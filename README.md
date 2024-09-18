# Text-Classification-using-FNet

### Introduction
In this we will demonstrate the ability of FNet to achieve comparable results with a vanilla Transformer model on the text classification task. We will be using the IMDb dataset, which is a collection of movie reviews labelled either positive or negative (sentiment analysis).

### Model
Transformer-based language models (LMs) such as BERT, RoBERTa, XLNet, etc. have demonstrated the effectiveness of the self-attention mechanism for computing rich embeddings for input text. However, the self-attention mechanism is an expensive operation, with a time complexity of O(n^2), where n is the number of tokens in the input. Hence, there has been an effort to reduce the time complexity of the self-attention mechanism and improve performance without sacrificing the quality of results.

### Tokenizing the data
We'll be using the keras_nlp.tokenizers.WordPieceTokenizer layer to tokenize the text. keras_nlp.tokenizers.WordPieceTokenizer takes a WordPiece vocabulary and has functions for tokenizing the text, and detokenizing sequences of tokens.  
Before we define the tokenizer, we first need to train it on the dataset we have. The WordPiece tokenization algorithm is a subword tokenization algorithm; training it on a corpus gives us a vocabulary of subwords. A subword tokenizer is a compromise between word tokenizers (word tokenizers need very large vocabularies for good coverage of input words), and character tokenizers (characters don't really encode meaning like words do).

### Building the model
Now, Define the model! We first need an embedding layer, i.e., a layer that maps every token in the input sequence to a vector. This embedding layer can be initialized randomly. We also need a positional embedding layer that encodes the word order in the sequence. The convention is to add, i.e., sum, these two embeddings. KerasNLP has a keras_nlp.layers.TokenAndPositionEmbedding layer which does all of the above steps for us.

### Conclusion
FNet outperforms the baseline model in computational efficiency, achieving a 1.7x speedup (4s vs 6.8s) with minimal accuracy loss (0.75%). Despite a slight drop in accuracy (0.8399 vs 0.8474), FNet's efficiency gain makes it suitable for real-time applications and large-scale deployments.

