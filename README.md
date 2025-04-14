# Emotion Detection for Airline Reviews

## Project Overview

Airlines frequently receive diverse reviews from passengers, spanning from negative feedback to positive evaluations. Recently, certain airlines have gained attention on social media due to complaints about uncomfortable seating. Manually sorting through these reviews is laborious and inefficient. The objective is to automate emotion recognition, categorizing reviews into relevant themes. This enables the extraction of actionable insights for airlines to enhance their services. By undertaking this project, I aimed to contribute to improving overall travel experiences.


For the model building and evaluation, I have followed the steps below to towards achieving my project goals.

## Tools & Libraries Used

- **Python**: Programming language used to implement the project.
- **Pandas**: For data manipulation and analysis.
- **NumPy**: For numerical operations and data handling.
- **Seaborn**: For data visualization (used for EDA on the **Book1.csv** dataset).
- **Matplotlib**: For generating visualizations such as histograms and bar plots.
- **NLTK**: Natural Language Toolkit, used for text processing (tokenization, stopword removal, stemming).
- **TensorFlow / Keras**: For building and training the deep learning model (LSTM-based neural network).
- **Scikit-learn**: For model evaluation and preprocessing (e.g., train-test split).

## Data Sources

- **Book1.csv**: This dataset contains text samples with corresponding emotion labels. This dataset is used for exploratory data analysis (EDA) and initial model training.
- **Book2.csv**:  This dataset is used for testing model.

- **Airline_review.csv**: This dataset contains reviews from passengers, and is used for emotion prediction after training the model.

## Steps Followed

### 1. Data Collection

- The data was sourced from two files: **Book1.csv** and **Airline_review.csv**.
    - **Book1.csv** contains a corpus of text with corresponding emotion labels. This dataset is used for EDA and initial model training.
    - **Airline_review.csv** contains reviews from passengers, which are used to test the model's emotion prediction capabilities.

### 2. Exploratory Data Analysis (EDA)

- **Book1.csv** was loaded and analyzed using Pandas.
- Iused **Seaborn** to visualize the distribution of emotion categories in the dataset.
  - **Bar plot** was used to show the count of each emotion in the dataset. The emotion categories include `joy`, `sadness`, `anger`, `fear`, `love`, and `surprise`.
  
- A **histogram** was created to show the distribution of text lengths in **Book1.csv**, revealing that most texts fall between lengths of 20 to 150 characters.

### 3. Text Preprocessing

- **Tokenization**: The text was tokenized using Keras' **Tokenizer** to convert words into sequences of tokens.
- **Stopwords Removal**: Using NLTK, I removed common words (stopwords) that don't contribute to the sentiment analysis.
- **Stemming**: Applied **PorterStemmer** from NLTK to reduce words to their root forms (e.g., "feel" and "feeling" both reduced to "feel").
- **Padding**: To ensure uniform length of sequences, padding was applied to the tokenized text.

### 4. Model Building

- **LSTM Neural Network**: I built an **LSTM** (Long Short-Term Memory) based deep learning model using Keras for emotion classification.
    - The model consists of an **Embedding layer** to convert tokens into dense vectors, an **LSTM layer** to capture sequential dependencies, and a **Dense layer** with softmax activation for multi-class classification.
  
- **Model Training**: The model was trained on the tokenized and padded text data, with **sparse categorical cross-entropy** as the loss function and **accuracy** as the metric.

### 5. Model Evaluation

- After training the model, I evaluated it on a testing dataset derived from **Book2.csv** to assess its accuracy in predicting emotions.
- The accuracy achieved was approximately **96%**.

### 6. Emotion Prediction on Airline Reviews

- Once the model was trained and evaluated, it was used to predict the emotion of each review in the **Airline_review.csv** dataset.
- I applied the trained model to classify the emotion of passenger reviews, adding the predicted emotion to the dataset.

### 7. Conclusion

This project demonstrates the application of deep learning (LSTM) for emotion detection in text, specifically focusing on classifying the emotions expressed in airline reviews. The model successfully predicts emotions such as `joy`, `sadness`, `anger`, `fear`, `love`, and `surprise`, providing valuable insights for airlines to improve customer service.

## Requirements

- Python 3.x
- TensorFlow 2.x
- Keras
- Pandas
- NumPy
- NLTK
- Seaborn
- Matplotlib

