# Demo notebooks using Pinecone vector database and Sentence Transformers in spanish

This repository contains some Jupyter notebooks, experimenting with Pinecone vector database and Sentence Transformers. We are working with text data in spanish, using Sentence Transformers to produce embeddings and then we create an index in Pinecone to store the embeddings. The goal is to build a question answering model, the questions will be used to retrieve the more acceptable context passages from our embeddings index and finally we create a QA model that receives the question and the context and return the answer. But we are really interested in manage the index and work with it, we do not search for the better QA model, that is a different task.

Steps in the notebooks:
- Data download and preprocessing
- Select and download a sentence transformer model to create the embeddings
- Select and download the retriever, the model thta generates the answers
- Connect and create a Pinecone index with the rigths parameters
- Select the metadata we need to store, chunck the texts and upload them to the index
- Given a question, query the vector index to retrieve the context
- Format the prompt or input to the question answering model 
- Infere the output using the retriever model

We are not interested in the model architecture, we are not searching the "best model" what we want to show here is how to deal and manage a Pinecone index and the embeddings. We create some demo and basic notebooks to show how to work 


**This repository is still In progress**

## The dataset

We will be using the dataset [SQUAD ES](https://huggingface.co/datasets/squad_es).

This is an automatic translation of the Stanford Question Answering Dataset (SQuAD) v2 into Spanish. 


## Problem description
**In progress**
Our goal is to show how easy is to work with Pinecone indexes where you can store your text embeddings, query them using different distance metrics and then you can extract context information to solve your task. for this purpose, we create sentence transformers model to generate the embeddings and question aswering models to extract the appropiate response.

**Note:** This is still in progress and some models maybe need some more experimentation to return good answers.

## The model
We use a [Multilingual Sentence Transformer](sentence-transformers/distiluse-base-multilingual-cased-v1) model to create the embeddings, based on distilbert model.

This is a sentence-transformers model: It maps sentences & paragraphs to a 512 dimensional dense vector space and can be used for tasks like clustering or semantic search.

For extractive question answering we use a [Deberta based model](timpal0l/mdeberta-v3-base-squad2)
It is a fine tunied model in our SQUAD database.

Abstractive question answering is a much complex problem, we finally use a [T5 small variant](mrm8488/spanish-t5-small-sqac-for-qa) from Manu Romero. It is a spanish-T5-small fine-tuned on SQAC for Q&A downstream task.

## Content
** Still In progress**

- extractive question answering notebook: In this notebook we generate the answers in an extractive approach.
- abstractive question answering notebook: In this notebook we try to generate the answers in an abstractive approach.

## Contributing
If you find some bug or typo, please let me know or fixit and push it to be analyzed. 

## License

These notebooks are under a public GNU License version 3.