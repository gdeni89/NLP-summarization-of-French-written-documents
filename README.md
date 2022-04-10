# NLP-summarization-of-French-written-documents
Our goal will be to implement and compare different approaches to produce a summary from a given text. As a "baseline", we will implement the more "naive" method to adress this task, which is called "Extractive Approach" and is unsupervised : the idea is to choose some embeddings for the sentences of a text, and compute a similarity matrix to form a summary by extracting the most revelant sentences of our text. Then, we will study the more advanced "Abstractive approach", where the idea is to leverage deep learning models (Encoder-Decoder or Attention Mechanism of Transformers), to build supervised generative models that will generate new sentences to create a summary.

NLP Project
Proposal :
Instructions : Provide details on your project . It should be a paragraph describing your project, what datasets you will be using, what modelling techniques and what evaluation you will be doing
Possible Datasets in French :

OrangeSum : dataset that was proposed for text summarization but in French (which is less studied in litterature than English) : articles with summaries, already grouped in categories (political, environment, ...) so we will be able to easily compare the perf of our model on different "subjects"

+ this dataset was proposed together with "BARThez", a seq2seq model proposed specifically for French and which is said to be more efficient than BERT-based models for French, above all for generative tasks (associated article)

CASS (summaries of "procès en cours de cassation", maybe less interesting and diverse than news articles)

MLSum & XL-Sum : datasets proposed by HuggingFace and composed of articles with abstracts on different languages, I guess we can concentrate on French subcorpus. It was originally proposed for multilingual text summarization (see article for XLSum or article for MLSum)

WikiLingual : article and summary pairs of Wikipedia articles in different languages

Possible Language models for French :

CamemBERT
FlauBERT
Deepfrench : pre-trained on Wikipedia corpuses, principally proposed for classification tasks
BARThez
Description of the task and approach(es) :
The idea of text summarization is to produce a summary of a text (or corpus of text if we want to extend it). There is two main possible approches :

1. Extractive Approach :

The first (maybe simplest) approach is to form a summary by selecting some sentences of the text (without modifying it at all). To do so, we need to find a way to "score" the sentences of the document to extract only the most revelant ones.

An example of algorithm that we can try to implement is the TextRank algorithm, which is unsupervised and with few DL. The idea is to compute a similarity matrix between the sentences of our document, which can be done by computing similarities between embeddings of the sentences (with Seq2Vec for instance).

Example of tuto really well detailed for Extractive Approach

2. Abstractive Approach :

A more advanced approach is to generate the summary, that is to say to produce a summary with sentences that we have generated and do not exist in the document to summarize.

For this task, we may use DL, with models such as Transformers with Attention Mechanism (or Encoder-Decoder to start but it's more limited and should lead to worse perf than Transformers).

Example of tuto really well detailed for Abstractive Approach

⇒ Proposal :

Our project will focus on the text summarization task applied to the summarization of French written documents. (We will not cover multi-lingual models and summarization of corpus of documents, which are possible extensions of this task).

Formally, our goal will be to implement and compare different approaches to produce a summary from a given text. As a "baseline", we will implement the more "naive" method to adress this task, which is called "Extractive Approach" and is unsupervised : the idea is to choose some embeddings for the sentences of a text, and compute a similarity matrix to form a summary by extracting the most revelant sentences of our text. Then, we will study the more advanced "Abstractive approach", where the idea is to leverage deep learning models (Encoder-Decoder or Attention Mechanism of Transformers), to build supervised generative models that will generate new sentences to create a summary.

Concerning the datasets, we would like to train our models on news articles with their summaries in French, which can be found in datasets such as MLSum, XLSum or OrangeSum. As we are studying French written texts, we will use and compare some language models specific to French, such as FlauBERT, CamemBERT, DeepFrench or BARTHez. Moreover, to evaluate the performance of our generated summaries, we will use the ROUGE metric, which was specifically designed for this task and used in the litterature. We may also do some experiments by challenging our models on different type of texts, such as the ones available in WikiLingual or CASS.
