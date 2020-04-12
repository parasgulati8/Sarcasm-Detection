# Sarcasm Detection
 Detects Sarcasm in an input sentence

## Dataset

The dataset is acquired from the below api :

https://storage.googleapis.com/laurencemoroney-blog.appspot.com/sarcasm.json

The data is in Jason format. It is first loaded using `json.load()` and then preprocessed to store rhe text and the labels in separate lists. 

Thetext is first tokenized using the `Tokenizer` from keras. Tokenizer is then fit on text sequences using the `fit_on_texts` method. Next, the text sequences are converted to numerical sequences using the `tokenizer.texts_to_sequences` method. Embedding layers is used to convert the words into 16-dimenional vectors. The hyper-parameter vales used are as per below :

`vocab_size = 1000`

`embedding_dim = 16`

`max_length = 120`

`trunc_type='post'`

`padding_type='post'`

`oov_tok = "<OOV>"`

`training_size = 20000`

Model architecture is composed of Embeddng layer, bidirectional LSTM layer, followed by two dense layers. The loss function used in `binary_crossentropy` and optimizer used is `adam` optimizer. Model is trained for 50 epochs.

## Result

![Accuracy](https://github.com/parasgulati8/Sarcasm-Detection/blob/master/images/accuracy.JPG)

The highest validation accuracy achieved is 83.11% on 5th epoch. 

![Loss](https://github.com/parasgulati8/Sarcasm-Detection/blob/master/images/loss.JPG)
