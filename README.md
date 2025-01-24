# **Credit Card Approval Prediction**

In this project, we downloaded relevant data about credit card from kaggle (https://www.kaggle.com/datasets/rikdifos/credit-card-approval-prediction/data?select=credit_record.csv), first preprocessed the data, splited the target column (" risk "), then divided the data set into a balanced subset, and selected the model by balancing the dataset. Then the pre-processed dataset was divided into 5 sub-data sets with different imbalance proportions, and then the strategies of oversampling, undersampling and SMOTE sampling were adopted for each imbalance dataset, finally the sampled data set was evaluated on the selected model.

---

## **Table of Contents**

- [Overview](#overview)
- [Software Implementation](#software-implementation)
- [Requirements](#requirements)
- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Results](#results)
- [Contributing](#contributing)
- [License](#license)

---

## **Overview**

The entire code contains 9 different .py files, which are used for data preprocessing, creating subdata sets, model selection, grid search (model hyperparameter selection), oversampling, undersampling, SMOTE sampling, model evaluation. Finally, the whole project is implemented by calling functions in different .py files through the main.py file.

---

## **Software Implementation**

- Feature 1: Brief description
- Feature 2: Brief description
- Feature 3: Brief description

---

## **Requirements**

This project requires the following dependencies:
- `numpy`
- `pandas`
- `scikit-learn`
- `matplotlib`

To install the required dependencies, run:
```bash
pip install -r requirements.txt
