# Unsupervised Project Proposal
## Question/need
- The purpose of this project is to create a content-based recommendation system
- Will do it in different languages (if have time)
- Songwriters, music companies will find this project useful by knowing what word should they use more often when writing their songs
- Historian can find this project useful because the common words from lyrics in specific decade can reflect to people's life during that time
- Anthropologist will find this project useful if I apply this project into different languages because common words in different language have a straight relationship to its culture 

    - If the most common word in one language is 'love', it can mean that the culture of this language emphasizes on loving each other 

## Data Description 
- data.csv 
- 170653 rows with 18 columns
- feature highlight : tempo, acousticness, danceability, key
- lyrics-data.csv
- 379931 rows with 5 columns
- feature highlight : Lyric , SName (song name)
- genres_v2.csv
- 42305 rows with 21 columns
- feature highlight : Genre, song_name

- Genre: 'pop', 'country', 'blues', 'jazz', 'reggae', 'rock', 'hip hop'
- Spliting up the dataset into different genres
- Finding the most used word for each genre within decade 
- Evaluate the historical background of each decade to understand why a specific word was used the most 

## Tools
- Python (Jupyter Nobebook)
- Pandas and Numpy : data cleaning, data manipulation,data merging
- Sklearn : Topic Models(NMF) , Dimensionality reduction(Tfidf), cosine similarity

- Nltk: WordNetLemmatizer,stopwords
- re , string for text preprocessing


## MVP
Create a content-based recommendation system using cosine-similarity to find songs that are similar to the one that the user is listening to 
