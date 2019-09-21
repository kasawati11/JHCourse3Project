The run_analysis.R script prepares the data then follows the 5 steps required by course project outline.
Merges the training and the test sets to create one data set.
Extracts only the measurements on the mean and standard deviation for each measurement.
Uses descriptive activity names to name the activities in the data set
Appropriately labels the data set with descriptive variable names.
From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject.
1) Downloaded the dataset
Dataset downloaded and extracted under the folder called UCI HAR Dataset
2) Datasets were assigned to variables
features <- features.txt : 561 rows, 2 columns
The features selected for this database come from the accelerometer and gyroscope 3-axial raw signals tAcc-XYZ and tGyro-XYZ.
activities <- activity_labels.txt : 6 rows, 2 columns
List of activities performed when the corresponding measurements were taken and their labels
subject_test <- test/subject_test.txt : 2947 rows, 1 column
contains test data of 9/30 volunteer test subjects
x_test <- test/X_test.txt : 2947 rows, 561 columns
contains recorded features test data
y_test <- test/y_test.txt : 2947 rows, 1 columns
contains test data of activities code labels
subject_train <- test/subject_train.txt : 7352 rows, 1 column
contains train data of 21/30 volunteer subjects 
x_train <- test/X_train.txt : 7352 rows, 561 columns
contains recorded features train data
y_train <- test/y_train.txt : 7352 rows, 1 columns
contains train data of activities code labels
3) Merged the _train and the _test sets to create one data set
X (10299 rows, 561 columns) is created by merging x_train and x_test using rbind() function
Y (10299 rows, 1 column) is created by merging y_train and y_test using rbind() function
Subject (10299 rows, 1 column) is created by merging subject_train and subject_test using rbind() function
Merged_Data (10299 rows, 563 column) is created by merging Subject, Y and X using cbind() function
TidyData (10299 rows, 88 columns) is created by subsetting Merged_Data, by selecting the columns: subject, code and measurements on the mean and standard deviation for each measurement
 
4) Appropriately labels the data set with descriptive variable names
All start with character f in column’s name replaced by Frequency
All start with character t in column’s name replaced by Time
All Acc in column’s name replaced by Accelerometer
All BodyBody in column’s name replaced by Body
All Mag in column’s name replaced by Magnitude
All Gyro in column’s name replaced by Gyroscope
5) From the data set in step 4, created a second, independent tidy data set with the average of each variable for each activity and each subject
FinalData (180 rows, 88 columns) was created by taking the means of each variable for each activity and each subject, after grouping them by subject and activity.
Exported FinalData into tidyData.txt file.

