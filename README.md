The original Data was sourced from:

http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones 

The following details were obtained from that source. To quote from it directly, it provides and overview of the full data set and how it was derived.


==================================================================
Human Activity Recognition Using Smartphones Dataset
Version 1.0
==================================================================
Jorge L. Reyes-Ortiz, Davide Anguita, Alessandro Ghio, Luca Oneto.
Smartlab - Non Linear Complex Systems Laboratory
DITEN - Universit� degli Studi di Genova.
Via Opera Pia 11A, I-16145, Genoa, Italy.
activityrecognition@smartlab.ws
www.smartlab.ws
==================================================================

The experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope, we captured 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz. The experiments have been video-recorded to label the data manually. The obtained dataset has been randomly partitioned into two sets, where 70% of the volunteers was selected for generating the training data and 30% the test data. 

The sensor signals (accelerometer and gyroscope) were pre-processed by applying noise filters and then sampled in fixed-width sliding windows of 2.56 sec and 50% overlap (128 readings/window). The sensor acceleration signal, which has gravitational and body motion components, was separated using a Butterworth low-pass filter into body acceleration and gravity. The gravitational force is assumed to have only low frequency components, therefore a filter with 0.3 Hz cutoff frequency was used. From each window, a vector of features was obtained by calculating variables from the time and frequency domain. See 'features_info.txt' for more details. 


run_analysis.R produces a tidy data set using the following steps

1.   Read the test data X which gives the measures for each variable
2.   Read the test data Y gives a numeric value 1:6 for each activity
3.   Convert each of the numbers 1:6 to it description (walking, walkingupstairs, walkingdownstairs, sitting, standing, and laying)
4.   Read the test subjects which were selected from the original subjects 1:30  
5.   Merge the test data into a single data set.
6.   Repeat steps 1 to 5 with the training data to produce a single training data set
7.   Merge the training data set and the test data set into a single data frame
8.   Change the names of the column headings to those provided by �features.txt�, with the addition of two more variables, subjects and activities.
9.   Select using 'grep' only those variables that refer to mean or standard deviation.
10.  Identified that freqMean was also included, identified which columns contained this variable and removed them from the data frame
11.  Establish the mean and standard deviationof each variable for each activity and each subject using the plyr package, this needs to installed and loaded. The tool that was used 'numcolwise' 
12.  Change the names of each of the column headings to remove '-' and '()'.  Retained capital within the names because it made it easier to identify the variables in line with the information provided above.
13.  Save the file to the working folders as a txt file.
14.  Print the name of the file, and then the file itself to the console.


run_analysis can be run from the working directory, but relies upon the zip file being extracted to the working directory without any changes.  The folder UCI HAR Dataset should contain the test and training data.

When you run run_analysis, it is worth noting that that due to the size of the data sets it takes a couple of minutes to complete the work.
run_analysis is combined into a single program, so when loaded it performs all the required manipulation. It should run automatically.  If this fails enter  "run_analysis" (without quotation marks)on a command line and press return.


CodeBook.md provides details of the variable names.
run_analysis.docx provides the code, comments on the steps similar to the above and a print out of the tidy data.

