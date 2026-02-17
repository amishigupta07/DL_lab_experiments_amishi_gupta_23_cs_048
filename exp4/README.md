Text Generation using RNN and LSTM

Objective
The objective of this experiment is to implement and compare text generation models using:
Recurrent Neural Networks (RNN)
Long Short-Term Memory Networks (LSTM)

Two word representation techniques are evaluated:
One-Hot Encoding
Trainable Word Embeddings

Each encoding method is implemented using both RNN and LSTM architectures. The models are trained on a dataset of 100 poems to perform next-word prediction.

Dataset
The dataset consists of 100 poems stored in CSV format. All poems are combined into a single corpus for training.
The task is formulated as a next word prediction problem where the model predicts the next word given a sequence of previous words.

Preprocessing
The following preprocessing steps were performed:
Converted all text to lowercase
Removed punctuation
Replaced newline characters with a special <eol> token
Tokenized text into words
Created vocabulary from unique tokens
Generated word-to-index and index-to-word mappings
Created input sequences of length 5 for training

Model Architectures
RNN Model
Input: Word sequence
Hidden size: 128
Output layer: Fully connected layer
Loss function: CrossEntropyLoss
Optimizer: Adam
LSTM Model
Similar structure to RNN
Includes memory cell and gating mechanisms
Better at capturing long-term dependencies

Part 1: One-Hot Encoding
In this approach:
Each word is represented as a sparse vector of size equal to the vocabulary.
Only one element in the vector is set to 1, others are 0.
Models implemented:
RNN with One-Hot Encoding
LSTM with One-Hot Encoding
Observations
High dimensional representation
Slower training
Higher loss values
More repetition in generated text

Part 2: Trainable Word Embeddings
In this approach:
Words are converted into integer indices.
An embedding layer learns dense vector representations.
Embeddings are trained along with the model.
Models implemented:
RNN with Embedding
LSTM with Embedding
Observations
Faster convergence
Lower loss
Better semantic understanding
More coherent generated text

Results Comparison
RNN + One-Hot -	Slow,	High Loss, Repetitive Text
LSTM + One-Hot -	Moderate,	Medium Loss,	Improved Text
RNN + Embedding -	Faster,	Lower Loss,	Meaningful Text
LSTM + Embedding -	Fastest,	Lowest Loss,	Most coherent Text

Sample Generated Text
Prompt:
the night was
RNN One-Hot:
the night was the house and the body or the young men and the sea...
LSTM One-Hot:
the night was he was his eyes <eol> the little systems...
RNN + Embedding:
the night was the <eol> texan ranch <eol> the cleanhaired yankee...
LSTM + Embedding:
the night was the same <eol> i am not a minute longer...

Conclusion
The experiment demonstrates that:
LSTM performs better than vanilla RNN.
Trainable word embeddings outperform one-hot encoding.
The best performing model is LSTM with trainable embeddings.
Word representation significantly affects model performance and text quality.
