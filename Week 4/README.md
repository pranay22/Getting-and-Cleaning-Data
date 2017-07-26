Repository containing code and data files for Course project of Getting and Cleaning Data offered by Johns Hopkins University through Coursera.    

## Course Project
Submission requirement: Copies of all important files and datasets are there in this directory.  

## How to Run  

* Unzip the source dataset (https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip) in a local foler    

* Put run_analysis.R into the same folder  

* In RStudio: 
  1. setwd(<folder_name>)   
  2. source("run_analysis.R")    

* Reading Data: data <- read.table("dataset_with_avg.txt")  

That would be 180x68 because there are 30 subjects and 6 activities, thus "for each activity and each subject" means 30 * 6 = 180 rows.
