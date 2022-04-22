# NLP-summarization-of-French-written-documents


This project will focus on the text summarization task applied to the summarization of French written documents. Formally, our goal will be to implement and compare different approaches to produce a summary from a given text. We adopted extractive (TextRank algorithm) and abstractive (mainly BARTHez model), trained and tested on OrangeSum dataset, with both quantitative (using ROUGE metric) and qualitative experiments.


Our project focuses on the text summarization task applied to the summarization of French written documents.

Formally, our goal was to implement and compare different approaches to produce a summary from a given text. We implemented the more "naive" methods to adress this task, which are called "Extractive Approach" and are unsupervised. We implemented our version of the TextRank algorithm : the idea is to choose some embeddings for the sentences of a text (FastText for instance), and compute a similarity matrix using cosine similarity to form a summary by extracting the most revelant sentences of our text. Then, we studied the more advanced "Abstractive approaches", where the idea is to leverage deep learning models within an Encoder-Decoder structure, using LSTM or the Attention Mechanism of Transformers, to build supervised generative models that will generate new sentences to create a summary. For this approach, we started from a pre-trained BARTHez model.

Concerning the dataset, we mainly trained and tested our models on OrangeSum, a dataset providing news articles with their summaries in French. As we are studying French written texts, we will use appropriated language models specific to French, such as the French version of FastText, or BARTHez. Moreover, to quantitatively evaluate the performance of our generated summaries, we used the ROUGE metric, which was specifically designed for this task and used in the litterature. We also made several qualitative experiments, by challenging our models on different type of texts, which can be found in the attached notebook.
