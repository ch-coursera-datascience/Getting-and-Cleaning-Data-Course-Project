# Getting and Cleaning Data Course Project README

## Project Summary
The purpose of this project was to create an R script named run_analysis that will collect, manipulate, and clean a data set. Specifically, the R script:

1. Merges the training and test sets to create one data set.
2. Extracts only the measurements on the mean and standard deviation for each measurement.
3. Uses descriptive activity names to name the activities in the data set.
4. Appropriately labels the data set with descriptive variable names.
5. Creates a second, independently tidy data set with the average of each variable for each activity and each subject.
    
## Data Set
The data used in this project is from the data sets from the Human Activity Recognition Using Smartphones dataset, located here:

http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones

The R script is prepared to download and unzip the data files, however you can also
download and uzip the data folder manually here:

https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip

A codebook specific to this analysis is provided in this repository, however a detailed summary of all data included in the Human Activity Recognition Using Smartphones dataset is included in the downloaded folder.

## Analysis Files in the Repository
The following files are included in the repository:
    
1. `README.md`: Provides information about the project and analysis file contents.
2. `run_analysis.R`: The R script that downloads, manipulates, and cleans the data to make a tidy data set.
3. `CodeBook.md`: The code book for run_analysis.R which provides information on the data, variables, and calculations used in the R script.
4. `tidy.txt`: The tidy data set produced by run_analysis.R.

## How the code works
The run_analysis r script performs the following to create the final tidy data set:
1. The code loads the necessary packages.
2. If the data is not already downloaded and in the working directory, the code will download and unzip the required data set folder.
3. Next, the code reads the activity and feature label data sets and renames the variables for ActivityId, ActivityType, Id, and FeatureName.
4. The code then reads the test data and merges that data set with the activity labels. The values in the FeatureName column of the features data frame are used to label the columns of the test data. The code also reads in the subject ids for the test data set. The same steps are followed for the train data sets
5. Next, the code merges the test data with the test subject ids, and merges the train data with the train subject ids. Lastly, the code merges the test and the train data to create one tidy data set.
6. Once the data is merged, the code subsets the data to only include SubjectID, ActivityType, and all variables on the mean and standard deviation of the measurements.
7. From the data set created in step 6, the code calculates the average of each variable for each activity and participant.
8. Lastly, the code exports the file tidy.txt with the final tidy data set.
