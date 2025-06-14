Sequence to sequence model
Encoder-Decoder approach
the idea is to get an input sequence that goes into an encoder and produces context which si a vector. The decoder takes the context and produces an output. The encoder and decoder are NNs.

Seq2Seq with RNNs: compress the input and decompress it in the last layer, but this fades the meaning of the input vectors by going on. Attention instead allows to recover the original meaning of each input vector.

The input text gets tokenized and each word gets inputed to the encoder. Each word produces an hidden state.

This approach used RNNs until 2015: the problem was that every input sequence was represented with a single state. The last one hidden state compressed all the considered words right until that one.
The idea switched to instead of compressing all the hidden states into one, the states were kept divided. The decoder can "pay attention" to one particular hidden state at his choice.
This allows to highlight particular hidden states to produce a particular output word.

We go from having one vector to decode using a weighted sum of vectors which are the hidden states. We score each hidden state and gice them softmax scores which we use to multiply them. 

Every state of the art model in each deep learning community has become the transformer.

Given a word we tokenize it an embed in a vector each token. We obtain a nxd vector which resembles the input. This vector gets divided in other 3 vectors Q,K,V. 
K reflects the input data, Q the examined input and V which depends on attention to alter output.
Q and K transposed are multiplied to obtain the attention matrix QK^t. 
This matrix passes through softmax and returned the A matrix. 
The V matrix gets summed to the A matrix to obtain the output matrix. Z has a more abstract and general representation for the input.

The encoder:
The input goes into an input embedding layer and gets split into tokens: the tokens are indices into a vocabulary, which is 32k tokens big. Each index is transoformed into a vector of numbers (768-1536).
Now we do the positional encoding: to address the problem of natural language that is not positional invariant we need to sort the words. For each position of each word we sum incrementally bigger values (+10,+20...). This process is called positional encoding.
We then perform the transformation that is called multi-headed self-attention which returns the Z abstract matrix. This process related words between them in the sentence: I love my cat I just fed him is a sentece in which cat and him will be contextualized and related to each other.
The first step is the Feed Forward set in which pretrained knowledge is set. This is a multi layer perceptron.
Add and norm skip connections allow output vectors to skip refinement if they do not need to go trough attention again.
Normalization standardizes input across all the network by scaling the input between 0 and 1 to make everything more trainable.
The idea is to stack multiple attentions on top of each other to be able to process inputs and get more abstract representation of the input. This is called multi-head self attention.

point wise FF adds the last refinement to the output of the multi head attention and is where memory of the transformer lives.

Add and norm: skip connections allow outputs form each layers to be added to deeper layers and normalization standardizes inputs across features for each data 

MoE

The decoder:
The output is produced sequentially: we want to produce the probability for each token depending on the probabilities of the previously generated tokens. The first token is produced starting form X which is the output of the encoder. If we sample each of the tokens based on the probability we obtain the final output.
Masked self-attention hides the future words from the input but works exactly as the multi head attention.
min 14.12 issue with LLMs
Each decoded token looks at the encoder output: this is called Cross Attention and cross referenced decoder and encoder layers. 
Cross attention, gets keys and values from encoder but uses the query matri from the decoder.

NLP leverages transformers:
- BERT: encoder only architecture is used for contextualization of input sequences and is good in predicting words in the middle of the sentence for example. 
- GPT: decoder only architecture that given an input sequence predicts the last word that follows the input.
Vision: the image is tokenized into smaller chunks like 16x16 pixels of the image. The transformer encoder is used to predict the class of elements in the image etc.
	Vision Transformer: tokenize the image considering 16x16 pixels and creating a vector embedding.
Speech: we can translate sound in spectograms and the output which is an image is then inputed in the transformer as it happens in vision.
Reinforcement learning: sequence modeling. We cast the RL task in a language modeling task: for example in the case of training a model to win a videogame is to take a snapshot of the game and predict the next move consequently by inputing the image as in vision.

Anything that can be tokenize can be fed into a transformer and perform state of the art results.

There are multiple decoding strategies, we do not necessarly rely on greedy strategy that picks the token with the highest probabilities.

RL from human feedback, the idea is to have a model that interacts with a human that gives positive negative feedback and this updates the model parameters.

Monte Carlo Tree strategy
Mixture of Experts
Complex reasoning paths: chain of thougth

Next token prediction requires for specific abilities that the model needs to have. 
Training stages:
- pretraining, next token prediction on massive amounts of data, learn general languages understanding
- fine tune on instruction-response examples
- RLHF: use human feedback for RL
- reward optimization, learn a reward model from human output.

Generalizability embeddings: a model that generates the most possible general embeddings for any possible field. 

Advanced NLP
The LLMs  are mostly mimicking patterns in the training data. It should instead develop reasoning capabilities.
Few-shot learning, Generalization, Reasoning (events and consequent effects).
Thinking:  we try to provide few shot examples to explain to the LLM how should it reason to accomplish a task. This reasoning logics should be human like to obtain better results.
Reasoning is one ability the LLMs can develop: chain of thought consists in providing example on how to reason. 
least-to-most prompting: teach the model to decompose the problem and perform a task.
chain of thought does not perform well when the problem to solve is harder than the examples.
Reasoning with the decompose and recompose idea: decompose and then combine again the tasks.
Step by step reasoning: we instruct the model to decompose the problem and we do not need rationales. 
Analogical reasoning: we provide a similar problem with its solution.
CoT without prompting: we do not specify anything in the prompt but we provide tell the LLM to start with different initial decoding steps, this generates different reasoning paths. Out of many reasoning steps, there will be some with optimal results.
Self-constency: when generating different reasoning path we can then make the LLM aggregate them in one single final optimal reasoning path.
Irrelevant context harms irrevelvant context.
Atom of thougths, Markov chains.
Self-RAG
Reasoning models: we incorporate all the techniques listed above and push even more the reasoning technique. The idea is to identify the budget and define on which to invest.
STaR: framework to define a cycle to follow when implementing a reasoning process.
Process Reward Models: estimate the advantages on following a specific reasoning paths.
DeepSeek R1: fine tune the model to formally produce a <think> process in the answer. During RL we have accuracy and formal rewards.
Alternative view: learn to reason in the latent space and this means that the model is fed vector embeddings to reason on. Recurrent thinking in latent space.
Probes in LLMs: we input a sentence and froze the weights and its vectorial representation. This is taken and used to train a prober to predict the outcome. 



