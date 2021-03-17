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
We load the dataset to look at the statistics like mean, count, and median using describe.
![Screenshot 2021-03-16 at 10 47 24 PM](https://user-images.githubusercontent.com/70371572/111407029-a3c31c00-86a9-11eb-8f67-ea28a951396e.png)

## Part 3. Check for Null Values
We check for null values. Since there are no null values, we don't have to fill any missing information. If there were, there we could fill with mean or median depending on the data distribution.![Screenshot 2021-03-16 at 10 52 53 PM](https://user-images.githubusercontent.com/70371572/111407601-5dba8800-86aa-11eb-98a2-a5043cffc57d.png)

## Part 4. Graphs showing relation of popularity with different features available

### Popularity Distribution (in general) 
![Screenshot 2021-03-16 at 10 54 24 PM](https://user-images.githubusercontent.com/70371572/111407838-ad00b880-86aa-11eb-9f50-972a75761428.png)


### Dependency of Popularity on Time Signature
![Screenshot 2021-03-16 at 10 56 21 PM](https://user-images.githubusercontent.com/70371572/111407926-d7eb0c80-86aa-11eb-81cc-4408583a77da.png)


### Dependency of Popularity on Key


### Dependency of Popularity on Mode 


### Dependency of Popularity on Mode and Key 


### Popularity Distribution (in general) 
