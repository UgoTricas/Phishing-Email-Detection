# Détection d'e-mails de phishing par classification supervisée

🇬🇧/🇺🇸 [Read the English version](README.md)

Ce projet vise à détecter les e-mails de phishing à l'aide de plusieurs modèles supervisés d’apprentissage automatique.

À partir d’un jeu de données étiqueté (e-mails classés comme "légitimes" ou "phishing"), l’objectif est d’évaluer et comparer les performances de différents modèles afin d’identifier celui qui minimise au mieux les erreurs de prédiction — en tenant compte du coût potentiellement asymétrique entre les faux positifs et faux négatifs.

---

## Données utilisées

Les données sont disponibles à l’adresse suivante :  
[https://www.kaggle.com/datasets/subhajournal/phishingemails](https://www.kaggle.com/datasets/subhajournal/phishingemails)

Le jeu de données contient des milliers d’e-mails classés comme *Safe Email* ou *Phishing Email*. On observe un déséquilibre modéré entre les deux classes (environ 60 % / 40 %).

---

## Organisation du projet

L’analyse est structurée en plusieurs étapes :

### 1 - Prétraitement & vectorisation

- Nettoyage du texte et vectorisation via TF-IDF  
- Suppression des stopwords et limitation à 5000 variables  

### 2 - Sélection et optimisation des modèles

- Régression Logistique  
- Support Vector Classifier  
- Multinomial Naive Bayes  
- Random Forest Classifier  
- Optimisation des hyperparamètres via GridSearchCV  
- Comparaison basée sur le F1-score et l'AUC (ROC/PR)

### 3 - Comparaison et prise de décision

- Tous les modèles affichent de bonnes performances globales  
- La comparaison se recentre sur les matrices de confusion et la nature des erreurs  
- Une fonction de coût permet d’aider à choisir le meilleur modèle en fonction de l’aversion du décideur aux faux positifs ou faux négatifs  

### 4 - Mots importants en Régression Logistique

- Identification des mots les plus influents pour prédire les emails de phishing vs les emails sûrs
- Affichage des mots associés au phishing et aux emails sûrs en fonction de leurs coefficients dans le modèle de régression logistique

### 5 - Test sur des Emails Personnels

- Application du modèle de régression logistique entraîné sur des emails de phishing et sûrs reçus personnellement pour évaluer les performances du modèle dans un contexte réel

---

## Notebooks

Deux notebooks sont disponibles :

* `phishing_email_detection_en.ipynb` : [Version anglaise](phishing_email_detection_en.ipynb)  
* `phishing_email_detection_fr.ipynb` : [Version française](phishing_email_detection_fr.ipynb)  

---

## Lancer le projet

### Prérequis

Installer les dépendances nécessaires avec :

```pip install -r requirements.txt```

### Lancer le notebook

Utiliser Jupyter pour exécuter le notebook :

```jupyter notebook phishing_email_detection_fr.ipynb```
