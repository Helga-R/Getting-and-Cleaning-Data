CodeBook for the tidy dataset

Data source
This dataset is derived from the "Human Activity Recognition Using Smartphones Data Set" which was originally made available 
here: http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones

Feature Selection

To learn more about the dataset I refer to the README and features.txt files in the original dataset to learn more about 
the feature selection for this dataset. And there you will find the follow description:
The features selected for this database come from the accelerometer and gyroscope 3-axial raw signals tAcc-XYZ and tGyro-XYZ. 
These time domain signals (prefix 't' to denote time) were captured at a constant rate of 50 Hz. Then they were filtered 
using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise. 
Similarly, the acceleration signal was then separated into body and gravity acceleration signals (tBodyAcc-XYZ and 
tGravityAcc-XYZ) using another low pass Butterworth filter with a corner frequency of 0.3 Hz. 
Subsequently, the body linear acceleration and angular velocity were derived in time to obtain Jerk signals (tBodyAccJerk-XYZ 
and tBodyGyroJerk-XYZ). Also the magnitude of these three-dimensional signals were calculated using the Euclidean norm
(tBodyAccMag, tGravityAccMag, tBodyAccJerkMag, tBodyGyroMag, tBodyGyroJerkMag). 
Finally a Fast Fourier Transform (FFT) was applied to some of these signals producing fBodyAcc-XYZ, fBodyAccJerk-XYZ, 
fBodyGyro-XYZ, fBodyAccJerkMag, fBodyGyroMag, fBodyGyroJerkMag. (Note the 'f' to indicate frequency domain signals). 
The reasoning behind my selection of features is that the assignment explicitly states "Extracts only the measurements 
on the mean and standard deviation for each measurement." To be complete, I included all variables having to do with 
mean or standard deviation.

In short, for this derived dataset, these signals were used to estimate variables of the feature vector for each pattern:
'-XYZ' is used to denote 3-axial signals in the X, Y and Z directions.
•	tBodyAcc-XYZ
•	tGravityAcc-XYZ
•	tBodyAccJerk-XYZ
•	tBodyGyro-XYZ
•	tBodyGyroJerk-XYZ
•	tBodyAccMag
•	tGravityAccMag
•	tBodyAccJerkMag
•	tBodyGyroMag
•	tBodyGyroJerkMag
•	fBodyAcc-XYZ
•	fBodyAccJerk-XYZ
•	fBodyGyro-XYZ
•	fBodyAccMag
•	fBodyAccJerkMag
•	fBodyGyroMag
•	fBodyGyroJerkMag

The set of variables that were estimated (and kept for this assignment) from these signals are: 
•	mean(): Mean value
•	std(): Standard deviation

Additional vectors obtained by averaging the signals in a signal window sample. These are used on the angle() variable:
•	gravityMean
•	tBodyAccMean
•	tBodyAccJerkMean
•	tBodyGyroMean
•	tBodyGyroJerkMean

Other estimates have been removed for the purpose of this excercise.
Note: features are normalized and bounded within [-1,1].
The resulting variable names are of the following form: tbodyaccmeanx, which means the mean value of tBodyAcc-XYZ.

Full file layout Tidy Data Set 1
Label                          Type        Description
------------------------------------------------------------------------------------------
subject                        integer     Number representing the subject participant in the experiment.
activity.label                 factor      Factor representing the activity performed by the subject. participant.
tbodyacc.mean.x                numeric     
tbodyacc.mean.y                numeric     
tbodyacc.mean.z                numeric     
tbodyacc.std.x                 numeric     
tbodyacc.std.y                 numeric     
tbodyacc.std.z                 numeric     
tgravityacc.mean.x             numeric     
tgravityacc.mean.y             numeric     
tgravityacc.mean.z             numeric     
tgravityacc.std.x              numeric     
tgravityacc.std.y              numeric     
tgravityacc.std.z              numeric     
tbodyaccjerk.mean.x            numeric     
tbodyaccjerk.mean.y            numeric     
tbodyaccjerk.mean.z            numeric     
tbodyaccjerk.std.x             numeric     
tbodyaccjerk.std.y             numeric     
tbodyaccjerk.std.z             numeric     
tbodygyro.mean.x               numeric     
tbodygyro.mean.y               numeric     
tbodygyro.mean.z               numeric     
tbodygyro.std.x                numeric     
tbodygyro.std.y                numeric     
tbodygyro.std.z                numeric     
tbodygyrojerk.mean.x           numeric     
tbodygyrojerk.mean.y           numeric     
tbodygyrojerk.mean.z           numeric     
tbodygyrojerk.std.x            numeric     
tbodygyrojerk.std.y            numeric     
tbodygyrojerk.std.z            numeric     
tbodyaccmag.mean               numeric     
tbodyaccmag.std                numeric     
tgravityaccmag.mean            numeric     
tgravityaccmag.std             numeric     
tbodyaccjerkmag.mean           numeric     
tbodyaccjerkmag.std            numeric     
tbodygyromag.mean              numeric     
tbodygyromag.std               numeric     
tbodygyrojerkmag.mean          numeric     
tbodygyrojerkmag.std           numeric     
fbodyacc.mean.x                numeric     
fbodyacc.mean.y                numeric     
fbodyacc.mean.z                numeric     
fbodyacc.std.x                 numeric     
fbodyacc.std.y                 numeric     
fbodyacc.std.z                 numeric     
fbodyaccjerk.mean.x            numeric     
fbodyaccjerk.mean.y            numeric     
fbodyaccjerk.mean.z            numeric     
fbodyaccjerk.std.x             numeric     
fbodyaccjerk.std.y             numeric     
fbodyaccjerk.std.z             numeric     
fbodygyro.mean.x               numeric     
fbodygyro.mean.y               numeric     
fbodygyro.mean.z               numeric     
fbodygyro.std.x                numeric     
fbodygyro.std.y                numeric     
fbodygyro.std.z                numeric     
fbodyaccmag.mean               numeric     
fbodyaccmag.std                numeric     
fbodybodyaccjerkmag.mean       numeric     
fbodybodyaccjerkmag.std        numeric     
fbodybodygyromag.mean          numeric     
fbodybodygyromag.std           numeric     
fbodybodygyrojerkmag.mean      numeric     
fbodybodygyrojerkmag.std       numeric     

