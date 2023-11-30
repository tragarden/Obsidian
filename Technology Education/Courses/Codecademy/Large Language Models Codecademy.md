# Large Language Models

Large Language Models ( #LLM) are systems of Artificial Intelligence ( #AI) that assess large amounts of text based data, learning the patterns of language and applying them to algorithms. These can be used for translation purposes, summarization, and question/response interactions.

These LLM models are static and once their database is assigned, it remains that way unless managed by an administrator. This means that once an LLM is created, it is limited to the set of data it is provided with upon it's creation.

### Early Models

#### ELIZA

#ELIZA was the first digital chat interface created in 1966 by #MIT thanks to Joseph Weizenbaum. This project mimicked humans so well that people believed they were really communicating with a person - this became known as the ELIZA effect. 

#### Turing

Alan #Turing wrote the paper "Computing Machinery and Intelligence" in the 1950's which lead to the #Turing Test, which asks: "Can a machine successfully imitate human behavior so that it might dupe a human?"

### Natural Language Processing

Natural Language Processing ( #NLP) is when AI uses machine learning to analyze human input to understand the intent, meaning, and sentiment of the input. Sentiment analysis, proper noun recognition, and speech recognition are all facets of NLP technology.

NLP is used to create what is known as a Language Model - a system of algorithms that uses analysis from NLP data to decide a progression of words.

#Autoregressive is a term used to describe when statistical models use past values to determine word predictions for a current situation. 

#Count-based models use a counter method to identify how many times an individual word occurs within the given data. This is then formulaically paired with the possible next word, calculating the probability that a given combination will occur. This given combination and calculated probability is paired with the next potential word prediction to see what the next most likely word would be.

Count-based models are limited by certain situations where the AI model is unable to draw generalizations about a given user submission. If the user would submit a query that has never been seen by the model - meaning no where in the data does this specific combination of words occur - the model would assume 0% probability for this event!

To move beyond the limits of count-based models, semantical interpretation of words was introduced to the models. This allowed for word associations that count-based models do not consider. In the case of "does a shark eat fish?" - this exact order of words may have never happened in the data. A concept that may be within the data however, is the idea that a predator chases prey. This semantic application of the word 'prey' to a fish and 'predator' to a shark would allow the model to begin generalizing about ideas like this.

Word Embeddings are the mathematical object that allows us to apply semantical thinking to individual words and objects in the model.

Neural Networks are used to generate word embeddings and semantic thinking within a model.

#Generative is how we say that the model is able generate content.

#Generalizability is how we say that the model is able to generalize.

#Compression is used to lessen the amount of data and facilitate #generalization by reducing the amount of parameters analyzed. The count table is thusly approximated instead of painstakingly memorized and reviewed for each query. These lessened lists of parameters are also known as model weights. These approximated weights allow the model to apply a non-zero probability to text that does not exist within the model AND a zero probability to existing text in the data.

Generalization means applying non-zero probabilities to text that does not exist within the model.

Compression means applying some zero probabilities to text that actually exists within the model. The use of compression ensures that data will be lost.

A #Neural #Network is a machine learning model that is based on the pathing and communication styles of a human brain. These models were developed after breakthroughs in 1950's neuroscience. Programmers then applied these concepts to computing, drawing parallels from the background processes of the human subconscious to the background processes of a computer.

Frank Rosenblatt made the "Perceptron" in 1958 - a program that aimed to stimulate the smallest individual information processing unit possible - the neuron.

Machine learning has been around since the 1950's, but struggled to gain popularity until the 2000's when data became more available and abundant.

#Convolutional Neural Networks ( #CNN) is a type of NN used for analyzing image data.

#Recurrent Neural Networks ( #RNN)  is a type of NN used for sequential data like language processing, translation, and speech recognition. 

A #Transformer is an architecture type that performs exceptionally when applied to language-based tasks.

#Emergence is a term used to describe a sudden change in the performance of an LLM where the model can draw enough generalizations to start adding stylistic flair and humor to it's responses.

A #Hallucination refers to flaws in generalization that produce non-existent or erroneous content that does not seem to fit reality.

#Temperature refers to the relational probability between a dataset and a query. Low temperature would mean that the probability distribution narrows, encouraging responses that are more probable. High temperature would increase the likelihood that the model will return a less probable outcome.