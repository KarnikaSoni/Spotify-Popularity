# Spotify-Popularity
I am currently exploring the dependencies of parameters on the training behavior and accuracy. For this small project I will predict the popularity of songs based on song metrics such as features of acousticness, danceability, duration_ms, energy, instrumentalness, key, liveness, mode, speechiness, tempo, time_signature, and valence.

## Part 1.Import
In this section we essentially import essential packages for data visualisation, plotting, working with dataframe, and warnings (set that to ignore to  Discard the warning). This covers the first half of the code. The next set of imports including 

- RandomForest
- KNeighborsClassifier
- DecisionTreeClassifier
- LogisticRegression
- Linear Support Vector Classification

are the models we will compare the popularity prediction on.

## Part 2. View our Dataset
We load the dataset to look at the statistics like mean, count, and median using describe.
![Screenshot 2021-03-16 at 10 47 24 PM](https://user-images.githubusercontent.com/70371572/111407029-a3c31c00-86a9-11eb-8f67-ea28a951396e.png)

## Part 3. Check for Null Values
We check for null values. Since there are no null values, we don't have to fill any missing information. 
If there were, there we could fill with mean or median depending on the data distribution.

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

### 8.Acoustiness for Songs with More than 50 Popularity
![Screenshot 2021-03-16 at 11 05 04 PM](https://user-images.githubusercontent.com/70371572/111408710-0e755700-86ac-11eb-926c-9585ddce0a42.png)

### 9.Acoustiness for Songs with Less than 50 Popularity
![Screenshot 2021-03-16 at 11 05 22 PM](https://user-images.githubusercontent.com/70371572/111408733-18975580-86ac-11eb-9f2f-838d7fa72b07.png)

### 10.Loudness for Songs with More than 50 Popularity
![Screenshot 2021-03-16 at 11 05 38 PM](https://user-images.githubusercontent.com/70371572/111408755-2220bd80-86ac-11eb-87f9-4bc19de84707.png)

### 11.Loudness for Songs with Less than 50 Popularity
![Screenshot 2021-03-16 at 11 05 52 PM](https://user-images.githubusercontent.com/70371572/111408784-29e06200-86ac-11eb-92ae-9344035ce6a7.png)

## Part 5. Converting Variables from text to binary
There are 3 variables: key, mode, and time signature that need to be converted from text to numbers using one-hot-encoding. We also define popularity as a binary variable. 
- We will define above 57 as "popular" since that's the border of the top 25% of songs and encode that as 1, and below 75 as "not popular" and encode that as 0.
- Key: Since there are 12 letter keys, we will convert A to 0, A to 1, and so on and so forth until B is 12.
- Mode: We will assign major = 1 and minor = 0.

## Part 6. Prediction using different Models
For feature selection, we will select the following features: acousticness, danceability, duration_ms, energy, instrumentalness, key, liveness, mode, speechiness, tempo, time_signature, and valence.
- We define 80% of the dataframe for training and 20% of the dataframe for testing.
- Use train_test_split to make a testing dataset

## Part 7. Different Results from Models

- LogisticRegression has 
   - Accuracy: 0.7895316360511333
   - AUC: 0.5
- RandomForest
   - Accuracy: 0.9214201310559673
   - AUC: 0.8331614619226306
- KNeighborsClassifier
   - Accuracy: 0.7736330432914383
   - AUC: 0.6156631913174396
- DecisionTreeClassifier
   - Accuracy: 0.8518637877323021
   - AUC: 0.8112920096258869
- Linear Support Vector Classification
   - Accuracy: 0.7135
   - AUC: 0.5824956293706294
   
## Part 7. Conclusion
Using a dataset of ultimate-spotify-tracks, we were able to predict popularity (greater than 57 popularity) with audio-based metrics such as acousticness, danceability, duration_ms, energy, instrumentalness, key, liveness, mode, speechiness, tempo, time_signature, and valence. The Random Forest Classifier was the best performing algorithm with **92.1% Accuracy** and **83.3% AUC**.

### Model with best to worst Accuracy
![Screenshot 2021-03-16 at 11 24 32 PM](https://user-images.githubusercontent.com/70371572/111410247-c60b6880-86ae-11eb-87b7-3e63d48a0256.png)

### Model with best to worse AUC
![Screenshot 2021-03-16 at 11 24 41 PM](https://user-images.githubusercontent.com/70371572/111410260-cad01c80-86ae-11eb-8d5e-db984d338b01.png)


Moving forward, I want to explore the affect of more dependencies using large hospital data to predict Medical diseases.
