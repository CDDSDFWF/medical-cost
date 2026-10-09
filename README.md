# Medical Cost Prediction

Machine-learning project that predicts individual medical insurance charges from personal attributes.
Submitted for the **IBM SkillsBuild Data Analytics with AI – Academic Internship Program** (BharatCares in association with AICTE).

## Dataset
- **Name:** Medical Cost Personal Datasets (`insurance.csv`)
- **Source (Kaggle):** https://www.kaggle.com/datasets/mirichoi0218/insurance
- **Size:** 1,338 rows × 7 columns (1,337 after removing 1 duplicate), no missing values

| Column | Description |
|---|---|
| age | Age of primary beneficiary |
| sex | female / male |
| bmi | Body Mass Index |
| children | Number of dependents covered |
| smoker | yes / no |
| region | northeast, northwest, southeast, southwest |
| charges | **Target** – medical costs billed by insurance (USD) |

## Project Description
The project predicts `charges` (a regression problem). Steps: data cleaning, exploratory data analysis, feature engineering (`obese`, `obese_smoker`), training and comparing four models (Linear, Ridge, Random Forest, Gradient Boosting), hyperparameter tuning with GridSearchCV, evaluation, feature importance, and saving the final model.

## Technologies Used
Python 3.9+, Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn, Joblib, Jupyter Notebook

## Setup & Run
1. Download `insurance.csv` from the Kaggle link above and place it in the same folder as the notebook.
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Start Jupyter and open the notebook:
   ```bash
   jupyter notebook
   ```
4. Run all cells (`Kernel → Restart & Run All`). Charts are saved in a `figures/` folder and the trained model is saved as `medical_cost_model.pkl`.

## Key Results
| Model | Test R² | MAE (USD) | RMSE (USD) |
|---|---|---|---|
| Linear Regression (selected) | 0.907 | 2,369 | 4,142 |
| Ridge Regression | 0.906 | 2,378 | 4,146 |
| Gradient Boosting | 0.904 | 2,440 | 4,203 |
| Tuned Gradient Boosting | 0.902 | 2,475 | 4,235 |
| Random Forest | 0.881 | 2,630 | 4,677 |

**Key findings:** smoking is the strongest cost driver (smokers pay about 3.8× more on average), followed by age and the obese-smoker group. Sex, region and number of children have little effect.

## Project Files
- `YourName_MedicalCost.ipynb` – complete code
- `requirements.txt` – Python dependencies
- `YourName_ProjectReport.docx` – project report
- `README.md` – this file

## Limitations
Small dataset (1,337 records), only six inputs, US-based data, no medical history.

## Author
Your Name – IBM SkillsBuild Data Analytics with AI Internship
