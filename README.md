# neural-machine-translation

 1- the main goal
 
we'll be building a machine learning model to go from once sequence to another, using PyTorch and torchtext. This will be done on German to English translations, but the models can be applied to any problem that involves going from one sequence to another, such as summarization, i.e. going from a sequence to a shorter sequence in the same language.


2- the dataset

spaCy has model for each language ("de_core_news_sm" for German and "en_core_web_sm" for English) which need to be loaded so we can access the tokenizer of each model.

3- the model

The most common sequence-to-sequence (seq2seq) models are encoder-decoder models, which commonly use a recurrent neural network (RNN) to encode the source (input) sentence into a single vector. In this notebook, we'll refer to this single vector as a context vector. We can think of the context vector as being an abstract representation of the entire input sentence. This vector is then decoded by a second RNN which learns to output the target (output) sentence by generating it one word at a time.

we now use a bidirectional RNN. With a bidirectional RNN, we have two RNNs in each layer. A forward RNN going over the embedded sentence from left to right (shown below in green), and a backward RNN going over the embedded sentence from right to left (teal). All we need to do in code is set bidirectional = True and then pass the embedded sentence to the RNN as before.

Next up is the attention layer. This will take in the previous hidden state of the decoder,  𝑠𝑡−1 , and all of the stacked forward and backward hidden states from the encoder,  𝐻 . The layer will output an attention vector,  𝑎𝑡 , that is the length of the source sentence, each element is between 0 and 1 and the entire vector sums to 1.

4- the results

we got Train PPL: 4.493  and valid PPL: 11.493

and Test PPL: 10.752

