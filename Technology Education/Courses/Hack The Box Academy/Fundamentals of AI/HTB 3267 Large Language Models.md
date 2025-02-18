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

Encoders and Decoders - an encoder is a transformer component that processes input text to capture meaning and then decoders generate output based on output from encoders.

Self-Attention Mechanism - calculates attention scores between words so the model can understand long-range dependencies.

Training - unsupervised learning  is used to evaluate incredibly large amounts of data before parameters are adjusted to minimize prediction errors using gradient descent.

#### Transformer Architecture

Transformer Architecture is a revolutionary neural network design that changed the way language was processed by AI. They process sentences in parallel leading to more efficient and fast learning.

The self-attention mechanism is the primary way this is achieved. This allows the model to weight the importance of words within a sentence while it is being processed.

#### Tokenization

Tokenization breaks sentences into smaller sub-components like words, subwords, or characters  which are known as tokens.

#### Embeddings

After text is tokenized the tokens are converted into numerical representations known as embeddings. These capture semantic meanings of words in order to represent them as points in high-dimensional spaces. Words with similar meanings are embedded closer together in the high-dimensional spaces.

#### Encoding and Decoding

Encoders process input in order to capture it's meaning and relationships. 

Decoders use the output of encoders to generate output text.

They work together to gain understanding of human-like texts.

#### Self-Attention

Self-Attention allows transformers to capture long-range dependencies within text by calculating attention scores between each pair of words within a sentence. The score indicates how much each word should pay attention to other words around it.

### Related:
- [Hack The Box Academy](https://academy.hackthebox.com/ "Hack The Box Academy Home page")
- [HTB Large Language Models](https://academy.hackthebox.com/module/290/section/3267 "HTB Large Language Models")