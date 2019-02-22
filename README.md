# Preop Mortality Risk Prediction

This repo is for code used in the Preoperative Surgical Risk Prediction project.

## Setting up the environment 

If you do not have Anaconda installed, first install it as described [here](https://www.anaconda.com/distribution/). 
Once you have Anaconda installed, create the Anaconda environment using the command 
```
conda env create -f environment.yml
```
This should install the packages needed to run the code in this repository. 

## EHR_main.ipynb

This notebook is the primary notebook for filtering the data, training the models, and measuring performance using various methods. To run this notebook, you will need to have a file containing the preoperative surgical data, as well as a file containing the features to use. 

*TODO*: add script for generating feature file, as well as documentation 

## Preop_Mortality_Test.ipynb

*NOTE: this notebok is not finished yet*

Assuming you have a trained model as a pickled file, you can use this notebook to generate predictions on a test set of surgeries. 

## Plot_ROC_curves

Once the predictions have been generated for the various models, this notebook plots the ROC curve and the precision-recall curve for each model over all feature sets. 

## Compare_ROC_AUC.ipynb

This notebook is for comparing the AUROCs generated for different feature sets to see if they are statistically significantly different. 
