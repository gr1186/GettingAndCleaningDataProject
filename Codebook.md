The script run_analysis.R performs the 5 steps described in the course project's definition.

All the similar data is merged using the rbind() function; files having the same number of columns and referring to the same entities.

Only those columns with the mean and standard deviation measures are taken from the whole dataset. After extracting these columns, they are given the correct names, derived from features.txt.

Activity data is addressed with values 1:6, the activity names and IDs from activity_labels.txt are substituted in the dataset.

Columns with vague column names are corrected.

A new dataset is generated with all the average measures for each subject and activity type (30 subjects * 6 activities = 180 rows). The output file is named averages_data.txt.


Applied Variables

x_train, y_train, x_test, y_test, subject_train and subject_test contain the data from the downloaded files.

x_data, y_data and subject_data merge the previous datasets to further analysis.

features contains the correct names for the x_data dataset, which are applied to the column names stored in mean_and_std_features, a numeric vector used to extract the desired data.

A similar approach is taken with activity names through the activities variable.
all_data merges x_data, y_data and subject_data in a big dataset.

Averages_data contains the relevant averages which will be later stored in a .txt file. ddply() from the plyr package is used to apply colMeans()

