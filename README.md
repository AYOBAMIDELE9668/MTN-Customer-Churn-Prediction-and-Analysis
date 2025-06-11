# MTN-Customer-Churn-Prediction-and-Analysis

## 1. Introduction  
I undertook this project to analyze customer churn behavior for MTN, one of Nigeria’s leading telecommunications providers. The goal was to understand why customers leave the service and build a predictive model to identify customers at risk of churning. This would help MTN improve customer retention strategies, optimize pricing and network services, and ultimately reduce revenue loss due to customer attrition.

The dataset provided contains multiple subscription records per customer, including details such as age, gender, data usage, satisfaction rate, and reasons for churn. It also includes textual feedback from customers who have left the service.

## 2. Objectives  
My objectives were:

- To predict which customers are likely to churn using machine learning.  
- To analyze the reasons for churn using natural language processing (NLP).  
- To segment customers based on their behavior and demographics.

## 3. Data Overview  
The dataset contains over 400 customer records with multiple subscriptions per customer. Each row represents a subscription record, not a unique customer. Key fields include:

- **Customer ID** – Unique identifier  
- **Age, Gender, State**  
- **MTN Device** – Type of device used  
- **Satisfaction Rate, Data Usage, Total Revenue**  
- **Customer Tenure in months**  
- **Customer Churn Status** – Indicates if the customer has churned (Yes/No)  
- **Reasons for Churn** – Textual feedback from customers

## 4. Methodology  

### 4.1 Data Preprocessing  
Since each customer can have multiple subscriptions, I aggregated the data at the customer level. For each customer, I calculated:

- Total revenue  
- Average satisfaction rate  
- Maximum tenure  
- Number of devices used  
- Recency of purchase  

I also handled missing values, encoded categorical variables, and normalized numerical features.

### 4.2 Feature Engineering  
I created several derived features to enhance model performance:

- Average monthly revenue  
- Average monthly data usage  
- Number of subscriptions per customer  
- Plan variety – How many different plans a customer has tried  

These helped capture behavioral patterns that influence churn.

### 4.3 Exploratory Data Analysis (EDA)  
I performed EDA to understand the distribution of key variables and how they relate to churn. Visualizations included:

- Age vs Churn  
- Revenue vs Churn  
- Tenure vs Churn  
- Satisfaction levels by churn status  

This gave me early clues about the main drivers of churn.

### 4.4 Model Development  
I built a Random Forest classifier to predict whether a customer will churn. I trained the model using preprocessed customer-level data and evaluated its performance using:

- Accuracy  
- Precision  
- Recall  
- F1-score  
- ROC AUC  

I focused on maximizing recall, since identifying customers who will churn is more important than predicting all non-churners correctly.

### 4.5 Model Interpretation  
To understand what drives churn, I used SHAP values to interpret the model. This helped me identify the most influential factors, such as:

- High call tariffs  
- Costly data plans  
- Poor network quality  
- Low satisfaction scores  

### 4.6 NLP Analysis on Churn Reasons  
I extracted insights from the free-text Reasons for Churn column using NLP techniques. I generated:

- Word clouds showing frequently mentioned words  
- Keyword extraction to highlight top reasons like “Poor Network” and “Costly Data Plans”  
- Topic modeling using TF-IDF and clustering to group similar feedback  

This analysis supported my findings from the predictive model and provided actionable business insights.

## 5. Results and Insights  

### 5.1 Churn Prediction Performance  
- **Model**: Random Forest Classifier  
- **ROC AUC Score**: ~0.89  
- **Recall**: ~0.82 – Meaning the model successfully identifies 82% of actual churn cases  

### 5.2 Key Drivers of Churn  
From both model interpretation and text analysis, the top reasons for churn include:

- High Call Tariffs  
- Costly Data Plans  
- Poor Network Quality  
- Fast Data Consumption  
- Better Offers from Competitors  

### 5.3 Customer Segmentation  
I identified high-risk customer segments, including:

- Customers with low satisfaction scores  
- Customers who recently reduced plan usage  
- Customers who frequently changed plans  

## 6. Conclusion  
This project allowed me to combine machine learning, data visualization, and natural language processing to deliver actionable insights into customer churn for MTN.

By building a robust churn prediction model and analyzing real customer feedback, I provided a comprehensive understanding of why customers leave and how MTN can retain them.

## 7. Future Work  
Some improvements I plan to implement in the future include:

- Testing other models like XGBoost or LightGBM for better performance  
- Deploying the model as an API for integration with CRM systems  
- Automating the pipeline for periodic retraining and reporting  

## 8. Tools and Technologies Used  
- **Python** – Core programming language  
- **Pandas, NumPy** – Data manipulation  
- **Scikit-learn, XGBoost** – Machine learning  
- **SHAP** – Model interpretation  
- **NLTK, spaCy, Gensim** – NLP analysis  
- **Matplotlib, Seaborn, WordCloud** – Visualization  
