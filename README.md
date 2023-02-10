ANLP-Assignment 1
In this assignment we are required to reproduce results from base NLP research paper.

In this assignment1 I used BERT and BOW to make it easier for me when working on assignment 2.

This project has 4 Jupyter notebooks. Please note that you need to open them in order to avoid any errors:

The preferred order is as follows:

1- bert

2- cnn

3- lstm

4- traditional_ml

hint: keep bert running all time when opening the other notebooks since it has the main coding of the data train. It may slow down your PC. however, if it get stopped at the middle of processing, errors will occur.

Thank you for your patience :D

# Datasets

**Summary Table**

|     Dataset    | Year |  Content  |     Size     | Emotion categories | Balanced |
| :--------------: | :--: | :-------: | ------------ | ------------------ | :-------: |
|dailydialog| 2017 | dialogues |102k sentences|neutral, joy, surprise, sadness, anger, disgust, fear| No |
|emotion-stimulus|2015|dialogues|2.5k sentences|sadness, joy, anger, fear, surprise, disgust| No |
|isear|1990|emotional situations|7.5k sentences|joy, fear, anger, sadness, disgust, shame, guilt| Yes |

links: [dailydialog](http://yanran.li/dailydialog.html), [emotion-stimulus](http://www.site.uottawa.ca/~diana/resources/emotion_stimulus_data), [isear](http://www.affective-sciences.org/index.php/download_file/view/395/296/)


## Combined dataset

Dataset was combined from dailydialog, isear, and emotion-stimulus to create a balanced dataset with 5 labels: joy, sad, anger, fear, and neutral. The texts mainly consist of short messages and dialog utterances.

# Experiments

### Traditional Machine Learning:
* Data preprocessing: noise and punctuation removal, tokenization, stemming
* Text Representation: TF-IDF
* Classifiers: Naive Bayes, Random Forrest, Logistic Regrassion, SVM

| Approach            | F1-Score |
| :------------------ | :------: |
| Naive Bayes         | 0.6702   |
| Random Forrest      | 0.6372   |
| Logistic Regression | 0.6935   | 
| SVM                 | 0.7271   | 

### Neural Networks
* Data preprocessing: noise and punctuation removal, tokenization
* Word Embeddings: pretrained 300 dimensional word2vec ([link](https://fasttext.cc/docs/en/english-vectors.html))
* Deep Network: LSTM, biLSTM, CNN 

| Approach            | F1-Score |
| :------------------ | :------: |
| LSTM + w2v_wiki     | 0.7395   |
| biLSTM + w2v_wiki   | 0.7414   |
| CNN + w2v_wiki      | 0.7580   |

### Transfer learning with BERT
Finetuning BERT for text classification

| Approach            | F1-Score |
| :------------------ | :------: |
| finetuned BERT      | 0.8320   |
