CodeBook.md

This file describes the variables, data and transformations contained or carried out in this project.

•	The required data was downloaded from: https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip

•	The data was obtained from: http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones




run_analysis.R

•	The X_train.txt, y_train.txt and subject_train.txt files from the “./data/train” folder were read and stored in trainData, trainLabel and trainSubject variables.

•	The X_test.txt, y_test.txt and subject_test.txt files from the “.data/test” folder were read and stored in testData, testLabel and testSubject variables.

•	The elements testData and trainData were concatenated to create a data frame comprising 10299 rows and 561 columns called joinData.

•	The elements testLabel and trainLabel were concatenated to create a data frame comprising 10299 rows and 1 column called joinLabel.

•	The elements testSubject and trainSubject were concatenated to create a data frame comprising 10299 rows and 1 column called joinSubject.

•	The features.txt file from the “/data” folder was read and stored in a variable called features. Measurements on the mean and standard deviation were extracted resulting in a 66 indices list and a subset of joinData was obtained with the 66 corresponding columns.

•	The column names of the subset were cleaned up by removing the “()” and “-“ symbols from the names and capitalising the first letters of “mean” and “std”.

•	The activity_labels.txt file from the “./data” folder was read and stored in a variable called activity.

•	The activity names in the second column of activity were changed to all lowercase. Where underscores existed between letters, the underscore was removed and the letter immediately following the underscore was capitalised. 

•	The values of joinLabel were transformed according to the activity data frame.

•	The columns of joinSubject, joinLabel and joinData were concatenated to get a new data frame with 10299 rows and 68 columns called cleanedData.  The first two columns were named “subject” and “activity” – the “subject” column containing integers from 1 to 30; the “activity” column containing 6 different activity names. The last 66 columns contain measurements ranging from -1 to 1.

•	The merged_data.txt file was created from cleanedData.

•	Another dataset was created with the average of each measurement for each activity and each subject. With 30 unique subjects and 6 unique activities there are 180 combinations of subject and activity. After initialising the result data frame and using the nested for loops, a data frame was obtained with 180 rows and 68 columns.

•	The data_with means.txt file was created from result.




merged_data.txt

•	contains 10299 rows and 68 columns in text format

variables:

•	subject

•	activity

•	tBodyAccMeanX

•	tBodyAccMeanY

•	tBodyAccMeanZ

•	tBodyAccStdX

•	tBodyAccStdY

•	tBodyAccStdZ

•	tGravityAccMeanX

•	tGravityAccMeanY

•	tGravityAccMeanZ

•	tGravityAccStdX

•	tGravityAccStdY

•	tGravityAccStdZ

•	tBodyAccJerkMeanX

•	tBodyAccJerkMeanY

•	tBodyAccJerkMeanZ

•	tBodyAccJerkStdX

•	tBodyAccJerkStdY

•	tBodyAccJerkStdZ

•	tBodyGyroMeanX

•	tBodyGyroMeanY

•	tBodyGyroMeanZ

•	tBodyGyroStdX

•	tBodyGyroStdY

•	tBodyGyroStdZ

•	tBodyGyroJerkMeanX

•	tBodyGyroJerkMeanY

•	tBodyGyroJerkMeanZ

•	tBodyGyroJerkStdX

•	tBodyGyroJerkStdY

•	tBodyGyroJerkStdZ

•	tBodyAccMagMean

•	tBodyAccMagStd

•	tGravityAccMagMean

•	tGravityAccMagStd

•	tBodyAccJerkMagMean

•	tBodyAccJerkMagStd

•	tBodyGyroMagMean

•	tBodyGyroMagStd

•	tBodyGyroJerkMagMean

•	tBodyGyroJerkMagStd

•	fBodyAccMeanX

•	fBodyAccMeanY

•	fBodyAccMeanZ

•	fBodyAccStdX

•	fBodyAccStdY

•	fBodyAccStdZ

•	fBodyAccJerkMeanX

•	fBodyAccJerkMeanY

•	fBodyAccJerkMeanZ

•	fBodyAccJerkStdX

•	fBodyAccJerkStdY

•	fBodyAccJerkStdZ

•	fBodyGyroMeanX

•	fBodyGyroMeanY

•	fBodyGyroMeanZ

•	fBodyGyroStdX

•	fBodyGyroStdY

•	fBodyGyroStdZ

•	fBodyAccMagMean

•	fBodyAccMagStd

•	fBodyBodyAccJerkMagMean

•	fBodyBodyAccJerkMagStd

•	fBodyBodyGyroMagMean

•	fBodyBodyGyroMagStd

•	fBodyBodyGyroJerkMagMean

•	fBodyBodyGyroJerkMagStd




data_with_means.txt

•	contains 180 rows and 68 columns in text format

variables:

•	subject

•	activity

•	tBodyAccMeanX

•	tBodyAccMeanY

•	tBodyAccMeanZ

•	tBodyAccStdX

•	tBodyAccStdY

•	tBodyAccStdZ

•	tGravityAccMeanX

•	tGravityAccMeanY

•	tGravityAccMeanZ

•	tGravityAccStdX

•	tGravityAccStdY

•	tGravityAccStdZ

•	tBodyAccJerkMeanX

•	tBodyAccJerkMeanY

•	tBodyAccJerkMeanZ

•	tBodyAccJerkStdX

•	tBodyAccJerkStdY

•	tBodyAccJerkStdZ

•	tBodyGyroMeanX

•	tBodyGyroMeanY

•	tBodyGyroMeanZ

•	tBodyGyroStdX

•	tBodyGyroStdY

•	tBodyGyroStdZ

•	tBodyGyroJerkMeanX

•	tBodyGyroJerkMeanY

•	tBodyGyroJerkMeanZ

•	tBodyGyroJerkStdX

•	tBodyGyroJerkStdY

•	tBodyGyroJerkStdZ

•	tBodyAccMagMean

•	tBodyAccMagStd

•	tGravityAccMagMean

•	tGravityAccMagStd

•	tBodyAccJerkMagMean

•	tBodyAccJerkMagStd

•	tBodyGyroMagMean

•	tBodyGyroMagStd

•	tBodyGyroJerkMagMean

•	tBodyGyroJerkMagStd

•	fBodyAccMeanX

•	fBodyAccMeanY

•	fBodyAccMeanZ

•	fBodyAccStdX

•	fBodyAccStdY

•	fBodyAccStdZ

•	fBodyAccJerkMeanX

•	fBodyAccJerkMeanY

•	fBodyAccJerkMeanZ

•	fBodyAccJerkStdX

•	fBodyAccJerkStdY

•	fBodyAccJerkStdZ

•	fBodyGyroMeanX

•	fBodyGyroMeanY

•	fBodyGyroMeanZ

•	fBodyGyroStdX

•	fBodyGyroStdY

•	fBodyGyroStdZ

•	fBodyAccMagMean

•	fBodyAccMagStd

•	fBodyBodyAccJerkMagMean

•	fBodyBodyAccJerkMagStd

•	fBodyBodyGyroMagMean

•	fBodyBodyGyroMagStd

•	fBodyBodyGyroJerkMagMean

•	fBodyBodyGyroJerkMagStd