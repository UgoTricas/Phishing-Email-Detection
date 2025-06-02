# Phishing Email Detection and Decision Taking

🇫🇷 [Lire la version française](README_fr.md)

This project evaluates different Machine Learning models to detect phishing emails, incorporating a cost function to guide decision-making based on the decision-maker’s aversion to false positives and false negatives.

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
- Random Forest Classifier  
- GridSearchCV to find optimal hyperparameters  

### 3. Model Comparison

- All models perform well  
- Focus shifts to confusion matrices to assess the nature of errors  
- Function of cost introduced to guide decision-making based on the decision-maker’s aversion to false positives or false negatives  

### 4. Important Features in Logistic Regression

- Identification of the most influential words for predicting phishing vs safe emails 
- Displaying the top words associated with phishing and safe emails based on their coefficients in the logistic regression model
  
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
