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

`salary_in_usd`

## Repository Structure

| File | Purpose |
|---|---|
| `FullPipeline.ipynb` | Complete project pipeline from dataset loading until final model evaluation |
| `Milestone1_DataPipeline.ipynb` | Dataset loading, data cleaning, preprocessing, and early exploration |
| `Milestone2_ArchitectureLogic.ipynb` | Pipeline logic, feature handling, model architecture, and explanation of why the approach works |
| `Milestone3_TrainingLoop.ipynb` | Model training, 7-fold cross-validation, and baseline model comparison |
| `Milestone4_ModelOptimization.ipynb` | Hyperparameter tuning using RandomizedSearchCV and GridSearchCV |
| `Milestone5_FinalEvaluation.ipynb` | Final tuned model testing, evaluation metrics, and conclusion |
| `salaries.csv` | Dataset used for training and evaluation |
| `README.md` | Project explanation and instructions to run the codebase |

## How to Run the Codebase in Google Colab

### 1. Open the GitHub Repository

Open this project repository in GitHub.

To run the complete project, use:

`FullPipeline.ipynb`

This notebook contains the full machine learning workflow from dataset loading until final model evaluation.

### 2. Open the Notebook in Google Colab

There are two ways to open the notebook in Google Colab.

**Option 1: Open from GitHub**

1. Click `FullPipeline.ipynb` in the GitHub repository.
2. Click **Open in Colab** if the button is available.

**Option 2: Open from Google Colab**

1. Go to Google Colab.
2. Click **File**.
3. Click **Open notebook**.
4. Select the **GitHub** tab.
5. Paste the GitHub repository link.
6. Choose `FullPipeline.ipynb`.

### 3. Make Sure the Dataset is Available

The dataset file is included in this repository as:

`salaries.csv`

The notebook loads the dataset using:

`df = pd.read_csv('/content/salaries.csv')`

If the dataset does not load automatically in Google Colab, manually upload `salaries.csv` into the Colab file panel.

To upload manually:

1. Click the folder icon on the left side of Google Colab.
2. Click the upload button.
3. Upload `salaries.csv`.
4. Make sure the file name remains exactly `salaries.csv`.

### 4. Run the Installation Cells

Before running the full notebook, run the installation cells first.

The project uses several additional libraries:

`!pip install ydata-profiling`

`!pip install xgboost lightgbm catboost`

`!pip install tqdm`

These libraries are needed for automated profiling, machine learning models, CatBoost training, and progress bars.

### 5. Run the Notebook Cells From Top to Bottom

After the dataset and required libraries are ready, run all notebook cells in order.

The notebook workflow follows this sequence:

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

### 6. Runtime Note for Hyperparameter Tuning

The hyperparameter tuning section may take a long time because CatBoost is trained many times using 7-fold cross-validation.

In this experiment:

| Tuning Method | Approximate Runtime |
|---|---|
| RandomizedSearchCV | 2 hours |
| GridSearchCV | 7 hours |

RandomizedSearchCV was used for broad hyperparameter exploration. It randomly tested selected combinations from a wide search space.

GridSearchCV was used for focused hyperparameter tuning. It tested every possible combination from a smaller and more refined parameter grid.

To save time, users may skip the full tuning cells and run the final tuned CatBoost evaluation section directly because the best hyperparameters are already included in the notebook.

### 7. Check the Final Output

The final output shows the model performance before and after tuning.

The final evaluation table includes:

- CV R²
- CV R² Standard Deviation
- Test R²
- MSE
- RMSE
- Gap between CV R² and Test R²
- Model Status

The main purpose of the final comparison is to check whether hyperparameter tuning improves the CatBoost model and whether the tuned model generalizes well on unseen test data.

## Models Used

The project compares several regression models:

- Linear Regression
- Ridge Regression
- Lasso Regression
- Random Forest Regressor
- Support Vector Regressor
- XGBoost Regressor
- LightGBM Regressor
- CatBoost Regressor

CatBoost was selected for further hyperparameter tuning because it performed strongly compared to the other regression models.

## Model Evaluation Metrics

The models are evaluated using the following metrics:

| Metric | Purpose |
|---|---|
| CV R² | Measures average model performance during 7-fold cross-validation |
| CV R² Standard Deviation | Shows how stable the model performance is across folds |
| Test R² | Measures model performance on unseen test data |
| MSE | Measures the average squared prediction error |
| RMSE | Measures prediction error in the same unit as the target variable |
| Gap between CV R² and Test R² | Helps identify whether the model may be overfitting or generalizing well |

## Hyperparameter Tuning

The best model was optimized using two tuning methods.

### RandomizedSearchCV

RandomizedSearchCV was used as the first tuning stage. It randomly tested 100 parameter combinations from a wide search space using 7-fold cross-validation. This helped explore many possible CatBoost settings while reducing runtime compared to testing all combinations.

### GridSearchCV

GridSearchCV was used as the second tuning stage. It tested every possible combination from a smaller and more focused parameter grid. The grid was based on promising values found during RandomizedSearchCV.

### Final Tuned CatBoost Model

After tuning, the final CatBoost model was trained using the selected best hyperparameters and evaluated using:

- 7-fold cross-validation
- Unseen test set evaluation
- Before-and-after tuning comparison

## Requirements

This project is designed to run in **Google Colab**.

Required Python libraries:

- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn
- xgboost
- lightgbm
- catboost
- tqdm
- ydata-profiling

## Notes

- Make sure `salaries.csv` is available in the Colab environment before running the notebook.
- Run the notebook cells in order to avoid missing variables such as `X_train`, `X_test`, `y_train`, `y_test`, and `df_results`.
- The full tuning process may take several hours.
- For faster execution, run the final tuned CatBoost evaluation section instead of rerunning RandomizedSearchCV and GridSearchCV.
