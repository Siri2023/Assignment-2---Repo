# Creating a Pipeline Using Pycaret3
## Introduction
## Data
The link for the dataset used in creating this pipeline can be found here: https://archive.ics.uci.edu/ml/datasets/Breast+Cancer+Wisconsin+%28Diagnostic%29
## Steps
Data loading: First, we load the "Breast Cancer Wisconsin (Diagnostic)" dataset from the UCI Machine Learning Repository using Pandas.  

![image](https://user-images.githubusercontent.com/123089800/233313685-f145f526-cf43-409f-b906-675a72fac0cd.png)

Environment setup: We set up the Pycaret environment using setup(). We pass in our dataset, specify the target column ('diagnosis'), and set the train_size parameter to 0.7 to split the data into 70% for training and 30% for testing. We also set silent to True to suppress some of the output, and we set log_experiment and log_plots to True to log the experiment and the plots, respectively.  

![image](https://user-images.githubusercontent.com/123089800/233314164-78231ea7-e1cd-4eef-8e62-b4f55fe2e109.png)

Model comparison: We compare the performance of various models using compare_models(). We set fold to 5 to perform 5-fold cross-validation and we sort the models by F1 score. compare_models() returns the best performing model based on the evaluation metric (F1 score in this case).  

![image](https://user-images.githubusercontent.com/123089800/233314304-0dcd0205-391a-40dc-8186-19dd2f48e86f.png)  


Hyperparameter tuning: We tune the hyperparameters of the best model using tune_model(). We set optimize to 'F1' to optimize for F1 score and we set n_iter to 50 to perform 50 iterations of hyperparameter tuning. We also set search_library to 'optuna' to use Optuna as the search library.  

![image](https://user-images.githubusercontent.com/123089800/233314482-f8fc8175-8f36-48b9-8bb6-2b017e23fb9b.png)
Ensemble model: We ensemble the tuned model using ensemble_model(). We set fold to 5 to perform 5-fold cross-validation and we set method to 'Bagging' to use bagging as the ensemble method.  

![image](https://user-images.githubusercontent.com/123089800/233314619-bd3397cb-928d-43f7-bf6d-ee6640358a3e.png)
