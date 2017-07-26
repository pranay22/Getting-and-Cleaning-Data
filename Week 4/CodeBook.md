CodeBook
========================

Original Data Source: https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip  

The attached R script (run_analysis.R) performs the following tasks while cleaning up the data:  

* It merges training and test set and creates one data set: train/X_train.txt with test/X_test.txt; the result is a 10299x561 data frame. That is same as the original description ("Number of Instances: 10299" and "Number of Attributes: 561"), train/subject_train.txt with test/subject_test.txt; the result is a 10299x1 data frame with subject IDs, and train/y_train.txt with test/y_test.txt, the result is also a 10299x1 data frame with activity IDs.  

* It reads features.txt and extracts only the measurements on the mean and standard deviation for each measurement. Result is a 10299x66 data frame, because only 66 out of 561 attributes are measurements on the mean and standard deviation. All measurements appear to be floating point numbers in the range (-1, 1).  

* It reads activity_labels.txt and applies the following descriptive activity names to name the activities in the data set:  

        walking  
        
        walkingupstairs  
        
        walkingdownstairs  
        
        sitting  
        
        standing  
        
        laying  

* It labels the data set with descriptive names: all feature names (attributes) and activity names are converted to lower case, underscores and brackets () are removed. Then the merging: It merges the 10299x66 data frame containing features with 10299x1 data frames containing activity labels and subject IDs. Result is saved as merged_clean_data.txt which is a 10299x68 data frame such that the first column contains subject IDs, the second column activity names, and the last 66 columns are measurements. Subject IDs are integers between 1 and 30 inclusive. Names of the attributes are similar to the following:  

        tbodyacc-mean-x   
        
        tbodyacc-mean-y   
        
        tbodyacc-mean-z   
        
        tbodyacc-std-x  
        
        tbodyacc-std-y  
        
        tbodyacc-std-z  
        
        tgravityacc-mean-x  
        
        tgravityacc-mean-y  

* Finally, the script creates another independent tidy data set with the average of each measurement for each activity and each subject. The result is saved as data_set_with_the_averages.txt, a 180x68 data frame. There, just as before, the first column contains subject IDs, the second column contains activity names, and the averages for each of the 66 attributes are in columns 3...68. There are 30 subjects and 6 activities, so there are 180 rows in this data set with averages.  
