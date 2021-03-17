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
We check for null values. Since there are no null values, we don't have to fill any missing information. If there were, there we could fill with mean or median depending on the data distribution.
![Screenshot 2021-03-16 at 10 52 53 PM](https://user-images.githubusercontent.com/70371572/111407601-5dba8800-86aa-11eb-98a2-a5043cffc57d.png)

## Part 4. Graphs showing relation of popularity with different features available

### 1.Popularity Distribution (in general) 
![Screenshot 2021-03-16 at 10 54 24 PM](https://user-images.githubusercontent.com/70371572/111407838-ad00b880-86aa-11eb-9f50-972a75761428.png)


### 2.Dependency of Popularity on Time Signature
![Screenshot 2021-03-16 at 10 56 21 PM](https://user-images.githubusercontent.com/70371572/111407926-d7eb0c80-86aa-11eb-81cc-4408583a77da.png)


### 3.Dependency of Popularity on Key
![Screenshot 2021-03-16 at 10 59 44 PM](https://user-images.githubusercontent.com/70371572/111408202-4fb93700-86ab-11eb-9fb5-78f3b99bed4e.png)

### 4.Dependency of Popularity on Mode 
![Screenshot 2021-03-16 at 11 00 04 PM](https://user-images.githubusercontent.com/70371572/111408230-5a73cc00-86ab-11eb-99ea-2df3fc4b4c45.png)

### 5.Dependency of Popularity on Mode and Key 
![Screenshot 2021-03-16 at 11 00 21 PM](https://user-images.githubusercontent.com/70371572/111408256-652e6100-86ab-11eb-904d-de48d7813708.png)

### 6.Dependency of Popularity on Acousticness
![Screenshot 2021-03-16 at 11 00 43 PM](https://user-images.githubusercontent.com/70371572/111408285-71b2b980-86ab-11eb-8166-597a2b0b10bb.png)

### 7.Dependency of Popularity on Loudness
![Screenshot 2021-03-16 at 11 01 52 PM](https://user-images.githubusercontent.com/70371572/111408383-9b6be080-86ab-11eb-82f7-79d4a073e024.png)
