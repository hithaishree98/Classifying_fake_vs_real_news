# Fake vs. Real News Classifier

This project trains and evaluates simple text‐classification models to distinguish between **fake** and **real** news headlines using a public Kaggle dataset.

## Dataset & Preprocessing

- **Data source**: Kaggle “Fake News” train.csv (≈ 41 000 headlines, balanced classes).  
- **Cleaning**  
  - Dropped the `id` column and any rows with missing titles.  
  - Lower-cased and stripped all non-alphabetic characters.  
  - Removed English stop-words via NLTK.  
  - Stemmed tokens with Porter stemmer.  
- **Vectorization**  
  - `CountVectorizer(max_features=5000, ngram_range=(1,3))`  
    Captures up to 5 000 of the most frequent unigrams, bigrams, and trigrams.

## Results

| Model                      | Accuracy | Precision | Recall  |
|----------------------------|:--------:|:---------:|:-------:|
| Multinomial Naive Bayes    | 92.15 %  | 0.92      | 0.92    |
| Naive Bayes (α = 0.5)      | 92.28 %  | —         | —       |
| Logistic Regression        | 93.47 %  | 0.93      | 0.93    |
| Logistic Regression (C=0.8)| **93.60 %**  | —         | —       |

Confusion matrices and heatmaps for each model are available in the notebook.
