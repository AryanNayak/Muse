## *Conversational generative chatbot*
   
   In this chatbot we used the 'seq2seq model' also called the encoder-decoder model, that uses Long Short Term Memory- LSTM for text generation from the training corpus. This model predicts a word given in the user input and then each of
the next words is predicted using the probability of likelihood of that word to occur. We used a method called 'teacher forcing' to train the decoder which enables it to predict the following words in a target sequence given in the previous words.
  
### *Steps followed:*

1. Preprocessing the dataset:
   - We used Regular Expressions to clean our corpus. Later made pair-like human response-bot response to train our seq2seg model accurately.
   
2. Training setup:
   - We implemented three matrices of one-hot vectors, Encoder input data, Decoder input data, and Decoder output data. The reason for using two matrices lies in teacher forcing which is used by the seq2seq model while training input token from the previous timestep to help the model in predicting current target token.
   
3. Encoder-decoder training setup:
   - Our encoder model required an input layer which defines a matrix for holding the one-hot vectors and an LSTM layer with some number of hidden states. Decoder model's structure is almost the same as encoder’s but here we pass in the state data along with the decoder inputs.
   - We imported Keras, LSTM, Dense from tensorflow to help us build the model.
   
4. Building and training seq2seq model:
   - We used rmsprop as an optimizer and categorical_crossentropy as our loss function. We call the .fit() method by giving the encoder and decoder input data (X/input) and decoder target data (Y/label).

5. Testing setup and final model
   - we established the decoder input layer, the final states from the encoder, the decoder outputs from the Dense layer of the decoder, and decoder output states which is the memory during the network from one word to the next.
   - Final model can be viewed [here.](https://github.com/AryanNayak/Muse/blob/main/Conversational%20chatbot/generative_cb.ipynb)
   
