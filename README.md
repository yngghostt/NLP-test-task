# NLP-test-task
The goal to create a machine learning model that will help the public procurement department extract the necessary text fragment from the document in order to form the application form. The model takes text and request as input and returns the desired piece of text and its location in the source text.

## How to run
Open task.ipynb file and run it in Jupyter Notebook or Google Colab 

## Approach 
The [SentenceTransformers](https://github.com/UKPLab/sentence-transformers) library and [SBERT](https://arxiv.org/pdf/1908.10084.pdf) model are used to solve the problem. Problem solution pipeline:
1) Parse and tokenize raw text with regular expressions and NLTK
2) Create embeddings of sentences with SBERT model
3) Evaluate cosine similarity between vectors and find the most similar vector
4) Compare prediction and answer from dataset and tune model
5) Fit model (repeat steps 1-4) and create predictions for test data

## Text preprocessing

The desired fragment is a sentence from the text. In such cases, it is required to split the text into a sentence. Some parts of the text do not contain punctuation marks. Regular expressions and the NLTK library are used to solve this problem. In the future, punctuation model can be created for better parsing raw text.

## Creating Embeddings

The SBERT model is used to create sentence embeddings. The model get sentences as input and returns sentence embeddings.

## Tuning models

The model is tuned based on the predictiobs. Cosine similarity metrics is used for evaluating similarity of embedings. The most likely prediction have to be the most similar with request. To determine the similarity, a cosine measure is used, to determine the similarity of the answer and the forecast - the Jaro square ratio (because you need to understand how many characters matched and not severely penalize for a miss of several characters)