Full file layout of Tidy Data Set 2
Label                          Type      Description
-------------------------------------------------------------------------------------------
subject                        integer     Number representing the subject participant in the experiment.
activity.label                 factor      Factor representing the activity performed by the subject.
avg.tbodyacc.mean.x            numeric     
avg.tbodyacc.mean.y            numeric     
avg.tbodyacc.mean.z            numeric     
avg.tbodyacc.std.x             numeric     
avg.tbodyacc.std.y             numeric     
avg.tbodyacc.std.z             numeric     
avg.tgravityacc.mean.x         numeric     
avg.tgravityacc.mean.y         numeric     
avg.tgravityacc.mean.z         numeric     
avg.tgravityacc.std.x          numeric     
avg.tgravityacc.std.y          numeric     
avg.tgravityacc.std.z          numeric     
avg.tbodyaccjerk.mean.x        numeric     
avg.tbodyaccjerk.mean.y        numeric     
avg.tbodyaccjerk.mean.z        numeric     
avg.tbodyaccjerk.std.x         numeric     
avg.tbodyaccjerk.std.y         numeric     
avg.tbodyaccjerk.std.z         numeric     
avg.tbodygyro.mean.x           numeric     
avg.tbodygyro.mean.y           numeric     
avg.tbodygyro.mean.z           numeric     
avg.tbodygyro.std.x            numeric     
avg.tbodygyro.std.y            numeric     
avg.tbodygyro.std.z            numeric     
avg.tbodygyrojerk.mean.x       numeric     
avg.tbodygyrojerk.mean.y       numeric     
avg.tbodygyrojerk.mean.z       numeric     
avg.tbodygyrojerk.std.x        numeric     
avg.tbodygyrojerk.std.y        numeric     
avg.tbodygyrojerk.std.z        numeric     
avg.tbodyaccmag.mean           numeric     
avg.tbodyaccmag.std            numeric     
avg.tgravityaccmag.mean        numeric     
avg.tgravityaccmag.std         numeric     
avg.tbodyaccjerkmag.mean       numeric     
avg.tbodyaccjerkmag.std        numeric     
avg.tbodygyromag.mean          numeric     
avg.tbodygyromag.std           numeric     
avg.tbodygyrojerkmag.mean      numeric     
avg.tbodygyrojerkmag.std       numeric     
avg.fbodyacc.mean.x            numeric     
avg.fbodyacc.mean.y            numeric     
avg.fbodyacc.mean.z            numeric     
avg.fbodyacc.std.x             numeric     
avg.fbodyacc.std.y             numeric     
avg.fbodyacc.std.z             numeric     
avg.fbodyaccjerk.mean.x        numeric     
avg.fbodyaccjerk.mean.y        numeric     
avg.fbodyaccjerk.mean.z        numeric     
avg.fbodyaccjerk.std.x         numeric     
avg.fbodyaccjerk.std.y         numeric     
avg.fbodyaccjerk.std.z         numeric     
avg.fbodygyro.mean.x           numeric     
avg.fbodygyro.mean.y           numeric     
avg.fbodygyro.mean.z           numeric     
avg.fbodygyro.std.x            numeric     
avg.fbodygyro.std.y            numeric     
avg.fbodygyro.std.z            numeric     
avg.fbodyaccmag.mean           numeric     
avg.fbodyaccmag.std            numeric     
avg.fbodybodyaccjerkmag.mean   numeric     
avg.fbodybodyaccjerkmag.std    numeric     
avg.fbodybodygyromag.mean      numeric     
avg.fbodybodygyromag.std       numeric     
avg.fbodybodygyrojerkmag.mean  numeric     
avg.fbodybodygyrojerkmag.std   numeric     

