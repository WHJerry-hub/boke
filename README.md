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
All source code used to generate the results and figures in the paper are in the `INST0060Group0` folder. The calculations and figure generation are all run inside `terminal` of the Python compiler. Take Visual Studio Code as an example, you need to open the folder in VS code, and open the terminal interface, input the following command:
```bash
python main.py ./original_data/application_record.csv ./original_data/credit_record.csv processed_data.csv ./data_preprocess_result ./derived_dataset/balanced_data.csv ./smote_result ./over_sampling_result ./under_sampling_result
```
For input command, the format should be: main.py [-h] [--target_column TARGET_COLUMN] [--random_state RANDOM_STATE] application_file credit_file output_file output_path balance_output_path output_path_smote output_path_over output_path_under.
- application_file:

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
