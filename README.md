# Word Representation, Text Classification and Machine Translation

### Word Embeddings with Word2Vec
Following things have executed here:
* Preprocessing the training corpus (removed special characters, empty strings, digits and stopwords from the sentences and changed words into lower cases). Sentences with fewer than 3 words or at least empty sentences have been removed.
*  Creating the corpus vocabulary and preparing the dataset (word2idex("word":idx) and idx2word(idx:"word")).
*  Building the skip-gram neural network architecture
    * Initialize and transform the input and context word
    * Merge the inputs and pass these merged inputs to a output layer with sigmoid activation function.
    * Initialize and then compile the model.
* Training the models with 5 epochs
* Getting the word embedding and visualizing them using t-SNE

### Using LSTMs for Text Classification
Following things have executed here:
* Readying the inputs for the LSTM. As there is varying length inputs, a fixed length is obtained by padding and truncating.
* Building the model
    * Sorting the inputs expected and adding an embedding layer.
    * Adding an LSTM layer and finally a fully connected (Dense) layer.
    * The model has a 'binary_crossentropy' loss function and an 'adam' optimizer.
* Training the model with bacth size 1000.
* Model is evaluated on the test data and word embeddings are extracted (for visualization purpose).

### Comparing Classification Models
* Model 1: Neural averaging network using one-hot vectors:
    * The inputs are as an one-hot layer. The second layer is to compute average on all word vectors in a sentence without considering padding.
    * The output vector is piped through a fully-connected layer. The last layer is connected with a single output node with the sigmoid activation function. The final value is a float between 0 and 1.
* Model 2: Neural averaging network using embedding layer:
    * Instead of one-hot vectors, embeddings are used (integer-encoded vocabulary and looks up the embedding vector for each word-index).
* Model 3: Using pre-trained word embeddings (GloVe):
    * Neural bag of words using pre-trained word embeddings
        * Fine-tuning the pre-trained embeddings
    * LSTM with pre-trained word embeddings
* Model 4: Adding extra dense layer into Neural averaging network model:
    * Adding one-extra and two-extra dense layers
* Model 5: CNN for Text Classification
    * Building a basic CNN model and then adding an extra convolutional layer to it.

### Aspect-Based Sentiment Analysis
Given a review and an aspect, the sentiment conveyed is classified towards that aspect on a three-point scale: POSITIVE, NEUTRAL, and NEGATIVE. According to the word_index and the tokenizer function (text_to_word_sequence), the review text and aspect words are converted to word tokens and integers separately.
* Neural bag of words without pre-trained word embeddings
* CNN without pre-trained word embeddings
* Using pre-trained word embeddings:
    * Neural bag of words using pre-trained word embeddings
    * CNN with pre-trained word embeddings
* Model with multiple-input:
    * Neural bag of words model with multiple-input
    * CNN model with multiple-input
* Another LSTM model

## Neural Machine Translation
Deep neural network using seq2seq modelling with and without attention.