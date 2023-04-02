# Machine Translation: English to French

This project is to build an end-to-end machine translation pipeline that takes English text and retuns French translation. The model is built from scratch based on Encoder-Decoder and RNN structures. 

## Dataset
LLMs are typically trained on large corpus (at least 100M+ tokens). To train the model in a reasonalbe time and limited resources, a dataset that contains a small vocabulary has been chosen for this project.

The [dataset](https://github.com/sooolee/machine_translation_eng_to_french/tree/main/data) used for this project have 138k paris of English and French sentences. The maximum length (number of tokens) is 15 for English and 21 for French.

The dataset was split to 'train' and 'test' datasets with a 80:20 ratio. The train dataset was further split to 'train' and 'validation' sets with a 90:10 ratio during training. 

## Data Preprocessing
The data were already lowercased, but needed further preprocessing. The setences were tokenized (into word ids) and padded using `keras` `Tokenizer` and `pad_sequences`.

## Model Architecture
Encoder has a embedding layer with a embedding size of 300, bidirectional LSTM with 25