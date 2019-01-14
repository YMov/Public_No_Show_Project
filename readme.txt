We will use data from the following Kaggle dataset: https://www.kaggle.com/joniarroba/noshowappointments.
The goal here is to predict patients that will not show up for medical appointments based on their medical records. This project does have 3 parts:

Part I - Data Prep:
    1-Reading in data csv file
    2-Cleanup data column names
    3-Remove records with erroneous entries (e.g., negative ages, look at what people have done in Kaggle)
    4-Create a test set of 20k records that you won’t touch again for the reminder of this project until Part III. Use stratified sampling on the No-show variable to ensure test set and training set class proportions are the same. Save the train and test sets as csv files in the processed_data directory.
    5-Plot the No-show variable against the other variables in the dataset as part of Exploratory Data Analysis (USE THE TRAINING SET FOR THIS!!)
    6-Create a preprocessing pipeline using scikit to prepare the data for the ML algorithms we will use. At a minimum, standardize numerical variables, transform categorical variables into one or more numerical values. You may apply other transformations that you think would be useful (e.g., logarithmic transformations).
    


Part II: Classification Methods

    1-Using sklearn fit a DecisionTree, a RandomForest, a linear SVM and an SVM with a radial basis kernel to the transformed data. For now, use default parameters for each method.
    2-Use 10 fold cross validation to estimate performance of each of the above methods using both accuracy and AUC as metrics Report your estimated performances. Should you use accuracy or AUC as a metric for this task?
    3-Based on the above choose two of the ML methods and fit a model using 5 fold cross validation for model selection and 10 fold cross validation for model assessment. Report estimated performance for the tuned classifiers.
    Implement gradient descent for a linear svm and test it on the training set. How did its performance compare to the above?
    
    
    
Part III: Ensembles and Final Result


    1-Train an AdaBoost classifier and compare its performance to the results obtained in Part II using 10 fold cross validation as before
    2-Train an xgBoost classifier and compare its performance to the results obtained in Part II
    3-Choose a set of 5 or so classifiers, e.g., Decision Trees of diverse depths, linear SVMs over diverse subsets of features, RBF kernels with diverse bandwidths, Random Forests with diverse number of trees in their ensemble, be creative!.    Write a function that given a training set does the following:
        A-Creates a validation set using 20% of the training set
        B-Trains each of your chosen classifiers on the training set
        C-Using the validation set creates a new dataset where features are predictions made by each of your chosen classifiers
        D-Trains a logistic regression classifier to blend the predictions
        
    4-Compare its performance to the results obtained in Part II using 10 fold cross validation.
