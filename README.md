# Getting , Cleaning and Performing Analysis on the UCI Smartphone Data Set

## Introduction
The data set used here is from the UCI Machine Learning Repository (Human Activity Recognition Using Smartphones Data Set). A detailed description of the data set can be obtained from [http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones]

The script (run_analysis.R) performs the following activities :
1. Merges the training and the test sets to create one data set.
2. Extracts only the measurements on the mean and standard deviation for each measurement. 
3. Uses descriptive activity names to name the activities in the data set
4. Appropriately labels the data set with descriptive variable names. 
5. From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject.
6. Write the tidy data set created in step 5, to a file

## Script Details
1. The script has 3 functions defined to perfom all the activities :
   * getActivityName : Given an acitivity id , it returns the corresponding activity name . This is used to provide descriptive activity names for the activities in the data set.
   * preProcessDataSet : Appends "subject" and "activity" columns to the input data set ( test and train ). Makes use of 'getActivityName' function to convert activity id to it's corresponding activity name. It also  assigns column headers to the input data set ( test and train ) from the feature vector .
   * runAnalysis : Merges the test and train data sets pre-processed using the "preProcessDataSet" function. Extracts the mean and standard deviation for each measurement . Melts and Casts the data to create an independent tidy data set with the average of each variable for each activity and each subject. Writes the tidy data set to a file . 

## Usage Details
runAnalysis acts like the main method . In order to run the script , invoke "runAnalysis()" from the working directory . The directory containing the data set to be processed must be in the working directory from where the script is invoked . The directory where the data set to be processed is present must be named "UCI HAR Dataset" . The names of the data sets themselves are ( paths mentioned are relative the directory , "UCI HAR Dataset"):
1. test/X_test.txt
2. test/subject_test.txt
3. test/y_test.txt
4. train/X_train.txt
5. train/subject_train.txt
6. train/y_train.txt
