# 📰 Fake News Detection using Machine Learning

![Python](https://img.shields.io/badge/Python-3.10-blue)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-ML-orange)
![NLP](https://img.shields.io/badge/NLP-TF--IDF-green)
![Status](https://img.shields.io/badge/Project-Completed-success)

---

# 📖 Project Overview

Fake news has become one of the biggest challenges on the internet. Detecting misleading information manually is difficult because of the massive amount of news published every day.

This project applies **Natural Language Processing (NLP)** and **Machine Learning** techniques to automatically classify news articles as either:

- ✅ Real News
- ❌ Fake News

The project compares multiple Machine Learning algorithms and evaluates their performance to identify the best classifier.

---

# 🎯 Objectives

- Detect fake news automatically.
- Clean and preprocess news articles.
- Convert text into numerical features using TF-IDF.
- Compare multiple Machine Learning models.
- Optimize Decision Tree using Hyperparameter Tuning.
- Save the trained model for future predictions.

---

# 📂 Dataset

The project uses two datasets:

| Dataset | Description |
|----------|-------------|
| Fake.csv | Fake news articles |
| True.csv | Real news articles |

After loading both datasets:

- Fake News → Label **0**
- Real News → Label **1**

The datasets are merged into one dataset before preprocessing.

---

# 📊 Dataset Information

Initial dataset size:

- Fake News + Real News

Combined Dataset:

- **44,898** news articles

Columns before preprocessing:

- title
- text
- subject
- date

Final columns used:

- text
- class

Duplicate rows removed:

- **6,251**

Missing values:

- None

---

# 🧹 Data Preprocessing

Several preprocessing steps were applied before training:

### ✔ Shuffle Dataset

Randomly shuffled all samples.

---

### ✔ Remove Unnecessary Columns

Dropped:

- title
- subject
- date
- index

Only the article text was used for prediction.

---

### ✔ Remove Missing Values

```python
dropna()
```

---

### ✔ Remove Duplicate Records

```python
drop_duplicates()
```

Removed **6,251 duplicated articles**.

---

### ✔ Text Cleaning

Each article was processed by:

- Converting to lowercase
- Removing punctuation
- Removing special characters
- Removing extra spaces

Example:

```
Hello!!! World...
```

↓

```
hello world
```

---

### ✔ Source Leakage Removal

Since almost all real news articles started with:

```
Reuters -
```

The project removes this pattern to prevent the model from cheating by learning the source instead of the article content.

---

# 🔤 Feature Extraction

Text was converted into numerical vectors using:

## TF-IDF Vectorizer

This converts every news article into numerical features suitable for Machine Learning algorithms.

---

# 🤖 Machine Learning Models

The following classifiers were trained and compared:

| Model | Accuracy |
|--------|----------|
| Support Vector Machine (Linear) | **98.69%** 🏆 |
| Logistic Regression | **98.05%** |
| Random Forest | **96.53%** |
| Decision Tree (Optimized) | **94.42%** |
| Decision Tree | **93.97%** |
| Multinomial Naive Bayes | **93.30%** |
| K-Nearest Neighbors | **87.34%** |

---

# 🏆 Best Model

The highest-performing model was:

## Support Vector Machine (Linear Kernel)

Accuracy:

```
98.69%
```

Although the notebook exports the Logistic Regression model for deployment because it provides excellent performance with lower computational cost.

---

# 🌳 Decision Tree Optimization

The project improves Decision Tree using:

- GridSearchCV
- Cross Validation

Parameters searched:

- max_depth
- min_samples_leaf
- min_samples_split

Best Parameters:

```
max_depth = 20
min_samples_leaf = 1
min_samples_split = 2
```

Best Test Accuracy:

```
94.42%
```

---

# ✅ Cross Validation

5-Fold Cross Validation was performed.

Average Accuracy:

```
93.98%
```

Standard Deviation:

```
±0.47%
```

---

# 💾 Model Saving

The trained Logistic Regression model is exported using Joblib.

Saved files:

```
model.pkl
vectorizer.pkl
```

These files can later be loaded without retraining.

---

# 🔍 Prediction Pipeline

The prediction process:

```
Input News

      │

      ▼

Text Cleaning

      │

      ▼

Remove Reuters Pattern

      │

      ▼

TF-IDF Vectorizer

      │

      ▼

Logistic Regression Model

      │

      ▼

Real News / Fake News
```

---

# 📁 Project Structure

```
Fake-News-Detection/

│── Fake.csv
│── True.csv
│── model.pkl
│── vectorizer.pkl
│── Fake_News_Detection.ipynb
│── README.md
```

---

# ⚙ Requirements

Install all required packages:

```bash
pip install pandas
pip install numpy
pip install scikit-learn
pip install joblib
```

or

```bash
pip install pandas numpy scikit-learn joblib
```

---

# 📚 Libraries Used

- pandas
- numpy
- re
- joblib

Scikit-learn modules:

- train_test_split
- accuracy_score
- TfidfVectorizer
- MultinomialNB
- RandomForestClassifier
- DecisionTreeClassifier
- LogisticRegression
- KNeighborsClassifier
- SVC
- GridSearchCV
- cross_val_score

---

# 🚀 How to Run

Clone the repository

```bash
git clone https://github.com/YourUsername/Fake-News-Detection.git
```

Install dependencies

```bash
pip install -r requirements.txt
```

Run the notebook

```
Fake_News_Detection.ipynb
```

---

# 📈 Results Summary

| Model | Accuracy |
|--------|----------|
| SVM | **98.69%** |
| Logistic Regression | **98.05%** |
| Random Forest | **96.53%** |
| Decision Tree (Optimized) | **94.42%** |
| Decision Tree | **93.97%** |
| Naive Bayes | **93.30%** |
| KNN | **87.34%** |

---

# 💡 Future Improvements

- Apply stemming and lemmatization.
- Experiment with Word2Vec and FastText embeddings.
- Train transformer models such as BERT.
- Build a Streamlit or Flask web application.
- Deploy the model using Docker or cloud services.

---

# 👨‍💻 Author

**Omar Shoman**

Machine Learning & AI Student

---

# ⭐ If you found this project useful, don't forget to star the repository!
