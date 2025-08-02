## 1. LLM - Large Language Model

- LLM is a neural network.
- Designed to understands and generate humans like text.
- **Large :** Previous models have only few parameters but LLM can have millions and billions of parameters.
- Specially designed to do NLP Task.
- **What is the secret sauce :** Transformer Architecture.

## 2. Stages of Machine Learning

1. Pretraining(foundational model)
2. Fine Tuning.

## 3. Pretraining + Fine tuning

- Collect and get the data, this datasets are from books, from Internet,wikipedia and research paper.Mostly this are unlabelled text[raw text].
- Train the LLM using this unlabelled datasets, this is called pre-training(foundational course).Each words will be considered as token.For training the LLM we need larger gpu.
- Once you pre-trained the LLM, we need to fine tune the LLM for your domain purpose doa a specific task, for finetuning it you need labelled datasets.After the trained pre-training LLM you need to further train on labelled datasets.
- Two types of finetuning : **Instruction finetuning and fine tuning for classification task**.
- **Instruction finetuning :** Instruction answers paired on labelled datasets.
- **Finetuning for classification task :** Labelled datasets consists of text and associated labels.(Spam / Not spam).

## 4. Transformers.

- Original transformer development is for machine translations like english to german or french.
- **Input :** This is an example.
- **Input the data and pre-processing :** Preprocessing remove the unwanted data and break the sentence into words, each words will be considered as token. for each tokern a token id is generated with random number.
- **Encoder :** Pass the data to the encoder.
- **Convert Embedding :** Add the vector embedding to the token.Vector embedding gives the semantic difference to each word.E.g : Human - King, Woemen, Men. and Fruits - Apple, Mango, Orange.
- **Decoder :** Decorder will receive the predicted translated word for each word, decorder will receive this as a input and decorder will also recive the the vector embedding.
- **Output :** Generates the translated text one word at a time and format as a sentence.


## 5. Encoder and Decoder

- **Encoder :** Converts a text into a vector embedding.
- **Decoder :** Generate output text from the vector embedding.

## 6. Self Attention Mechanism 

- Allow models to weight the importance of different words relative to each other.
- Long range dependencies.
- **Predicting the next word :** Self attention mechanism will tell which word you need to give more importance to predicate the next work.
- Calculate the attention score to tell which word we need to give more importance for predicting the next word.

## 7. GPT - Generate Pretrained Transformer.
