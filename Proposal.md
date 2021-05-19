# Unsupervised Project Proposal
## Question/need
- The purpose of this project is to us evaluate the lyrics of different genres to see the word choices of different genre during different decade
- Will do it in different languages (if have time)
- Songwriters, music companies will find this project useful by knowing what word should they use more often when writing their songs
- Historian can find this project useful because the common words from lyrics in specific decade can reflect to people's life during that time
- Anthropologist will find this project useful if I apply this project into different languages because common words in different language have a straight relationship to its culture 

    - If the most common word in one language is 'love', it can mean that the culture of this language emphasizes on loving each other 

## Data Description 
- Lyrics(1950-2019) dataset from data mendeley
- 31 columns
- 28372 rows
- Genre: 'pop', 'country', 'blues', 'jazz', 'reggae', 'rock', 'hip hop'
- Spliting up the dataset into different genres
- Finding the most used word for each genre within decade 
- Evaluate the historical background of each decade to understand why a specific word was used the most 

## Tools
- Python (Jupyter Nobebook)
- Pandas and Numpy : Examine the data 
- Sklearn for the NLP packages
- ntlk for tokenization
- re , string for text preprocessing

## MVP
Find the common words of each genre during each decade and use topic modeling to classify the lyrics into different groups (The vibe of the music )