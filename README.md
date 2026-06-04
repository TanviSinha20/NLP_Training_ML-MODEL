# NLP_Training_ML-MODEL
Implementation of ML topics like encoding and embedding inNLP

# Spam Message Classification Using Text Representation Techniques

## Overview

This project implements a Spam Message Classification system using Natural Language Processing (NLP) and Machine Learning techniques. The objective is to compare different text representation methods and evaluate their effectiveness in classifying SMS messages as **Spam** or **Ham (Legitimate Messages)**.

The project uses the SMS Spam Collection Dataset and compares the performance of multiple text representation techniques using a Logistic Regression classifier.

---

## Dataset

### SMS Spam Collection Dataset

* Total Messages: **5,572**
* Classes:

  * **Ham** (Legitimate Messages)
  * **Spam** (Unwanted Promotional/Fraudulent Messages)

### Example Messages

**Ham:**

> Hey, are we meeting at 5 PM?

**Spam:**

> Congratulations! You have won a free prize!

---

## Project Workflow

```text
Dataset
   ↓
Text Preprocessing
   ↓
Feature Extraction
   ↓
Model Training
   ↓
Evaluation
```

---

## Text Preprocessing

The following preprocessing steps were performed:

* Convert text to lowercase
* Remove special characters and numbers
* Tokenization
* Stopword Removal

### Example

**Original Text**

```text
Congratulations! You've won ₹5000. Call now!!!
```

**Processed Text**

```text
congratulations won call
```

---

## Text Representation Techniques

### 1. One-Hot Encoding

Represents words using binary values.

* 1 → Word Present
* 0 → Word Absent

Example:

```text
free cash
```

Vector:

```text
[1, 1, 0, 0]
```

---

### 2. Bag of Words (BoW)

Represents text using word frequency counts.

Example:

```text
free free cash
```

Vector:

```text
[2, 1, 0, 0]
```

---

### 3. TF-IDF

TF-IDF (Term Frequency – Inverse Document Frequency) assigns higher importance to informative words and lower importance to common words.

**High Importance Words**

```text
free, prize, cash
```

**Low Importance Words**

```text
the, is, and
```

---

### 4. Word2Vec CBOW

Continuous Bag of Words (CBOW) learns word embeddings by predicting a target word from surrounding context words.

```text
Context → Target Word
```

Example:

```text
You won a ___ ticket
```

Prediction:

```text
free
```

---

### 5. Word2Vec Skip-Gram

Skip-Gram learns word embeddings by predicting surrounding words from a target word.

```text
Target Word → Context Words
```

Example:

Input:

```text
free
```

Predicted Words:

```text
cash, prize, offer
```

---

## Machine Learning Model

### Logistic Regression

A Logistic Regression classifier was trained using each text representation technique and evaluated on the test dataset.

### Why Logistic Regression?

* Simple and efficient
* Performs well on text classification tasks
* Fast training and prediction
* Easy to compare across different embeddings

---

## Technologies Used

* Python
* Google Colab
* Pandas
* NumPy
* NLTK
* Scikit-learn
* Gensim
* Matplotlib
* Seaborn

---

## Results

The performance of different text representation techniques was compared using Logistic Regression.

| Technique          | Accuracy (%) |
| ------------------ | -----------: |
| One-Hot Encoding   |    **97.85** |
| Bag of Words       |    **97.58** |
| TF-IDF             |    **95.70** |
| Word2Vec Skip-Gram |    **95.25** |
| Word2Vec CBOW      |    **86.55** |

### Performance Ranking

1. One-Hot Encoding – 97.85%
2. Bag of Words – 97.58%
3. TF-IDF – 95.70%
4. Word2Vec Skip-Gram – 95.25%
5. Word2Vec CBOW – 86.55%

---

## Analysis

* One-Hot Encoding achieved the highest accuracy of **97.85%**.
* Bag of Words produced nearly identical performance with **97.58%** accuracy.
* TF-IDF achieved **95.70%** accuracy by emphasizing informative words.
* Skip-Gram achieved **95.25%** accuracy and successfully captured semantic relationships between words.
* CBOW achieved **86.55%** accuracy, which is lower due to the small dataset size and short message lengths.

---

## Project Structure

```text
├── spam.csv
├── ML_Project_2.ipynb
├── README.md
```

---

## Key Concepts Covered

* Natural Language Processing (NLP)
* Text Preprocessing
* Tokenization
* Stopword Removal
* One-Hot Encoding
* Bag of Words
* TF-IDF
* Word Embeddings
* CBOW
* Skip-Gram
* Logistic Regression
* Text Classification

---

## Conclusion

This project demonstrates how different text representation techniques affect the performance of machine learning models in spam message classification.

The experimental results show that traditional count-based methods such as One-Hot Encoding and Bag of Words outperform Word2Vec-based embeddings for this dataset. This is because spam messages often contain highly distinctive keywords such as **"free"**, **"win"**, **"cash"**, and **"prize"**, making simple frequency-based representations highly effective.

Among all evaluated techniques, **One-Hot Encoding achieved the best performance with an accuracy of 97.85%**, making it the most effective approach for this SMS spam classification task.

---

## Future Work

Possible improvements include:

* Support Vector Machines (SVM)
* Naive Bayes Classifier
* FastText Embeddings
* GloVe Embeddings
* BERT and Transformer Models
* Hyperparameter Tuning
* Cross Validation
* Deployment as a Web Application

```
```
