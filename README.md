# Spotify-Popularity
I am currently exploring the dependencies of parameters on the training behavior and accuracy. For this small project I will predict the popularity of songs based on song metrics such as features of acousticness, danceability, duration_ms, energy, instrumentalness, key, liveness, mode, speechiness, tempo, time_signature, and valence.

## Part 1.Import
In this section we essentially import essential packages for data visualisation, plotting, working with dataframe, and warnings (set that to ignore to  Discard the warning). This covers the first half of the code. The next set of imports including 

- RandomForest
- KNeighborsClassifier
- DecisionTreeClassifier
- LogisticRegression

are the models we will compare the popularity prediction on.

## Part 2. View our Dataset
We load the dataset to look at the statistics like mean, count, and median.
![Screenshot 2021-03-16 at 10 47 24 PM](https://user-images.githubusercontent.com/70371572/111407029-a3c31c00-86a9-11eb-8f67-ea28a951396e.png)
