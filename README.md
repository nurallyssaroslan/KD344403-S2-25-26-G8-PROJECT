# KD344403-S2-25-26-G8-PROJECT

## Dataset Used

**Data Science, AI & ML Job Salaries in 2025** by Adil Shamim on Kaggle.

This dataset contains real-world salary data for jobs in Data Science, Artificial Intelligence, and Machine Learning from 2020 to 2025. Each row represents a reported annual salary together with job-related and company-related attributes such as work year, experience level, employment type, job title, salary currency, salary in USD, employee residence, remote work ratio, company location, and company size.

The target variable used in this project is `salary_in_usd`, which represents the annual salary converted into USD for standardized comparison. The dataset is suitable for regression-based machine learning because the goal is to predict a continuous numerical value, which is job salary.

## Project Objective

The objective of this project is to develop and evaluate machine learning regression models to predict job salaries in the Data Science, Artificial Intelligence, and Machine Learning fields.

The project aims to analyze how factors such as job title, experience level, company size, remote work ratio, work year, employee residence, and company location influence salary prediction. Several regression models are compared, and the best-performing model is optimized using hyperparameter tuning to improve prediction performance.

## Machine Learning Task

This project is a **supervised regression task**.

The model learns from historical salary records and predicts the salary value based on input features. Since the predicted output is a continuous numerical value, regression models are used instead of classification models.

## Target Variable

```python
salary_in_usd
