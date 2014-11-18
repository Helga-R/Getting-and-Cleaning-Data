Getting-and-Cleaning-Data
=========================

Getting and Cleaning Data - Project Course

Introduction

The code contained in this repository was written for the final project for Coursera's Getting and Cleaning Data Course.
This script uses the Human Activity Recognition Using Smartphones Dataset of which the original dataset and its description can be found here:

http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones

The project data can be found on:

https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip

The purpose of this request is to create an R script called run_analysis.R that does the following. 
1.	Merges the training and the test sets to create one data set.
2.	Extracts only the measurements on the mean and standard deviation for each measurement. 
3.	Uses descriptive activity names to name the activities in the data set
4.	Appropriately labels the data set with descriptive variable names. 
5.	From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject.

About the raw data

The features (561 of them) are unlabeled and can be found in x_test.txt. The activity labels are in the y_test.txt file. The test subjects are in the subject_test.txt file.
The training set are also unlabeled and can be found in x_train.txt. The activity labels are in the y_train.txt. The test subjects are located in the subject_tect.txt.

Process the data

This script creates two separate data sets as output and stores the files in the output directory.

tidy.txt
The original data set separated participants into test and train groups. That makes it necessary to merge the test and train data into a single data set which is done using the row bind. 

Since the operations in the second data set are only concerned with the mean and standard deviation for each measurement, the mean() and std() features from the list of 17 signals in features_info.txt in the original data set were selected - 8 with XYZ 3-axial signals (8 * 3 * 2 = 48) and 9 magnitudes (9 * 2 = 18) for a total of 66 features extracted. Extracting the features with 'mean()' and 'std()' in the feature name seemed to accomplish this.
The original data set coded the six activities as 1-6 so it was necessary to use activity_labels.txt from the original data set to get human-readable names of the activities. 
To avoid impossibly long feature names it was decided the original feature names were sufficiently descriptive. The original feature names were used for the tidy data set in lower case minus the special characters '(', ')' and '-'.

tidy-avg.txt
Finally, the script calculates the average of each mean and standard deviation feature for each activity and each subject. This was most easily accomplished using the melt and cast functions in the Hadley Wickham's reshape2 package.

Expected output

Two new files will be written to the output directory.
1.	tidy.txt
2.	tidy-avg.txt
Both files are read into R with read.table using a header attribute set to TRUE.

How to run the script
The script is written in the R statistical programming language. It is assumed that the working directory has been set to the root of the repository.

The dataset as downloaded on Wed Jun 18, 2014 has been included in the repository in the data folder. If the dataset should be updated in the future it should be sufficient to delete or rename the data folder. The new dataset will be downloaded the next time the script is run.

The script relies on the following packages which must be installed prior to running the script:
•	reshape2

License:
Use of this dataset in publications must be acknowledged by referencing the following publication :
Davide Anguita, Alessandro Ghio, Luca Oneto, Xavier Parra and Jorge L. Reyes-Ortiz. Human Activity Recognition on Smartphones using a Multiclass Hardware-Friendly Support Vector Machine. International Workshop of Ambient Assisted Living (IWAAL 2012). Vitoria-Gasteiz, Spain. Dec 2012


