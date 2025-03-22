# Sentiment-analysis-using-LSTM


# Dataset Overview

The dataset used for this sentiment analysis task consists of tweets related to various airlines. Each tweet is labeled with one of three sentiment categories: negative, neutral, or positive. The dataset includes key text features, such as the length of tweets, word distribution, and class imbalances, where negative sentiments are more prevalent than positive or neutral sentiments. The dataset required preprocessing, including tokenization, vocabulary creation, sequence padding, and conversion into numerical representations for model training.

# Baseline and Improved LSTM Architectures

The baseline LSTM model consists of an embedding layer, followed by three stacked LSTM layers, dropout regularization, and a fully connected output layer with softmax activation. It processes input sequences in a unidirectional manner, meaning it only learns from past context.

The improved LSTM model incorporates several enhancements:

Bidirectional LSTM: Allows the model to learn dependencies from both past and future contexts.
Attention Mechanism: Helps the model focus on the most relevant words in each tweet.
Higher Dropout Rate: Helps mitigate overfitting by randomly deactivating neurons during training.
Stacked LSTM Layers: Increases model capacity for learning complex relationships.
GRU Alternative (Optional): Provides a computationally efficient alternative to LSTMs.
The improved model is designed to capture richer semantic information while reducing overfitting.

# Comparative Performance Analysis

The baseline LSTM achieved an accuracy of 79.81%, while the improved LSTM reached approximately 81-82% accuracy. The following observations highlight the differences:

Training and Validation Loss: The baseline model experienced overfitting after around five epochs, as indicated by increasing validation loss. The improved model, with higher dropout and bidirectional LSTM, showed a more stable validation loss trend.
Confusion Matrix Insights: Both models performed well in predicting negative sentiments, but the improved model had fewer misclassifications for neutral and positive classes. The attention mechanism helped the improved model distinguish these subtle differences more effectively.
Precision and Recall: The improved model demonstrated higher precision and recall across all sentiment classes, indicating a better generalization capability.
Despite these improvements, the gains in accuracy were relatively moderate, suggesting that external factors, such as data augmentation or pre-trained embeddings, could further enhance performance.

# Strengths and Limitations of LSTMs for Sentiment Analysis

Strengths
Handling Long Sequences: LSTMs are designed to capture dependencies across long text sequences, making them well-suited for analyzing tweets with complex sentiment structures.
Better Context Understanding: Unlike traditional models (e.g., logistic regression), LSTMs learn contextual relationships between words, improving sentiment classification accuracy.
Limitations
Computational Cost: Training LSTMs is computationally expensive due to sequential processing, which limits scalability for large datasets.
Hyperparameter Sensitivity: The performance of LSTMs heavily depends on careful tuning of learning rates, dropout rates, and the number of hidden layers.
Interpretability Issues: Unlike logistic regression or decision trees, LSTMs act as black-box models, making it difficult to explain why certain predictions were made.
While LSTMs are effective for sentiment analysis, more modern architectures like Transformers (BERT, GPT) provide state-of-the-art performance with better efficiency and interpretability.

Baseline accuracy - 79%

Improved LSTM accuracy - 80.2%

