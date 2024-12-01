# Sentiment Analysis on IMDB Movie Reviews with LSTM

This project demonstrates a sentiment analysis task using a Long Short-Term Memory (LSTM) neural network to classify IMDB movie reviews as positive or negative. The dataset is preprocessed and modeled using Keras.

Project Overview
1. Dataset
Source: IMDB movie reviews dataset from tensorflow.keras.datasets.
Content:
Reviews represented as sequences of word indices (based on the most frequent 20,000 words in the dataset).
Labels:
Positive sentiment = 1.
Negative sentiment = 0.
Splits:
Training set: 25,000 reviews.
Test set: 25,000 reviews.
Workflow
1. Data Preprocessing
Steps:
Load the dataset with imdb.load_data(num_words=20000):
Keeps only the 20,000 most frequent words.
Discards less frequent words to simplify training.
Pad the sequences to ensure uniform length:
Maximum sequence length = 80 words.
Shorter sequences are padded with zeros.
2. Model Design
Built using Keras Sequential API.
Architecture:
Embedding Layer:
Maps the 20,000 words into a dense vector space of size 128.
LSTM Layer:
128 units.
Regularization:
Dropout rate: 0.2.
Recurrent dropout rate: 0.2.
Dense Layer:
Single neuron with a Sigmoid activation for binary classification.
3. Compilation
Loss function: binary_crossentropy (suitable for binary classification).
Optimizer: Adam.
Metrics: accuracy.
4. Model Training
Parameters:
Batch size: 32.
Epochs: 15.
Validation set: Uses the test data (x_test, y_test) for validation.
5. Evaluation
The model is evaluated on the test set to calculate:
Test Score: Binary cross-entropy loss.
Test Accuracy: Proportion of correctly classified reviews.
