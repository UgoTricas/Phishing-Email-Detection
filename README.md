# Phishing Email Detection via Supervised Classification

🇫🇷 [Lire la version française](README_fr.md)

This project explores the detection of phishing emails using several supervised machine learning models.

Starting from a labeled dataset of emails (classified as "Safe" or "Phishing"), the objective is to evaluate and compare different models to identify which performs best at minimizing false predictions — especially in a context where the cost of different types of errors may vary.

---

## Data Used

The data can be found at the following link:  
[https://www.kaggle.com/datasets/subhajournal/phishingemails](https://www.kaggle.com/datasets/subhajournal/phishingemails)

The dataset contains thousands of email texts labeled as either *Safe Email* or *Phishing Email*. It has a moderate class imbalance (around 60% / 40%).

---

## Project Structure

The analysis proceeds in several steps:

### 1. Preprocessing

- Text cleaning and vectorization using TF-IDF
- Handling of stopwords and dimensionality reduction (max 5000 features)

### 2. Model Selection and Optimization

- Logistic Regression  
- Support Vector Classifier  
- Multinomial Naive Bayes  
- Random Forest Classifier  
- GridSearchCV to find optimal hyperparameters  
- F1-score and AUC (ROC/PR) used to compare model performance

### 3. Model Comparison

- All models perform well on traditional metrics  
- Focus shifts to confusion matrices to assess the nature of errors  
- Function of cost introduced to guide decision-making based on the decision-maker’s aversion to false positives or false negatives  

### 4. Important Features in Logistic Regression

- Identification of the most influential words for predicting phishing vs safe emails 
- Displaying the top words associated with phishing and safe emails based on their coefficients in the logistic regression model

### 5. Personal Email Testing

- Applying the trained logistic regression model to personally received phishing and safe emails to evaluate the model’s real-world performance  

---

## Notebooks

Two notebooks are available:

* `phishing_email_detection_en.ipynb` : [English version](phishing_email_detection_en.ipynb)  
* `phishing_email_detection_fr.ipynb` : [French version](phishing_email_detection_fr.ipynb)  

---

## Running the Project

### Prerequisites

Install the required libraries via pip:

```pip install -r requirements.txt```

### Run the Notebook

Use Jupyter to run the notebook:

```jupyter notebook phishing_email_detection_en.ipynb```
