# Debt Collection NLP Classifier with Intelligent Routing

## Project Overview

Built an NLP-based classification system to analyse customer messages in a debt collection environment and predict the customer’s intent. The solution combines text preprocessing, sequence modelling using LSTM neural networks, hyperparameter tuning, and a rule-based routing system to automate decision-making.

The model classifies messages into predefined categories and routes them to the appropriate action or team, with a confidence-based fallback to human agents when predictions are uncertain.

---

## Project Objectives

- Classify customer messages into meaningful intent categories  
- Apply NLP preprocessing techniques to prepare text data  
- Build and optimise an LSTM-based deep learning model  
- Evaluate model performance using classification metrics  
- Implement a routing system based on predicted intent  
- Introduce confidence-based decision logic for real-world use  

---

## Dataset

A custom dataset was manually created for this project. Each row represents a customer message and its corresponding intent label.

### Target Categories

- willing_to_pay  
- financial_hardship  
- dispute  
- refusal  
- payment_plan  

---

## Data Cleaning and Preparation

The following preprocessing steps were completed:

- Converted all text to lowercase  
- Removed punctuation using regular expressions  
- Removed extra whitespace  
- Encoded categorical labels using LabelEncoder  
- Tokenised text using Keras Tokenizer  
- Converted text into numerical sequences  
- Applied padding to ensure uniform sequence length  

---

## Model Development

### Model Architecture

- Embedding layer to learn word representations  
- LSTM layer to capture sequence dependencies  
- Dropout layer to reduce overfitting  
- Dense hidden layer with ReLU activation  
- Output layer with Softmax activation for multi-class classification  

### Hyperparameter Tuning

Random Search (Keras Tuner) was used to optimise:

- Embedding dimensions (32, 64, 128)  
- Number of LSTM units (32, 64, 128)  

### Train-Test Split

- 80% Training Data  
- 20% Testing Data  

---

## Model Evaluation

### Performance Metrics Used

- Accuracy  
- Precision  
- Recall  
- F1-score  

A classification report was generated to evaluate model performance across all classes.

---

## Routing System

A rule-based routing system maps predicted labels to actions:

- willing_to_pay → Send payment link  
- financial_hardship → Send to financial hardship team  
- dispute → Send to dispute team  
- refusal → Send to refusal team  
- payment_plan → Offer installment plan  

---

## Confidence-Based Decision System

A confidence threshold improves reliability:

- High confidence → Automatically route the message  
- Low confidence → Send to human agent  

---

## Example Workflow

Input message → Preprocessing → Tokenisation → Model prediction → Confidence check → Routing decision  

---
## Tools and Libraries Used

- Python  
- pandas  
- numpy  
- tensorflow / keras  
- keras-tuner  
- scikit-learn  
- re  

---

## Project Files

- `Debt_NLP_Classifier.ipynb` – Full workflow and model  
- `README.md` – Project documentation  

---

## How to Run

### Install dependencies
pip install datasets
pip install keras-tuner
pip install tensorflow pandas numpy scikit-learn
