# Large Language Models

Large Language Models (LLM) are artificial intelligence models that generate human-like text responses, focusing specifically on patterns and relationships in language. These models are used for translation, summarization, and creative writing.

Transformers are a deep learning architecture that focuses on processing sequential data with the capability of capturing long-range dependencies between words. It utilizes self-attention, where models have the ability to asses the importance of different words within sentences.

LLMs receive very large volumes of text-based data while parameters are adjusted to minimize the difference between predictions and input texts. This process is very taxing on hardware and often relies on GPUs and TPUs.  

LLMs often possess the following three characteristics:

- Very Large Scale - these models often contain billions or trillions of parameters in order to capture the nuance of human languages.
- Few-Shot Learning - tasks are performed using very few examples, while other types of machine learning models require extremely large sets of labeled data.
- Contextual Understanding - the context of a conversation or text is understood by the model and used to generate more realistic responses.

#### Key Components

Transformer Architecture - a neural network that processes sentences in parallel for fast and efficient computations.

Tokenization - conversion of text into smaller units known as tokens, which are often words, subwords, or characters.

Embeddings - numeric representations of tokens used to capture semantic meaning. Similar words have embeddings closer together in a high-dimensional space.

