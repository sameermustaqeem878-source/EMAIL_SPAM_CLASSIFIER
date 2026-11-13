
# Smart Spam Filter

Smart Spam Filter is a machine learning project that detects whether an email is spam or legitimate (ham). It uses Natural Language Processing (NLP), TF-IDF feature extraction, and Logistic Regression to classify emails.

The project also includes a Gradio web interface where users can test emails, view prediction results, and manage their mailbox.

## Features

- Email classification into Spam and Not Spam.
- Text cleaning and preprocessing using NLTK.
- TF-IDF vectorization with unigrams and bigrams.
- Training and comparison of Naive Bayes and Logistic Regression.
- Spam probability for each email.
- Identification of words influencing the prediction.
- Interactive Gradio web interface.
- Sample emails for testing.
- Mailbox with Inbox, Spam, and All folders.
- Search emails by sender, subject, or message content.
- Move emails between Inbox and Spam.
- Delete individual emails or clear the mailbox.
- Adjustable spam detection threshold.
- Automatic mailbox storage using JSON.

## Model Performance

The models were evaluated using an 80/20 train-test split with stratified sampling.

Test set size: 16,636 emails.

| Model | Accuracy | Precision | Recall | F1-Score |
|---|---:|---:|---:|---:|
| Naive Bayes | 97.51% | 98.70% | 96.52% | 97.60% |
| Logistic Regression | 98.78% | 98.59% | 99.10% | 98.84% |

Logistic Regression performed better and was selected as the final classification model.

## Technologies Used

- Python
- Pandas
- NumPy
- NLTK
- Scikit-learn
- Matplotlib
- Gradio
- Joblib
- KaggleHub
- Google Colab

## Project Structure

```text
EMAIL_SPAM_CLASSIFIER/
│
├── EMAIL_SPAM_CLASSIFIER.ipynb
├── README.md
│
└── spam_classifier_project/
    │
    ├── emails.csv
    ├── emails_clean.csv
    ├── emails_processed.csv
    │
    ├── spam_model.joblib
    ├── tfidf_vectorizer.joblib
    ├── model_nb.joblib
    ├── model_lr.joblib
    │
    └── mailbox.json
```

The `spam_classifier_project` folder and its files are created or saved automatically when the notebook runs.

## How It Works

1. The dataset is downloaded from Kaggle using KaggleHub.
2. Unnecessary, duplicate, contradictory, and very short emails are removed.
3. Email text is cleaned by removing URLs, punctuation, numbers, and stopwords.
4. Porter Stemming is applied to normalize words.
5. TF-IDF converts the processed email text into numerical features.
6. Naive Bayes and Logistic Regression models are trained.
7. Both models are evaluated using accuracy, precision, recall, and F1-score.
8. The trained Logistic Regression model is used for email classification.
9. Gradio provides an interface for testing emails and managing the mailbox.

## Running the Project

This project was developed using Google Colab.

### 1. Clone the Repository

```bash
git clone https://github.com/sameermustaqeem878-source/EMAIL_SPAM_CLASSIFIER.git
```

### 2. Open the Notebook

Open `EMAIL_SPAM_CLASSIFIER.ipynb` in Google Colab.

### 3. Mount Google Drive

Run the notebook and connect your Google Drive when prompted.

```python
from google.colab import drive
drive.mount('/content/drive')
```

### 4. Run All Cells

Execute the notebook cells in order. The notebook handles dataset downloading, preprocessing, model training, evaluation, and saving the trained models.

### 5. Launch the Application

Run the final cell to launch the Gradio interface.

Open the generated Gradio link to access the application.

## Application

The Gradio interface contains three main sections:

### Receive Email

Enter the sender, subject, and email message to check whether it is spam or legitimate. The application displays the prediction, spam probability, and words influencing the classification.

### Mailbox

View received emails in Inbox, Spam, or All folders. Search messages, read selected emails, move them between folders, or delete them.

### Settings

Adjust the spam probability threshold between 0.1 and 0.9. The mailbox is automatically updated based on the selected threshold, except for emails manually moved between folders.

## Author

Muhammad Sameer Mustaqeem

GitHub: https://github.com/sameermustaqeem878-source
