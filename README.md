```markdown
# 📧 Smart Spam Filter (`EMAIL_SPAM_CLASSIFIER`)

An end-to-end Machine Learning web application that classifies emails as **Spam** or **Ham (Legitimate)** using **TF-IDF Vectorization** and **Logistic Regression**, complete with an interactive **Gradio** dashboard and persistent mailbox management.

Achieves **98.8% F1-score** and accuracy on held-out test data.

---

## 🚀 Features

* **Robust Data Preprocessing & Cleaning:** Automatically downloads the email spam classification dataset via `kagglehub`, filters out noise, handles contradictory labels, removes short/duplicate texts, and applies Porter stemming using NLTK.
* **High-Performance ML Models:** Trains and benchmarks both **Multinomial Naive Bayes** and **Logistic Regression**, saving the best-performing model via `joblib`.
* **Explainable AI (Token-level Signals):** Highlights specific words driving predictions toward spam or ham so users can see *why* an email was flagged.
* **Interactive Gradio Dashboard:**
  * **Receive Email Tab:** Test custom emails or load pre-built sample messages to instantly view probability scores and highlighted token signals.
  * **Mailbox Tab:** Search, filter by folder (`Inbox`, `Spam`, `All`), manually reclassify messages, and manage incoming emails.
  * **Settings Tab:** Dynamically adjust the classification probability threshold (`0.1` to `0.9`) to make filtering stricter or more lenient.
* **Persistent Storage:** Automatically saves mailbox state in JSON format (`mailbox.json`).

---

## 📊 Model Performance

Evaluated on an independent test split ($N = 16,636$):

| Model | Accuracy | Precision | Recall | F1-Score |
| :--- | :---: | :---: | :---: | :---: |
| Naive Bayes | 97.51% | 98.70% | 96.52% | 97.60% |
| **Logistic Regression (Best)** | **98.78%** | **98.59%** | **99.10%** | **98.84%** |

---

## 🛠️ Tech Stack

* **Language:** Python
* **Data & NLP:** Pandas, NumPy, NLTK (Stopwords & PorterStemmer)
* **Machine Learning:** Scikit-Learn (`TfidfVectorizer` with `ngram_range=(1, 2)`, `LogisticRegression`, `MultinomialNB`)
* **Web UI:** Gradio
* **Storage & Serialization:** Joblib, JSON, KaggleHub

---

## 📦 Repository & Generated Artifacts

```text
EMAIL_SPAM_CLASSIFIER/
│
├── EMAIL_SPAM_CLASSIFIER.ipynb   # Main notebook (preprocessing, training, evaluation & Gradio UI)
├── README.md                     # Project documentation
│
└── spam_classifier_project/      # Generated automatically during notebook execution
    ├── emails.csv                # Raw dataset downloaded from Kaggle
    ├── emails_clean.csv          # Cleaned dataset
    ├── emails_processed.csv      # Stemmed text dataset
    ├── spam_model.joblib         # Best trained model (Logistic Regression)
    ├── tfidf_vectorizer.joblib   # Fitted TF-IDF vectorizer
    ├── model_nb.joblib           # Naive Bayes baseline model
    ├── model_lr.joblib           # Logistic Regression model
    └── mailbox.json              # Persistent state for Gradio UI

```

---

## 💻 Getting Started & Usage

1. **Clone the repository** or open `EMAIL_SPAM_CLASSIFIER.ipynb` directly in **Google Colab**:
```bash
git clone [https://github.com/sameermustaqeem878-source/EMAIL_SPAM_CLASSIFIER.git](https://github.com/sameermustaqeem878-source/EMAIL_SPAM_CLASSIFIER.git)

```


2. **Mount Google Drive** (when running in Google Colab) so datasets, trained models, and `mailbox.json` persist across sessions:
```python
from google.colab import drive
drive.mount('/content/drive')

```


3. **Run all cells** sequentially to download the dataset, preprocess text, train and evaluate the models, and launch the interactive Gradio web interface.
4. **Test the Filter:** Open the generated Gradio link to compose test emails, load sample messages, inspect word-level spam signals, and experiment with threshold tuning.

```[cite: 1, 2]

```
