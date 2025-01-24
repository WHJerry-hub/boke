# **Credit Card Approval Prediction**

In this project, we downloaded relevant data about credit card from kaggle (https://www.kaggle.com/datasets/rikdifos/credit-card-approval-prediction/data?select=credit_record.csv), first preprocessed the data, splited the target column (" risk "), then divided the data set into a balanced subset, and selected the model by balancing the dataset. Then the pre-processed dataset was divided into 5 sub-data sets with different imbalance proportions, and then the strategies of oversampling, undersampling and SMOTE sampling were adopted for each imbalance dataset, finally the sampled data set was evaluated on the selected model.

---

## **Table of Contents**

- [Overview](#overview)
- [Software Implementation](#software-implementation)
- [Functions](#functions)
- [Output](#output)

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
- application_file: The application_record.csv file in the original_data folder is one of our original data.
- credit_file: The credit_record.csv file in the original_data folder is one of our original data.
- output_file: Save the preprocessed data as a new csv file 'processed_data.csv'.
- output_path: Save the new 'processed_data.csv' in the folder 'data_preprocess_result'.
- balance_output_path: Save the generated balancer data as 'balanced_data.csv' and store it in the 'derived_dataset' folder.
- output_path_smote: Store SMOTE sampling results in the 'smote_result' folder.
- output_path_over: Store Over sampling results in the 'over_sampling_result' folder.
- output_path_under: Store Under sampling results in the 'under_sampling_result' folder.

---

## **Functions**

This project requires the following dependencies:
- `numpy`
- `pandas`
- `scikit-learn`
- `matplotlib`
- `argparse`

There are important function .py file：<br>
**data_preprocess.py**:
- `load_application_data(file_path)`: Upload application dataset.
- `load_credit_data(file_path)`: Upload credit dataset.
- `preprocess_data(application_data, credit_data)`: The data of the two csv of the original data, label encoding, the creation of new features, and the classification of the target column "risk" by weight calculation and classification based on credit score were carried out.
- `plot_score_distribution(data, output_path)`: Draw the figure of 'Score Weighted Sum Distribution'.
- `save_data(data, output_path, filename)`: save the data to the specified path.
- `data_pipeline(application_file, credit_file, output_file, output_path)`: Call all the previous functions to implement the entire preprocessing process, which is convenient to call in the main.py file.

**model_selection.py**:
- `model_case_1(input_file)`: The training set and test set were divided, and the cross check with fold of 3 was adopted to obtain the average score of the cross check and the accuracy of the test set.
- `model_case_2(input_file, random_state=42, test_size=0.2, n_splits=3)`: Standardization is introduced based on case 1.
- `model_case_3(input_file, random_state=42, test_size=0.2, n_splits=3)`: Based on case2, the best hyperparameters obtained by grid search are applied.

**grid_search.py**:
- `cross_validate(model, X, y, cv=3)`: The data is divided into cv folds, and one fold is selected as the verification set each time, and the other folds are used as the training set to evaluate the performance of the model. By loop training the model and predicting on the verification set, the accuracy of each verification is calculated, and finally the average accuracy of all folds is returned as the overall performance indicator of the model.
- `grid_search(model_class, param_grid, X, y, cv=3)`: Evaluate model performance using cross-validation by traversing all parameter combinations in the parameter grid to find the combination of parameters that gives the model the highest score. Returns the best parameter combination (best_params) and the corresponding highest cross-validation average score (best_score), and prints the score for each parameter combination.
- `search_hyper(input_file, target_column='risk', split_ratio=0.8, random_state=42, cv=3)`:Call all the previous functions to implement the entire grid search process, which is convenient to call in the main.py file.

---
## **Output**
By calling the main.py file in terminal and entering the corresponding instructions, the entire process of the project will be run. First, conduct data preprocessing, store processed_data.csv obtained after preprocessing in the corresponding folder, then obtain the balanced data subset, save it as balanced_data.csv and store it in the corresponding folder, and then give SMOTE, Over, smote, smote, smote, smote, smote, smote, smote, smote, smote, smote, smote, smote, smote. under sampling, the MLP model was selected (3 cases), and the sampled data set was placed on the MLP model for evaluation. The accuracy of each evaluation will be displayed in the terminal interface, and 4 images will be obtained at the same time (when the image pops up, remember to close the image to ensure the normal operation of the program). The overall running time was 14 min 32 seconds.
