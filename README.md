# Machine Translation: English to French

This project is to build an end-to-end machine translation pipeline that takes English text and retuns French translation. The model is built from scratch based on Encoder-Decoder and RNN structures. 

## Dataset
LLMs are typically trained on large corpus (at least 100M+ tokens). To train the model in a reasonalbe time and limited resources, a dataset that contains a small vocabulary has been chosen for this project.

The [dataset](https://github.com/sooolee/machine_translation_eng_to_french/tree/main/data) used for this project have 138k paris of English and French sentences. The maximum length (number of tokens) is 15 for English and 21 for French.

The dataset was split to 'train' and 'test' datasets with a 80:20 ratio. The train dataset was further split to 'train' and 'validation' sets with a 90:10 ratio during training. 

## Data Preprocessing
The data were already lowercased, but needed further preprocessing. The setences were tokenized (into word ids) and padded using `keras` `Tokenizer` and `pad_sequences`.

## Model Architecture
Encoder has a embedding layer with a embedding size of 300, a bidirectional LSTM and Decoder has a bidirectional LSTM and 2 dense layers. 

## Model Training
### Hyperparameters
Various values for hyperparameters were experimented. Embedding size, learning rate, epochs, GRU vs LSTM units, etc. Also 'relu' activation function was tried for LSTM instead of its default 'tanh'. Considering the training time, following values were chosen for the final model.

```
embedding_dim = 300
learning_rate = 2e-3
LSTM units = 256
LSTM activation = 'relu'
epochs = 25
```
## Model Outcome
The model achieved **over 98% accuracy** for both tratining and validation data, even with the relatively simple structure!

Here's an example of prediction and label comparison:
![image](https://github.com/sooolee/NLP-Machine-Translation_Eng-French/blob/main/outcome_example.png?raw=true)

