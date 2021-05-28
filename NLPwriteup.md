# Natural Language Processing and Unsupervised Learning Project - Song Recommendation 

## Abstract
The goal of this project is to create a song recommendation model based on lyrics. The dataset I used contains around sixteen hundreds data points with features like the lyric,artist,release date, etc. The dataset is established from ten singers including Ariana Grande, Beyonce, Dua Lipa, Lady Gaga,Taylor Swift, Ed Sheeran,Eminem,Justin Bieber,Maroon 5, and Drake.

 Before fitting the data into a top modeling algorithm, I have done the preprocessing on the lyric. I used Tfidf vectorizer along with the lemmatization tokenizer and the extend stop_word list to get the frequency score of each word in the lyrics.  After that, I fit it into three topic models : NMF (Non-Negative Matrix Factorization),Latent Dirichlet Allocation (LDA), and CorEx. I chose to use NMF because it is more interpretable. The NMF model gives me the relatability of each song to the topics. I interpret the topics by looking at the top ten song lyrics with the highest value of a topic, read the lyrics, and determine the theme. After determining the theme, I convert the NMF score into a dataframe and fit it to the cosine similarity metric. I get a dataframe of the song similarity based on lyric. At the end, I created a function using the cosine similarity result to take a song name, and generate seven recommended songs.

 ## Design
 A song is made of music and the lyric. I believe the lyric represents the theme of the song. I assume that a person listen to a song partially because of its theme, therefore, I will create a recommendation algorithm based on the lyrics to generate songs with similar theme and recommend them to that person.

 ## Data
 ### Song Lyrics Dataset from Kaggle
 - Ariana Grande
 - Beyonce
 - Dua Lipa
 - Lady Gaga
 - Taylor Swift
 - Ed Sheeran
 - Eminem
 - Justin Bieber
 - Marron 5
 - Drake

 - 1526 rows with 8 columns
 - feature highlight : Lyric 

 ## Algorithms
1. Use python to concatenate the small individual singer datasets into one big dataset
2. Do a simple explordatory data analysis , dropping the missing values, dropping the duplicated title
3. Word preprocessing on the lyrics create a new column called 'vec' that has the punctations, non-english words removed
4. Create a lemmatizer tokenizer function based on the nltk WordNetLemmatizer
5. create a stop word list and extend it with words that are meaningless
6. import the TfidfVectorizer from sklearn and set the stop words to be out stop word list, and the tokenizer as the lemmatizer tokenizer 
7. Use TfidfVectorizer to fit_transform the 'vec' column and set it as lyrics_matrix
8. import NMF from sklearn and choose the n_components = 8 (optional, 8 is my preference)
9. use NMF to fit transform the lyrics_matrix and name it as topic_values

10. Evaluate the top twelve words from each topic
![topics](https://user-images.githubusercontent.com/63031028/119936855-a7dba780-bf3e-11eb-8879-c3e0a2d2206e.png)
11. Evaluate the top lyrics from each topic 
- Example of topic 8 
![lyrics](https://user-images.githubusercontent.com/63031028/119937193-37815600-bf3f-11eb-8ca1-f76f1fa1243f.png)

After evaluating the most used words, top lyrics, and even listen to the song , I finally come up with the label of each topic which are ['Rap','Falling in love','Girl','Missing someone','Confessing','Needy','Regret','Breaking up'] and I use the lables as columns and created a dataframe called df_topic which maps the topic_values, and the topic labels

12. tried the same process on LDA and CoRex, but the topics aren't as interpretable as NMF, so decided to use NMF

13. import cosine_similarity from sklearn 
14. I rename the df_topic as lyric_matrix (with no s) , and then fit it into the cosine similarity metric as saved it as cos_sim

15. cos_sim is an array that tells me the similarity of songs
16. Lastly, create a function called recommendation which will take the lyric_matrix, and the song database ,to generate the songs that aresimilar to the input song
![recfun](https://user-images.githubusercontent.com/63031028/119939567-ebd0ab80-bf42-11eb-9974-91936fd77f4a.png)

17. Here is the result:

![input](https://user-images.githubusercontent.com/63031028/119939797-39e5af00-bf43-11eb-8e23-e705ad04ff3b.png)

![output](https://user-images.githubusercontent.com/63031028/119940152-a52f8100-bf43-11eb-8d69-09729ce1817d.png)

## Tools
- Python Numpy , Pandas - data cleaning, data manipulation 

- Nltk - lemmatizer

- Sklearn - Topic Models(NMF,LDA) , Dimensionality reduction(Tfidf), cosine similarity

- Corextopic - topic model (CoRex)

## Communication
The recommendation function is based on the similarity of the lyrics, therefore, the suggested songs may from different genres and have a big difference in the speed of the song

## Further steps
- add more songs to the dataset
- put the song tempo, and song genre on the cosine similarity metric because these two things should be taken as consideration on recommending songs
- Try different number of components 