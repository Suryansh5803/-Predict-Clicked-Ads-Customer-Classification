# Ad Click Prediction Model

## Table of Contents
1. [Project Overview](#project-overview)
2. [Data Preparation](#data-preparation)
3. [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
4. [Feature Engineering](#feature-engineering)
5. [Model Selection and Training](#model-selection-and-training)
6. [Model Evaluation](#model-evaluation)
7. [Business Recommendations & Simulation](#business-recommendations--simulation)
8. [Conclusion and Future Work](#conclusion-and-future-work)

---

## 1. Project Overview

This project aims to develop a machine learning model capable of predicting whether users will click on an advertisement, using behavioral and demographic data. The goal is to increase ad engagement, improve ad spend efficiency, and maximize revenue from ad clicks by providing actionable insights for targeted marketing.

With ad budgets increasing globally, optimizing ad targeting is crucial. By predicting user ad-click behavior, businesses can allocate resources more effectively, reach high-intent users, and avoid wasting ad spend on less likely clicks. This project uses demographic and engagement data to create a model that identifies factors influencing ad-click likelihood, enabling tailored ad campaigns for different user segments.

**Key Objectives:**
- Understand user behavior and demographics that influence ad-click likelihood.
- Create a machine learning model with high precision for ad-click prediction.
- Provide data-driven recommendations to improve click-through rates (CTR).
- Simulate financial impacts of using the model to optimize ad campaigns.

## 2. Data Preparation
Data preprocessing was conducted to ensure compatibility and maximize model performance. The following steps were taken:

1. **Handling Missing Values:** Missing data were carefully reviewed and handled by either filling with mean/median values (for numerical data) or imputing with common category values (for categorical data).
2. **Encoding Categorical Variables:** Features such as 'Gender' were converted using one-hot encoding, while ordinal features were numerically encoded to retain rank order.
3. **Normalization and Scaling:** Numerical features (e.g., 'Daily Internet Usage', 'Age') were standardized to improve model convergence during training.
4. **Data Splitting:** The dataset was divided into training (80%) and testing (20%) sets to ensure the model's performance can be assessed on unseen data.
5. **Handling Outliers:** The dataset was checked for having outliers and founded outliers in area coloumn and handeled with imputation.
![image](https://github.com/user-attachments/assets/6cc4114d-6f67-4d09-b2c2-646fbfc7f197)

   
## 3. Exploratory Data Analysis (EDA)
EDA was conducted to identify patterns, trends, and correlations that might affect ad-click behavior. Key insights from the data analysis include:
![image](https://github.com/user-attachments/assets/e540c71a-d917-4697-a80a-d3cebca17f63)

---
![image](https://github.com/user-attachments/assets/43d32e95-2dd9-4698-98e3-e3be1f2ce1df)

---
![image](https://github.com/user-attachments/assets/b6b91a4c-2d78-4116-a056-ab7b39308b33)

---
![image](https://github.com/user-attachments/assets/f0504499-8de6-40b7-b73f-93c8cf4fcd77)

---
![image](https://github.com/user-attachments/assets/50bad65e-d223-4334-80bd-07ffe7826faa)



1. **Daily Internet Usage and Time on Site:**
   - Users with higher 'Daily Internet Usage' and 'Daily Time Spent on Site' are less likely to click on ads, indicating that users who spend more time browsing may become desensitized to ads.

   
2. **Age and Income Patterns:**
   - Older users tend to have higher ad-click rates, suggesting they might be less familiar with internet ads and more likely to engage.
   - Users from areas with lower income are more likely to click on ads, which may indicate a higher interest in offers and promotions targeted at budget-conscious consumers.

3. **Gender Analysis:**
   - Gender differences in ad-click behavior were examined, revealing slight variances in engagement, which may inform ad personalization strategies.

4. **Correlation Analysis:**
   - Correlation heatmaps and pair plots revealed significant relationships between variables such as 'Daily Internet Usage' and 'Daily Time Spent on Site', both of which were important in shaping the prediction model.

## 4. Feature Engineering
Based on the insights from EDA, several new features were engineered to enhance model prediction accuracy. Key feature engineering steps include:

1. **Interaction Terms:**
   - Interaction terms between variables such as 'Daily Time Spent on Site' and 'Area Income' were created to capture combined effects, which may reveal more nuanced user behaviors.

2. **Behavioral Segmentation:**
   - Behavioral features like 'Engagement Level' were created based on thresholds of daily internet usage and site time to classify users into high, medium, and low engagement groups.

3. **Time-Based Features:**
   - Features related to the time of day or day of the week of user interactions were extracted to see if engagement varies by time, which may influence ad scheduling.

## 5. Model Selection and Training
Several machine learning algorithms were considered, including:

1. **Logistic Regression:** Provides baseline performance with interpretable results, although limited in capturing complex patterns.
2. **Random Forest:** Offers robust predictions with interpretability through feature importance, ideal for handling non-linear relationships.
3. **Gradient Boosting (XGBoost):** Chosen as the final model due to its ability to handle complex patterns with high precision and recall scores.

Each model was tuned using hyperparameter optimization to achieve optimal performance on metrics like accuracy, precision, recall, and F1-score. The final model, a tuned Gradient Boosting classifier, was selected for its balance of interpretability and predictive accuracy.

## 6. Model Evaluation
The model was evaluated on key performance metrics to ensure its reliability and effectiveness for predicting ad-click behavior:

1. **Accuracy:** Measures overall correctness, reaching over 90%, showing strong predictive capability.
2. **Precision and Recall:** Precision was prioritized over recall to ensure that only high-probability users are targeted for ad engagement, achieving a precision of 95%.
3. **F1-Score:** Balances precision and recall, yielding a score of 92%, indicating the model is both accurate and effective at targeting high-likelihood users.
4. **Confusion Matrix:** Provided insights into false positives and negatives, with minimal misclassification.
![image](https://github.com/user-attachments/assets/0bfaf91c-a5b2-44e3-8b20-2f3545df71f2)
---
![image](https://github.com/user-attachments/assets/d62d33af-e3b8-4850-bebc-157d48adf363)


## 7. Business Recommendations & Simulation

### 7.1 Business Recommendations

Based on insights from EDA and feature importance analysis, the following recommendations are provided:

#### 1. Content Optimization
   - **Insight:** Users with high daily time on site and daily internet usage are less likely to click on ads.
   - **Recommendation:** Create highly engaging and relevant ad content tailored to target users. Visuals and messaging should align with the audience’s preferences. Consider interactive or dynamic content to capture attention and improve ad click-through rates.

#### 2. Targeted Pricing Strategies
   - **Insight:** Users from lower-income areas are more likely to click on ads.
   - **Recommendation:** Implement pricing strategies aimed at lower-income users, such as special pricing tiers, discounts, or bundled products. Ads promoting affordable product options or seasonal discounts can attract budget-conscious users, increasing ad engagement and conversion rates.

#### 3. Age-Targeted Marketing Campaigns
   - **Insight:** Older users are more likely to click on ads.
   - **Recommendation:** Design campaigns tailored to older demographics, featuring content that resonates with their interests, such as ease of use, reliability, or value-based messaging. Personalized visuals and copy focused on quality or savings may enhance ad performance within this segment.

### 7.2 Business Simulation

To illustrate the financial impact of implementing the machine learning model, we compare ad performance before and after using the model:

#### Assumptions:
- **Cost per Mille (CPM)**: Rp.100,000
- **Revenue per Ad Clicked**: Rp.2,000

#### **Before Using Machine Learning Model**
- **Number of Users Advertised**: 1,000
- **Click-Through Rate (CTR)**: 50%
- **Total Cost**: Rp.100,000
- **Total Revenue**: \(0.5 \times 1,000 \times 2,000 = Rp.1,000,000\)
- **Total Profit**: \(Rp.1,000,000 - Rp.100,000 = Rp.900,000\)

#### **After Using Machine Learning Model**
- **Number of Users Advertised**: 1,000
- **Click-Through Rate (CTR)**: 95%
- **Total Cost**: Rp.100,000
- **Total Revenue**: \(0.95 \times 1,000 \times 2,000 = Rp.1,900,000\)
- **Total Profit**: \(Rp.1,900,000 - Rp.100,000 = Rp.1,800,000\)

#### Conclusion:
Implementing the machine learning model has resulted in:
- **Increased CTR by 45%**, from 50% to 95%.
- **Doubled profit**, from Rp.900,000 to Rp.1,800,000.

These outcomes show that the model significantly improves ad targeting efficiency, increasing both engagement and profitability by focusing on high-probability ad-click users.

## 8. Conclusion and Future Work
The ad-click prediction model effectively identifies high-likelihood users, optimizing ad targeting and maximizing revenue. Future enhancements could include:
- Incorporating real-time user interaction data.
- Testing alternative models (e.g., neural networks) for further accuracy improvements.
- Implementing an A/B testing framework to validate model recommendations in live campaigns.

This project demonstrates the potential for machine learning in ad optimization, highlighting data-driven decision-making benefits for businesses aiming to enhance engagement and reduce ad spend waste.



