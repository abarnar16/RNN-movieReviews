### RNN for Movie Review Sentiment Analysis

---

### Introduction

This project implements a Recurrent Neural Network (RNN) to perform sentiment analysis on a dataset of movie reviews. The goal is to classify reviews as "good" or "bad" based on their textual content. The project addresses challenges such as multilingual reviews and class imbalance.

---

### Project Files

* `RNN_reviews.ipynb`: A Jupyter Notebook containing the full source code for the project, including data loading, preprocessing, model architecture, training, and evaluation.
* `RNN_reviews_Slides.pdf`: A presentation slide deck summarizing the project's methodology, results, and key visualizations.
* `RNN_best_weights.h5`: The saved weights of the best-performing RNN model after training.
* `RNN_reviews.html`: A static HTML version of the Jupyter Notebook.

---

### Dataset & Preprocessing

The project uses a dataset of 527 movie reviews. Initial data exploration revealed several issues that were addressed during preprocessing:
* The dataset contained reviews in multiple languages, primarily English and Malay, with a few in Chinese and Japanese. To handle this, all non-English reviews were translated to English to ensure consistent input for the model.
* The `Score` column had two missing values, while another column was completely empty and was subsequently dropped.
* The reviews were preprocessed using techniques such as stop-word removal, lemmatization, and tokenization to prepare the text for the RNN model.

---

### Model Architecture: Recurrent Neural Network (RNN)

A **Recurrent Neural Network (RNN)** with a Bidirectional LSTM layer was chosen for this task. The model's architecture includes:
* **Embedding Layer**: Converts words into dense vector representations.
* **Bidirectional LSTM Layer**: Processes the sequence of words in both forward and backward directions, capturing more context from the review text.
* **Dense Layers**: A stack of fully-connected layers for final classification.
* **Dropout & Batch Normalization**: Regularization techniques to prevent overfitting and stabilize training.

---

### Evaluation and Results

The model was evaluated using standard metrics to assess its performance, particularly on the imbalanced dataset:
* **Final Accuracy**: The model achieved an overall accuracy of 92% on the test set.
* **Confusion Matrix**: The model accurately classified 43 out of 46 "Good" reviews and 13 out of 15 "Bad" reviews, with only five total misclassifications.
* **Classification Report**: The "Good" class achieved a precision of 0.96 and an F1-score of 0.95, while the "Bad" class, despite being the minority, still performed well with a precision of 0.81 and a recall of 0.87.
* **ROC Curve**: The Receiver Operating Characteristic (ROC) curve rises steeply, with an Area Under the Curve (AUC) of 0.98, indicating excellent separability between the two sentiment classes.

These results confirm the model's robustness and its ability to handle both majority and minority classes effectively due to the preprocessing steps and the chosen architecture.
