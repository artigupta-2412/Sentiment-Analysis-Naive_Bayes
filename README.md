
# Amazon Review Sentiment Analyzer

This project uses Natural Language Processing (NLP) and Machine Learning (Logistic Regression) to classify Amazon product reviews as **Positive** or **Negative** based on their content. A Gradio interface is integrated for real-time user interaction.

---

## 📦 Features

- Clean and preprocesses text data while preserving key negations like "not", "never", etc.
- Uses **TF-IDF with bigrams** for vectorization.
- Handles class imbalance using **SMOTE**.
- Trains a **Logistic Regression model** with balanced class weights.
- Deploys a user-friendly GUI using **Gradio**.

---

## 🛠️ Installation

```bash
pip install wordcloud imbalanced-learn nltk gradio
```

---

## 📁 Dataset

The dataset is a compressed CSV file named `amazon.csv.zip`, containing at least the following columns:

- `review_content`: Text of the customer review
- `rating`: Integer rating (1 to 5)

---

## 📊 Preprocessing Steps

1. Remove HTML tags, numbers, and punctuation
2. Lowercase all text
3. Lemmatize words and remove stopwords (except negations)
4. Use **TF-IDF** with `ngram_range=(1,2)` and `max_features=5000`

---

## 🧠 Model

- Algorithm: Logistic Regression (`class_weight='balanced'`)
- Text Vectorization: TF-IDF
- Resampling: SMOTE to handle imbalance

---

## 🎯 Evaluation

- **Accuracy:** ~98-99% (varies by test split)
- Includes classification report and confusion matrix.

---

## 🖥️ Gradio Interface

The GUI allows users to input a product review and get sentiment prediction.

### Run the App:

```python
interface.launch()
```

---

## 📌 Example

```python
review = "This product is not worth the price!"
print(analyze_sentiment(review))
# Output: Predicted Sentiment: Negative
```

---

## 🧾 License

This project is for educational and research purposes.
