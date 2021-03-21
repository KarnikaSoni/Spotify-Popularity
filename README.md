# Spotify-Popularity
I am currently exploring the dependencies of parameters on the training behavior and accuracy. For this project I will predict the popularity of songs based on song metrics such as features of acousticness, danceability, duration_ms, energy, instrumentalness, key, liveness, mode, speechiness, tempo, time_signature, and valence.

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

## Descriptions of the 12 unique numerical attributes for each song:
- 1 - Acousticness (float) 
  - A confidence measure from 0.0 to 1.0 of whether the track is acoustic.|
- 2 - Danceability (float)
  - Danceability describes how suitable a track is for dancing based on a combination of musical elements including tempo, rhythm stability, beat strength, and overall regularity.
- 3 - duration_ms (int) 
  - Energy is a measure from 0.0 to 1.0 and represents a perceptual measure of intensity and activity. Typically, energetic tracks feel fast, loud, and noisy.
- 4 - instrumentalness (float)
  - Predicts whether a track contains no vocals. “Ooh” and “aah” sounds are treated as instrumental in this context.
- 5 - key (int)
  - The estimated overall key of the track.
- 6 - liveness (float)	
  - Detects the presence of an audience in the recording. Higher liveness values represent an increased probability that the track was performed live.
- 7 - loudness	-9.94	6.50	
  - The overall loudness of a track in decibels (dB)
- 8 - mode (int)	
  - Mode indicates the modality (major or minor) of a track, the type of scale from which its melodic content is derived.
- 9 - speechiness (float)	
  - Speechiness detects the presence of spoken words in a track. The more exclusively speech-like the recording (e.g. talk show, audio book, poetry), the closer to 1.0 the attribute value.
- 10 - tempo (int)
  - The overall estimated tempo of a track in beats per minute (BPM). In musical terminology, tempo is the speed or pace of a given piece and derives directly from the average beat duration.
- 11 - time signature (int)	
  - An estimated overall time signature of a track.
- 12 - valence (float)	
  - A measure from 0.0 to 1.0 describing the musical positiveness conveyed by a track. Tracks with high valence sound more positive (e.g. happy, cheerful, euphoric), while tracks with low valence sound more negative (e.g. sad, depressed, angry).

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

### Heatmap for all features and Popularity
![Screenshot 2021-03-21 at 1 33 18 PM](https://user-images.githubusercontent.com/70371572/111914817-01f55380-8a4a-11eb-9683-f25e538feefa.png)

To look at any potential multicolinearity issues within the independent variables, and using sns to make a heatmap. Overall, there aren't many independent variables with high correlation values, but energy/loudness have strong correlation which could potentially cause problems, which could have pretty big implications for fitting a linear model. Another thing we notice is there is not much correlation between independent variables and popularity.![Screenshot 2021-03-21 at 1 35 20 PM](https://user-images.githubusercontent.com/70371572/111914892-4b45a300-8a4a-11eb-91c2-5ff646bd5226.png)


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
   
## Part 8. Conclusion
Using a dataset of ultimate-spotify-tracks, we were able to predict popularity (greater than 57 popularity) with audio-based metrics such as acousticness, danceability, duration_ms, energy, instrumentalness, key, liveness, mode, speechiness, tempo, time_signature, and valence. The Random Forest Classifier was the best performing algorithm with **92.1% Accuracy** and **83.3% AUC**.

### Model with best to worst Accuracy
![Screenshot 2021-03-16 at 11 24 32 PM](https://user-images.githubusercontent.com/70371572/111410247-c60b6880-86ae-11eb-87b7-3e63d48a0256.png)

### Model with best to worse AUC
![Screenshot 2021-03-16 at 11 24 41 PM](https://user-images.githubusercontent.com/70371572/111410260-cad01c80-86ae-11eb-8d5e-db984d338b01.png)


Moving forward, I want to explore the affect of more dependencies using large hospital data to predict Medical diseases.

## References
- Cher Lau-Cher Lau - https://towardsdatascience.com/5-steps-of-a-data-science-project-lifecycle-26c50372b492
- Are Hit Songs Becoming Less Musically Diverse? Andrew Thompson-Matt Daniels-Damián Gaume - https://pudding.cool/2018/05/similarity/
- Song Popularity Predictor Mohamed Nasreldin-Mohamed Nasreldin - https://towardsdatascience.com/song-popularity-predictor-1ef69735e380
- Titanic: Beginner's Guide with Sklearn https://www.kaggle.com/ialimustafa/titanic-beginner-s-guide-with-sklearn/data
- Data Source: https://www.kaggle.com/zaheenhamidani/ultimate-spotify-tracks-db
