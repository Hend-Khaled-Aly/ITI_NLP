
## Understanding Recurrent Neural Networks (RNNs)

Recurrent Neural Networks (RNNs) are a specialized type of neural network designed for processing data with sequential dependencies. They are particularly suited for tasks involving time series or language, where the order of data points is important.

---

### 🧠 How RNNs Differ from Traditional Neural Networks

RNNs diverge from conventional feedforward neural networks in several important ways:

* **Flexible Sequence Lengths:** Unlike standard networks that require fixed-size inputs and outputs, RNNs can work with sequences of varying lengths.
* **Sequential Memory:** RNNs use a hidden state that is updated at each time step, enabling the network to "remember" prior inputs and capture temporal patterns or context across a sequence.

---

### 🔄 RNN Structure and Time Unfolding

An RNN processes input one step at a time, using the same set of weights across all time steps. When visualized, this is often shown as the network being “unfolded” through time, revealing multiple layers that all share parameters.

While this recurrent structure is powerful for sequence modeling, it also introduces two key challenges during training:

---

### ⚠️ Challenges in Training RNNs

* **Vanishing Gradients:** In long sequences, gradients can diminish to near-zero values, making it hard for the network to learn dependencies that span many steps.
* **Exploding Gradients:** In contrast, gradients can sometimes grow excessively, leading to numerical instability and making the training process erratic.

Both problems arise due to the repeated application of the same weights through time, which amplifies or diminishes gradient signals during backpropagation.

---

### 🔁 Common RNN Variants Based on Input/Output

RNNs can be adapted to various input-output configurations:

| Type                         | Description                                     | Example Use Case         |
| ---------------------------- | ----------------------------------------------- | ------------------------ |
| One-to-One                   | Single input to single output                   | Image classification     |
| One-to-Many                  | Single input leading to a sequence              | Image captioning         |
| Many-to-One                  | Sequence input resulting in one output          | Sentiment analysis       |
| Many-to-Many (same length)   | Input and output sequences of same size         | Named Entity Recognition |
| Many-to-Many (varied length) | Input and output sequences of different lengths | Machine translation      |

---

### 🔐 Introduction to LSTM Networks

To address the limitations of standard RNNs, particularly the vanishing gradient problem, Long Short-Term Memory (LSTM) networks were developed. LSTMs incorporate special components called **gates**—namely, input, forget, and output gates—which help regulate the flow of information, enabling the model to better maintain and learn long-term dependencies in sequences.
