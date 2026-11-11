# Titanic Survival Prediction

**Dasey Dang · UW–Madison · PSYC 752 Machine Learning**  
*First place in the course’s held-out Titanic prediction challenge*

[Project overview](#project-overview) · [Model comparison](#model-comparison) · [Repository files](#repository-files) · [Acknowledgments](#acknowledgments)

---

## Project overview

I used passenger records from the Titanic to predict survival with two classification approaches in R. I explored how to represent passenger characteristics such as age, family size, and ticket information, then compared how those choices affected validation accuracy.

For k-nearest neighbors (KNN), I tested age bands, ticket-prefix groups, and different numbers of neighbors. For discriminant analysis, I tested features including log-transformed fare, whether a passenger traveled alone, and an interaction between sex and passenger class. The interaction let the model represent a different relationship between sex and survival across passenger classes.

## Model comparison

| Model | Configuration | Validation accuracy |
| --- | --- | ---: |
| K-nearest neighbors (KNN) | Age bands and 35 neighbors | **82.1%** |
| Quadratic discriminant analysis (QDA) | Sex-by-passenger-class interaction | **81.3%** |

I submitted the QDA model, fitted through the lab’s regularized discriminant analysis interface, for the course’s held-out test set. That submission placed **first in the class challenge**. The percentages above are from the validation split used during development.

## Repository files

| File | What it contains |
| --- | --- |
| [`eda_cleaning.qmd`](eda_cleaning.qmd) | Exploratory data analysis and data preparation |
| [`fit_knn.qmd`](fit_knn.qmd) | KNN preprocessing recipes, model fitting, and validation results |
| [`fit_rda.qmd`](fit_rda_dang.qmd) | Discriminant analysis recipes, validation results, and held-out prediction code |

The analyses use **R, Quarto, and tidymodels**. Start with the data preparation file, then open the two modeling files. Running the original workflow requires the course-provided Titanic files, including the unlabeled test split.

## Acknowledgments

John Curtin designed the Unit 4 classification assignment and provided the starter Quarto templates for UW–Madison’s PSYC 752 Machine Learning course. I developed the feature recipes, fitted and compared the model configurations, and generated the final held-out predictions.
