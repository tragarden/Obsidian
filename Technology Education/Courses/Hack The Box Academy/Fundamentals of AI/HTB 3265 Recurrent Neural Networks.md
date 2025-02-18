# Recurrent Neural Networks

Recurrent Neural Networks (RNN) are designed to handle sequential data where order of the data points matters. They maintain a memory of past inputs in order to capture temporal dependencies and patterns within these sequences. These networks are strongly suited to natural language processing, speech recognition, and time series analysis.

The recurrent connections in these networks create loops within the network that allow the information to persist and pass on to a next step. This works the same way as auto-predicted text on your phone - a new word is always predicted but the more of a sentence you write, the more specific the next prediction would be.

#### Vanishing Gradient

The Vanishing Gradient Problem is a challenge that all RNNs face where during training, backpropagation through time (BPTT) is used to update values for weights. What occurs is that the gradients produced by loss functions get propagated back through the iterative process. When this occurs, they can become smaller and smaller until they actually disappear altogether. This prevents the network from learning long-term consequences and rewards.

#### Long-Short-Term Memory

Long-Short-Term Memory (LSTM) is a gating mechanism that incorporates memory cells for storing information over long periods of time.

There are three gates that allow this to happen:

- Input - regulates influx of new information into the memory cell.
- Forget - controls the amount of information that is retained or discarded.
- Output - determines what the memory cell will next produce.

This allows the LSTM to selectively remember or forget any information, thus mitigating the amount of information that is forgotten and alleviating the vanishing gradient problem.

#### Gated Recurrent Unit

Gated Recurrent Units (GRU) are an alternative to using LSTMs and only use two gates. They are more computationally efficient as they are less complex.

The two gates used are below:

- Update - how much of the previous hidden state is retained.
- Reset - how much of the previous hidden state is combined with current input.

#### Bidirectional RNN

While most RNNs are designed to move in a forward direction, there exist models that can simultaneously move backwards as well. This means they capture data from the past and present simultaneously.

### Related:
- [Hack The Box Academy](https://academy.hackthebox.com/ "Hack The Box Academy Home page")
- [HTB Recurrent Neural Networks](https://academy.hackthebox.com/module/290/section/3265 "HTB Recurrent Neural Networks")