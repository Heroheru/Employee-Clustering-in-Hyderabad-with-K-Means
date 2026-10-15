# Employee Segmentation in Hyderabad with K-Means

Unsupervised clustering of salaried employees in Hyderabad, based on **salary**, **work experience**, and **education level**. Built as the final project of the Data Science Course at Universitas Gunadarma (Associate Data Scientist scheme, June 2025).

## Goal

Group employees into meaningful segments to support HR decisions on compensation, training, and promotion, using data that has no predefined labels.

## Dataset

[Hyderabad Salaried Employees Dataset](https://www.kaggle.com/datasets/shubamsumbria/hyderabad-salaried-employees-dataset-clustering/data) (Kaggle), about 28.8k records.

## Pipeline

1. **Data understanding**: types, missing values, distributions, Spearman correlation, boxplots
2. **Cleaning**
   - Dropped irrelevant or sparse columns (`candidateName`, `companyName`, `designation`, `qualificationMas2`, `locationCurrentMas`, `Category`)
   - Parsed `salary` (lacs) to float and `experienceMas` to total months
   - Mapped `qualificationMas` to an ordinal scale (0-6)
   - Dropped rows with missing values and handled outliers (about 23.9k rows remain)
3. **Scaling**: `RobustScaler` (median and IQR, resistant to outliers)
4. **Modeling**: K-Means (`k-means++`), k chosen with the elbow method, k = 3
5. **Evaluation and visualization**: Calinski-Harabasz index and a 2D PCA scatter plot

## Result
<img width="712" height="468" alt="image" src="https://github.com/user-attachments/assets/4362bb3b-faf3-4345-8e86-2f69182ce7bd" />

| Metric | Value |
|---|---|
| Clusters (k) | 3 |
| Calinski-Harabasz Index | 11,709.88 |

## Tech Stack

Python, pandas, NumPy, scikit-learn, SciPy, seaborn, matplotlib

## Run It

```bash
pip install pandas numpy scikit-learn scipy seaborn matplotlib
jupyter notebook Template_Final_Project_Kursus_DS__2_.ipynb
```

Download the dataset from Kaggle and save it as `data_salaries.csv` in the same folder as the notebook.
