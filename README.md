# Tidy Data Assignment UCI HAR Data set
Vinod
_11th June 2017_

This repository has been prepared as part of the assignment on tidying data.
The data shared as per assignment has been processed and the final data (tidy) , R script for processing and Codebook shared. This README file 

## Data for assignment

This script uses the data from UC Irvine's Human Activity Recognition Using Smartphones Data Set. The data used is here:

https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip

More information about the data can be found here:

http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones

## Data set Information

The experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope, we captured 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz. The experiments have been video-recorded to label the data manually. The obtained dataset has been randomly partitioned into two sets, where 70% of the volunteers was selected for generating the training data and 30% the test data.

The sensor signals (accelerometer and gyroscope) were pre-processed by applying noise filters and then sampled in fixed-width sliding windows. From each window, a vector of features was obtained by calculating variables from the time and frequency domain.

**Information in files as zip**

_SUBJECT FILES
test/subject_test.txt
train/subject_train.txt
ACTIVITY FILES
test/X_test.txt
train/X_train.txt
DATA FILES
test/y_test.txt
train/y_train.txt_

_features.txt - Names of column variables in the dataTable_

_activity_labels.txt - Links the class labels with their activity name_

## Assignment Objectives
Create one R script called run_analysis.R that does the following.

- Merges the training and the test sets to create one data set.
- Extracts only the measurements on the mean and standard deviation for each measurement.
- Uses descriptive activity names to name the activities in the data set
- Appropriately labels the data set with descriptive variable names.
- From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject.


## Artifacts in repo

- run_analysis.R : R file which does the processing
- tidydata.txt : the merged data set which provides subject, activity description and the mean and standard deviation values for test and train observations
- averages.txt : tidy data set with the average grouped by variable, activity and subject
- codebook.md : Code book for the data and process


## Processing by R script
_Load Data_
- Load library dplyr and reshape2. 
- Use "read.table" to read the txt files provided

_Include descriptive activity names to name the activities in the data set_
- Use activity names from activity_labels.txt

_Label the data set with descriptive variable names_
- Include descriptive variable name for Subject and features. Use details in features.txt

_Merge data and extract only mean and standard deviation variables_
- RBIND train and test data
- Prepare final data set by selecting Subject, Activity and other variables which have mean() and std()

_Prepare second data set which provides averages by variable, activity and subject_
- Data is melted and recast as a set of the means of the columns per subject per activity with reshaper2 to a new data set 



