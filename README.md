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

Okay good — since your GitHub already has **multiple milestone notebooks + `FullPipeline.ipynb` + `salaries.csv`**, your README should explain **which file to run** and **what each file is for**.

Use this structure in your README:

````markdown
## How to Run the Codebase in Google Colab

1. Open the GitHub repository.

2. To run the complete project, open:

   `FullPipeline.ipynb`

   This notebook contains the full machine learning workflow from dataset loading until final model evaluation.

3. Open the notebook in Google Colab.

   In GitHub, click `FullPipeline.ipynb`, then click **Open in Colab** if the button is available.  
   If not, go to Google Colab → File → Open notebook → GitHub → paste the repository link.

4. Make sure the dataset file is available.

   The dataset file is already included in the repository as:

   `salaries.csv`

   The notebook loads the dataset using:

   ```python
   df = pd.read_csv('/content/salaries.csv')
````

If running directly in Colab, upload `salaries.csv` into the Colab file panel.

5. Run the installation cells first.

   The notebook uses additional libraries such as:

   ```python
   !pip install ydata-profiling
   !pip install xgboost lightgbm catboost
   !pip install tqdm
   ```

6. Run the notebook cells from top to bottom.

   The workflow follows this order:

   ```text
   1. Initial dataset exploration
   2. Data cleaning
   3. Exploratory Data Analysis
   4. Feature preprocessing and encoding
   5. Train-test split
   6. Model training
   7. 7-fold cross-validation
   8. Model comparison
   9. CatBoost hyperparameter tuning
   10. Final tuned CatBoost evaluation
   11. Before-and-after tuning comparison
   ```

7. Runtime note:

   The hyperparameter tuning section may take a long time:

   * RandomizedSearchCV: approximately 2 hours
   * GridSearchCV: approximately 7 hours

   To save time, users may skip the full tuning cells and run the final tuned CatBoost evaluation section because the best hyperparameters are already included.

## Notebook File Guide

| File                                 | Purpose                                                              |
| ------------------------------------ | -------------------------------------------------------------------- |
| `FullPipeline.ipynb`                 | Complete project pipeline from data loading to final evaluation      |
| `Milestone1_DataPipeline.ipynb`      | Dataset loading, cleaning, and preprocessing                         |
| `Milestone2_ArchitectureLogic.ipynb` | Pipeline logic, feature handling, and model architecture explanation |
| `Milestone3_TrainingLoop.ipynb`      | Model training and cross-validation                                  |
| `Milestone4_ModelOptimization.ipynb` | Hyperparameter tuning using RandomizedSearchCV and GridSearchCV      |
| `Milestone5_FinalEvaluation.ipynb`   | Final tuned model testing and evaluation results                     |
| `salaries.csv`                       | Dataset used for training and evaluation                             |
| `README.md`                          | Project explanation and running instructions                         |

## Requirements

This project is designed to run in Google Colab.

Required libraries:

```text
pandas
numpy
matplotlib
seaborn
scikit-learn
xgboost
lightgbm
catboost
tqdm
ydata-profiling
```

```

This is much better than only explaining the dataset, because it directly answers **“how to run your codebase in Google Colab.”**
```
