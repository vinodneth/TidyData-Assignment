# Code Book - Tidy Data Assignment
_ Vinod
  11th June 2017 _

## Data Provided
This assignment uses the data from UC Irvine's Human Activity Recognition Using Smartphones Data Set. The data used is here:

https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip

More information about the data can be found here:

http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones

The experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope, we captured 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz. The experiments have been video-recorded to label the data manually. The obtained dataset has been randomly partitioned into two sets, where 70% of the volunteers was selected for generating the training data and 30% the test data.

The sensor signals (accelerometer and gyroscope) were pre-processed by applying noise filters and then sampled in fixed-width sliding windows. From each window, a vector of features was obtained by calculating variables from the time and frequency domain.
_** Information in files as zip **

SUBJECT FILES
test/subject_test.txt
train/subject_train.txt
ACTIVITY FILES
test/X_test.txt
train/X_train.txt
DATA FILES
test/y_test.txt
train/y_train.txt

features.txt - Names of column variables in the dataTable

activity_labels.txt - Links the class labels with their activity name._

Description of the DATA
The features selected for this database come from the accelerometer and gyroscope 3-axial raw signals tAcc-XYZ and tGyro-XYZ. These time domain signals (prefix �t� to denote time) were captured at a constant rate of 50 Hz. and the acceleration signal was then separated into body and gravity acceleration signals (tBodyAcc-XYZ and tGravityAcc-XYZ) � both using a low pass Butterworth filter.

The body linear acceleration and angular velocity were derived in time to obtain Jerk signals (tBodyAccJerk-XYZ and tBodyGyroJerk-XYZ). Also the magnitude of these three-dimensional signals were calculated using the Euclidean norm (tBodyAccMag, tGravityAccMag, tBodyAccJerkMag, tBodyGyroMag, tBodyGyroJerkMag).

A Fast Fourier Transform (FFT) was applied to some of these signals producing fBodyAcc-XYZ, fBodyAccJerk-XYZ, fBodyGyro-XYZ, fBodyAccJerkMag, fBodyGyroMag, fBodyGyroJerkMag. (Note the �f� to indicate frequency domain signals).

Description of abbreviations of measurements

leading t or f is based on time or frequency measurements.
Body = related to body movement.
Gravity = acceleration of gravity
Acc = accelerometer measurement
Gyro = gyroscopic measurements
Jerk = sudden movement acceleration
Mag = magnitude of movement
mean and SD are calculated for each subject for each activity for each mean and SD measurements.
The units given are g�s for the accelerometer and rad/sec for the gyro and g/sec and rad/sec/sec for the corresponding jerks.

These signals were used to estimate variables of the feature vector for each pattern:
�-XYZ� is used to denote 3-axial signals in the X, Y and Z directions. They total 33 measurements including the 3 dimensions - the X,Y, and Z axes.

tBodyAcc-XYZ
tGravityAcc-XYZ
tBodyAccJerk-XYZ
tBodyGyro-XYZ
tBodyGyroJerk-XYZ
tBodyAccMag
tGravityAccMag
tBodyAccJerkMag
tBodyGyroMag
tBodyGyroJerkMag
fBodyAcc-XYZ
fBodyAccJerk-XYZ
fBodyGyro-XYZ
fBodyAccMag
fBodyAccJerkMag
fBodyGyroMag
fBodyGyroJerkMag
The set of variables that were estimated from these signals are:

mean(): Mean value
std(): Standard deviation


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