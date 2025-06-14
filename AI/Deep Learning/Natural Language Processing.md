Concerned to providing computers the ability to process data expressed in natural language.

Natural language is not only textual: can be sign language, ancient text and speech/audio.

When the goal is to translate words, we need to learn a machine translation sytem. 

Language is complex because is represented by a linear signal when spoken and the meaning depends from the context. 

Representing language and signal:
- words are represented by strings, issues with bytes representation.
- despite similar letters and inclusion words could be completely unrelated. Also the spelling could be close with completely inrelated words.
Words with close meaning should have similar representations.
Possible ideas:
- Bag of words: simple idea which defines a vocabulary for all the possible words and encodes each word with a vector of words in which only the position relative to a word set to 1 if it is present in the sentence.
	- not scalable, not context aware, not ordered, the vocabularies can be too large.
- TF-IDF: replaces 1 and 0 with numbers that reflect the importance of the word in the document. The importance of the word depends on its frequency in the document.
- Language model: statistical models which assigns probabilities to the most likely next word in a sentence. The model considers a vocabulary and assignes a probability to each word appearing which is 1 in total for all the words combined.
- Unigram language model: assumes every word is independent, and to guess a sentence it multiplies the probabilities of the single words. Issues with new words and context.
- N-gram language models: condition the next probability to all the words we learned in the past. The product is compound to all the subsequence. 
Evaluation of models: perplexity quantifies how well a LM predicts a sequence of words. It is related to the entropy which is the number of bits to represent a word. Intuitively the lower the perplexity the more I am sure of my prediction.

Featurization models: embedding table which is a look up table in which all the words have a vector representing it. Then we compute a softmax to obtain the probability for each word.
- Neural Language Modeling: is a type of language modeling that uses neural networks to predict the probability of a sequence of words. In simpler terms, it's about training a neural network to predict the next word in a sentence, given the preceding words.

Word2Vec: algorithm to turn words into vectors, 2 methods:
- continuos bag of words, run a sliding window across the tet and given a sentence we predict its context.
- skip gram training system
The obtianed embedding table is very semantic.

Recurrent Neural Networks: gradually builds an internal representation of the sentence. Good for text generation but has limits. It has infinite context length and memory and account for word ordering. The issues is the training: vanishing and exploding gradients. Gradient get slower or explode after some long sequences. LSTM and GRU can be used to prevent from this. LSTM has input, output and forget gates used to address these issues.
Stacked and bidirectional RNNs are proposed solution invented in the years. 



