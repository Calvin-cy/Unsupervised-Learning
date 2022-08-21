# Natural Language Processing and Unsupervised Learning Project - Song Recommendation System

## Abstract
The goal of this project is to create a song recommendation model based on the song elements like a key, tempo, acoustics, etc., along with the lyrics. The datasets I used are the data.csv which contains the features of the song like valence, tempo, danceability, etc., and the lyrics-data.csv which has the information of the song lyrics and artist names. I merged them into a final dataset that contained all the song features including the artist name, and the song name.
Since the lyrics are not numbers and they aren't comparable, I have to convert them into something comparable. Therefore, I used Tfidf vectorizer along with the lemmatization tokenizer and the stop_word list provided by nltk to get the frequency score of each word in the lyrics. Then, I fit it into the NMF (Non-Negative Matrix Factorization) model to get the relatability of each song to the topics. I merged the NMF scores with the song features and fit them to the cosine similarity metric. The cosine similarity metric gives me the result of songs that share similar features. My recommendation system is based on the result of cosine similarity and will generate 10 similar songs.

 ## Design
 A song is made of music and the lyric. I believe the all elements of the song represent the song's uniqueness. I assume that a person listen to a song partially because of its uniqueness, therefore, I created a recommendation algorithm based off on song elements to recommend songs with similar identities to the users.

 ## Data
 ### data.csv 
 - 170653 rows with 18 columns
 - feature highlight : tempo, acousticness, danceability, key
 ### lyrics-data.csv
 - 379931 rows with 5 columns
 - feature highlight : Lyric , SName (song name)
 ### genres_v2.csv
 - 42305 rows with 21 columns
 - feature highlight : Genre, song_name 

 ## Algorithms
1. Use python to merge data.csv,lyrics-data.csv,and genres_v2.csv into the big dataset that I will use for the rest of the project
2. Do a simple explordatory data analysis , dropping missing values and duplicated songs (some song may have performed byy different singers, so only keeping the oldest one), dropping non-english songs since I only want to focus on english songs, and do a quick data engineering, dropping some features that I think is vague and useless
3. Word preprocessing on the lyrics applying functions to remove punctuations, to make strings lower-case and remove the '\n' sign from the lyrics, create a new column called 'vec' to store the new word-preprocessed lyric
4. Create a lemmatizer tokenizer function based on the nltk WordNetLemmatizer
5. Create a stop word list for english only
6. Import the TfidfVectorizer from sklearn and set the stop words to be our stop word list, and the tokenizer as the lemmatizer tokenizer 
7. Use TfidfVectorizer to fit_transform the 'vec' column which is the columns that I did the word-preprocessing on and name it as lyrics_matrix
8. Import NMF from sklearn and choose the n_components to 8 (optional, 8 is my preference)
9. Use NMF to fit transform the lyrics_matrix and name it as topic_values and convert it into a dataframe called df_topic 
10. Merge the song dataset with the df_topic dataframe and drop the lyric column because the df_topic dataset represents the topic values of lyrics and merge with the genres dataframe to get the genre for each song

11. Get the dummy-variables for all the categorical columns 
12. Drop the name column because cosine_similarity cannot take strings and our dataframe is all settled (with all the categorical columns as dummy-variables, lyrics become topic_values, along with the numeric columns stated the way they were)

<img width="848" alt="Screen Shot 2022-08-20 at 8 37 57 PM" src="https://user-images.githubusercontent.com/63031028/185774359-a513600e-7941-4baa-b874-528772293a25.png">


13. Create a reverse mapping of song titles to indices. By this, we can easily find the title of the songs based on the index, and be used in the function that we are going to create


14. Import cosine_similarity from sklearn 
15. Create a function called recommend_song which takes a song name and return 10 songs based on the similarity score after feeding the cosine_similarity model with the dataframe we created
<img width="366" alt="Screen Shot 2022-08-20 at 8 42 51 PM" src="https://user-images.githubusercontent.com/63031028/185774480-913fa4f3-c468-4b70-8ac6-1ffbb24e83dd.png">



## Tools
- Python Numpy,Pandas - data cleaning, data manipulation,data merging

- Nltk - WordNetLemmatizer,stopwords

- Sklearn - Topic Models(NMF) , Dimensionality reduction(Tfidf), cosine similarity



## Communication
The recommendation function is based on the similarity of all the song features, therefore, the suggested songs contained very similar features to the input song

## Further steps
- Try different number of components 
- Dig into the meaning of the topics
