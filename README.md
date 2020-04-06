# Bioinformatics

Accompanying code for Bioinformatics project. 

The attached Jupyter notebook does the following:

* Load thedataset of protein sequences in FASTA format and labelled with their subcellular location (cytosolic, mitochondrial, nuclear, secreted).

* Explores the dataset, removes outliers and performs extracts 71 protein features using the Biopython library.

* Plots various violin plots, bar graphs and box plots of these extracted features.

* Performs Recursive Feature Extraction (RFE) using the yellowbrick package to remove 6 redundant features. We now have data in the form (X,y) where rows of X are 65 dimensional feature vectors of the training examples, and each entry of y is the associated label. 

* Make an 80/20 train/test split of (X,y) into (X_train,y_train) and (X_test,y_test).

* Construct a variety of classifiers from the sklearn package and perform a 10-fold cross-validation grid search on (X_train,y_train) over the parameter space of each classifier to identify the optimal parameters of each classifier.

* Have each classifier (with its optimal parameters) make a prediction y_pred on each example in X_test. Compare y_pred to the true labels y_test and return the F1 score for each class as well as the accuracy and weighted-average F1 score over all classes.

* Select the best classifier as that with the highest weighted-average F1 score. 

* Display the test set confusion matrix of this best classifier.

* Load the unlabelled protein sequences provided to use in the blind dataset and extract features X_blind from them. Have the best classifier make a prediction of the subcellular location of each of these and return this prediction with an associated confidence in each of these predictions.
