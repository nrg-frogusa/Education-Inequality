# Education-Inequality
The purpose of this repository is to explore the inequality of education in the U.S. More descriptively, we will determine whether or not certain socioeconomic factors affect SAT and ACT scores of high school students.

# Data
This project utilizes two data sets EdGap_data.xlsx and ccd_sch_029_1617_w_1a_11212017.csv. The primary data set is the EdGap data set from EdGap.org. This data set from 2016 includes information about average ACT or SAT scores for schools and several socioeconomic characteristics of the school district. The secondary data set is basic information about each school from the National Center for Education Statistics.

The CSV file above can be accessed from the followin link: https://drive.google.com/file/d/1HvW2w-o2XZzCm4KTvnb1Bb3BvoAa14BP/view?usp=sharing

# Data Preparation
First, I converted any data to the correct data types for use in the future. For example, the ID variable in our "school_info" data set had it set as a float while our "ed_gap" had it set as an interger. We normalized them to an interger so we could join them later.

Next, I selected only relevant subsets of data. We don't need all of the information stored in the datasets to answer our questions on education inequality, so I only selected the socioeconomic factors such as median income and percent of lunchs that were free/state subsidized.

After that, I joined the two data sets, using the ID as our variable to join upon. This way we can correspond the school information to the socioeconomic factors that were in "ed_gap".  

Next, I only included entries that were within range and helpful to creating relationships or observations. For example, it's very unlikely that a whole school for a year had an average ACT score of less than 5, so I only included values that were greater than 5. I did this for all columns in the dataset to bring out number of observations down and make the dataframe more workable. 

Then, I performed a train-test split where we could use some of the data to train our model to predict average ACT scores using the remaining 20% of our socioeconomic data that the model didn't see. In all, the model performed relatively well in predicting the average ACT scores with an RMSE of approximately 0.92 error.

The notebook used to prepare the data is called: DATA_3320_Education_Inequality_Data_Preparation_Justin_Ishida.ipynb
The clean dataframe is called: clean_education_inequality.csv
