# Amazon-ML-Challenge-2021

Amazon ML Challenge WASs a two-stage competition where students from all engineering campuses across India were given a unique opportunity to work on Amazon’s dataset to bring in fresh ideas and build innovative solutions for a real-world problem statement.

## APPROACH:

## DATA PREPROCESSING ON TRAIN DATA:

•	We have dropped the rows which were having null values in all columns.<BR>
•	After that we cleaned the text data by removing stopwords, words with length less than 3, html tags,  numbers, punctuations and words like ‘inch’.<BR>
•	Followed by that, we performed Lemmatization on the cleaned text data.<BR>
•	Once we had cleaned our data, we handled the missing values as follows:<BR>
1.	We filled the null BRAND values as the mode of BRAND values for the same BROWSE_NODE_ID.
2.	The null values in the TITLE column were replaced by the BULLET_POINTS/DESCRIPTION/BRAND (whichever is non null) values of the same row.
3.	The null values in the BULLET_POINTS column were replaced by the TITLE values of the same row.
4.	The null values in the DESCRIPTION column were replaced by the BULLET_POINTS values of the same row.
Hence, no null value is left in the dataset.

## FEATURE ENGINEERING:
•	We made a set of words common in any two of the three columns i.e. TITLE, BULLET_POINTS and DESCRIPTION for each row.<BR>
•	We added the BRAND value of that row in the set.<BR>
•	After that, we created a new column- “Merged” , each row of which contained the set for that particular row.<BR>
•	We used the Merged column for creating Bag of Words vector for the dataset.<BR>

## TRAINING:
•	Using the Bag of Words we trained KNN model for 3 neighbours and metric=cosine.

## TESTING:
•	We did the same data preprocessing and feature engineering as on train dataset.<BR>
•	We used the Bag of Words vector for testing our model and saved our result in the csv file.

## LEADERBOARD RANKING:
129/3290

