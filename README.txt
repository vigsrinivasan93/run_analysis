The run_analysis function has a single input: the filename of the zip file (it has a set default value of Coursera_DS3_Final.zip).

The function then performs the following 4 steps:

1. Check if file exists 

Checks if the file exists in the current working directory. If it doesn't, it downloads the file from using the link(https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip). This file is then unzipped.

2. Read table data and assign column names

Read table data from the list of features, activities and the subjects (both test and train subjects). It also reads the test and train data for x and y.
Data on the trained and test subjects from both groups (x and y) are merged along with the subject names in both groups.

The mean and standard deviation data for each activity by subject is then isolated from this data set (called TidyData.

3. Column naming

The column names of the merged dataset are still relatively unclean. Clean names are assigned to each column using regular expressions (eg. any column which has "Acc" will be named "Accelerometer"  

4. Creating FinalData.txt

The clean dataset is summarised using the summarise_all and list functions of dplyr. A new file called FinalData.txt is created in the working directory containing the mean and standard deviation of each of the activities using the write.table function (keeping row.names = FALSE)

