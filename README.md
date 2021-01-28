# PACE-ML: Feature Selection

## Product overview

PACE-ML Feature Selection will run machine learning related feature selection operations on the user provided data. The feature selection tasks to execute on the data can be provided by user in a separate config file. This will simplify the task of feature selection for a data scientist where in the user will only have to specify select few parameter to generate the correct output instead of writing specific code for each individual feature selection tasks.

## Product Highlight

* This solution will provide the relevant and optimal features after running the user specified feature selection operations.
* This solution saves a significant amount of time spent over developing and running different feature selection operations on the user data.
* PACE - ML is Mphasis Framework and Methodology for end-to-end machine learning development and deployment. PACE-ML enables organizations to improve the quality & reliability of the machine learning solutions in production and helps automate, scale, and monitor them. Need customized Machine Learning and Deep Learning solutions? Get in touch!

## Amazon Marketplace Link
The product can be found [here](https://aws.amazon.com/marketplace/pp/prodview-grip2ega2nrya)

## Usage Instruction
### Input Schema
This algorithm takes a zip file as an input. This zip file should contain exactly two files:
1. Data.csv – This will be the data on which feature selection is to be done.
2. Config.json – This file should contain parameters specific to feature selection tasks to be executed on the supplied data. The available parameter are as follows with their available values:
* Target_variable: specify the target variable from the input dataset
* Apply_feature_selection: If feature selection should be applied on the provided data. Boolean: True/False
* Feature_selections_top_features_to_keep: Can be a value between 0 to 1. 
* Feature_selection_method: Which feature selection method to use. Can be one of: classic, boruta 
* Remove_multicollinearity: Whether multicollinearity should be removed from the data. Boolean: True/False
* Maximum_correlation: Sets the threshold for features to drop while using remove multicollinearity function
* Apply_pca: Whether PCA should be applied on the provided data. Boolean: True/False
* Pca_method: Can be one of: linear, kernel, incremental
* Pca_variance_retained_or_number_of_components: Can be a value between 0 to 1. Specifies the amount of variance retained

**A sample config.json can be found below :**
```
{
  "target_variable": "",
  "feat_selection": {
    "apply_feature_selection": false,
    "feature_selections_top_features_to_keep": 0.8,
    "feature_selection_method": "classic",
    "remove_multicollinearity": false,
    "maximum_correlation": 0.9,
    "apply_pca": false,
    "pca_method": "liner",
    "pca_variance_retained_or_number_of_components": 0.99
  }
}
```
### Output Schema
The output will be the modified data in the form of a CSV file with the relevant features
