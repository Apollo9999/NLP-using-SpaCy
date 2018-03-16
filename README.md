# NLP-using-SpaCy

NLP using SpaCy python library

About spaCy and Installation:

Spacy is written in cython language, (C extension of Python designed to give C like performance to the python program). Hence is a quite fast library. spaCy provides a concise API to access its methods and properties governed by trained machine (and deep) learning models.

installation:

conda install -c conda-forge spacy
python -m spacy download en_core_web_sm-2.0.0 --direct

SpaCy Pipeline and Properties:

Implementation of spacy and access to different properties is initiated by creating pipelines. A pipeline is created by loading the models. There are different type of models provided in the package which contains the information about language – vocabularies, trained vectors, syntaxes and entities.

We will load the default model which is english-core-web.

import spacy 
nlp = spacy.load(“en”)

create an object nlp
The object “nlp” is used to create documents, access linguistic annotations and different nlp properties. Let’s create a document by loading a text data in our pipeline

document = unicode(open(filename).read().decode('utf8')) 
document = nlp(document)

The document is now part of spacy.english model’s class and is associated with a number of properties. 

Tokenization:

Every spaCy document is tokenized into sentences and further into tokens which can be accessed by iterating the document

Part of Speech Tagging:

Part-of-speech tags are the properties of the word that are defined by the usage of the word in the grammatically correct sentence. These tags can be used as the text features in information filtering, statistical models, and rule based parsing.

Entity Detection:

Spacy consists of a fast entity recognition model which is capable of identifying entitiy phrases from the document. Entities can be of different types, such as – person, location, organization, dates, numerals, etc. These entities can be accessed through “.ents” property.

Dependency Parsing:

One of the most powerful feature of spacy is the extremely fast and accurate syntactic dependency parser which can be accessed via lightweight API. The parser can also be used for sentence boundary detection and phrase chunking. The relations can be accessed by the properties “.children” , “.root”, “.ancestor” etc.

Noun Phrases:

Dependency trees can also be used to generate noun phrases

Word to Vectors Integration:

Spacy also provides inbuilt integration of dense, real valued vectors representing distributional similarity information. It uses GloVe vectors to generate vectors. GloVe is an unsupervised learning algorithm for obtaining vector representations for words.

Machine Learning with text using Spacy
Integrating spacy in machine learning model is pretty easy and straightforward. Let’s build a custom text classifier using sklearn. I  created a sklearn pipeline with following components: cleaner, tokenizer, vectorizer, classifier. For tokenizer and vectorizer I built custom modules using spacy.
