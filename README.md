# Preop Mortality Risk Prediction

This repo is for code used in the Preoperative Surgical Risk Prediction project. For details, please see our [paper](https://doi.org/10.1016/j.bja.2019.07.030)

Brian L. Hill, Robert Brown, Eilon Gabel, Nadav Rakocz, Christine Lee, Maxime Cannesson, Pierre Baldi, Loes Olde Loohuis, Ruth Johnson, Brandon Jew, Uri Maoz, Aman Mahajan, Sriram Sankararaman, Ira Hofer, Eran Halperin. "An automated machine learning-based model predicts postoperative mortality using readily-extractable preoperative electronic health record data". British Journal of Anaesthesia (2019).

A file containing the column headers is located [here](https://github.com/brianhill11/PreopMortalityPrediction/blob/master/data/main_header.txt). The scripts expect an input file using these column names, as well as pipe (|) delimited features.  

## Testing the model

If you do not have Anaconda installed, first install it as described [here](https://www.anaconda.com/distribution/). 
Once you have Anaconda installed, create the Anaconda environment using the command 
```
conda env create -f test_environment.yml
```
This should install the packages needed to run code for testing the model. 

### Preop_Mortality_Test.ipynb

Assuming you have a trained model as a pickled file, you can use this notebook to generate predictions on a test set of surgeries. 

To run this notebook, you will need to have a file containing the preoperative surgical data, as well as a file containing the features to use. A file containing the column headers is located [here](https://github.com/brianhill11/PreopMortalityPrediction/blob/master/data/main_header.txt).


## Training the model

If you do not have Anaconda installed, first install it as described [here](https://www.anaconda.com/distribution/). 
Once you have Anaconda installed, create the Anaconda environment using the command 
```
conda env create -f train_environment.yml
```
This should install the packages needed to run code for training the model. 

### EHR_main.ipynb

This notebook is the primary notebook for filtering the data, training the models, and measuring performance using various methods. To run this notebook, you will need to have a file containing the preoperative surgical data, as well as a file containing the features to use. A file containing the column headers is located [here].(https://github.com/brianhill11/PreopMortalityPrediction/blob/master/data/main_header.txt)

You will need to update the path to this cloned repo in the notebook (variable named `repo_dir`).

The `exp_prefix` variable sets the feature set to use. For example, setting this variable to `exp_prefix = "preop_no_lab_times"` will use all preoperative features except the lab-time features. 

### Plot_ROC_curves

Once the predictions have been generated for the various models, this notebook plots the ROC curve and the precision-recall curve for each model over all feature sets. 

### Compare_ROC_AUC.ipynb

This notebook is for comparing the AUROCs generated for different feature sets to see if they are statistically significantly different. 
