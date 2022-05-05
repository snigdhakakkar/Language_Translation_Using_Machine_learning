# Language_Translation_Using_Machine_learning <br />
Implementing English to French Language translation using Machine Learning <br />

A project on Sequence to Sequence Neural Networks : involves Encoders - Decoders <br />


![hello](https://user-images.githubusercontent.com/65984649/167022486-6298f099-4292-4d59-92cb-5b6fd526a55f.jpeg)

**First implementation**: I have implemented a character-level sequence-to-sequence model, processing the input character-by-character and generating the output character-by-character.  <br />

**Steps of implementation **__- <br />
1) Turn the sentences into 3 Numpy arrays, encoder_input_data, decoder_input_data, decoder_target_data: <br />
encoder_input_data is a 3D array of shape (num_pairs, max_english_sentence_length, num_english_characters) containing a one-hot vectorization of the English sentences.  <br />
decoder_input_data is a 3D array of shape (num_pairs, max_french_sentence_length, num_french_characters) containg a one-hot vectorization of the French sentences. <br />
decoder_target_data is the same as decoder_input_data but offset by one timestep. decoder_target_data[:, t, :] will be the same as decoder_input_data[:, t + 1, :]. <br />

2)Train a basic LSTM-based Seq2Seq model to predict decoder_target_data given encoder_input_data and decoder_input_data. The model uses teacher forcing. In teacher forcing, basically decoder LSTM is trained to turn the target sequences into the same sequences but offset by one timestep in the future <br />

3)Decode some sentences to check that the model is working (i.e. turn samples from encoder_input_data into corresponding samples from decoder_target_data).

**Second implementation:** Another implementation is a word-level model, which tends to be more common for machine translation.  <br />

