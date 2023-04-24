# NLP-test-task
The goal to create a machine learning model that will help the public procurement department extract the necessary text fragment from the document in order to form the application form. The model takes text and request as input and returns the desired piece of text and its location in the source text.

# How to run
Open task.ipynb file and run it in Jupyter Notebook or Google Colab 

# Approach 
The [SentenceTransformers](https://github.com/UKPLab/sentence-transformers) library and [SBERT](https://arxiv.org/pdf/1908.10084.pdf) model are used to solve the problem. Problem solution pipeline:
1) Parse and tokenize raw text with regular expressions and NLTK
2) Create embeddings of sentences with SBERT model
3) Evaluate cosine similarity between vectors and find the most similar vector
4) Compare prediction and answer from dataset and tune model
5) Fit model (repeat steps 1-4) and create predictions for test data
