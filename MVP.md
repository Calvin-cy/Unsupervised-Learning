## MVP
The goal of this project is to use Natural Language processing to create a song recommendation system based on the song contents

So far, I have done the topic modelling on different genres.
Some words are used across all the genres. The words heart and break appears to be an topic for all the genres except for hiphop.

HipHop and Reggae uses more offensive words like 'bxtch', 'hoe' more often.
HipHop also uses word like weed,smoke, party,drink,roll and the other genres except reggae do not use any of it.

### For Hip Hop:

```
[like     1.814132
 cause    0.346399
 check    0.208906
 style    0.208503
 crew     0.195260
 Name: topic_0, dtype: float64,
 bitch    1.468146
 hoe      0.313151
 know     0.185825
 want     0.185552
 like     0.158146
 Name: topic_1, dtype: float64,
 life     0.493371
 live     0.408931
 feel     0.356315
 away     0.349747
 world    0.344666
 Name: topic_2, dtype: float64,
 yeah     1.491642
 right    0.245888
 bust     0.122925
 throw    0.116049
 know     0.113238
 Name: topic_3, dtype: float64,
 know     0.896377
 come     0.622001
 cause    0.539324
 time     0.488657
 want     0.314230
 Name: topic_4, dtype: float64,
 party     1.377550
 club      0.188176
 people    0.182747
 world     0.181622
 time      0.159912
 Name: topic_5, dtype: float64,
 money      1.112300
 power      0.225988
 respect    0.175867
 block      0.122648
 whip       0.116966
 Name: topic_6, dtype: float64,
 baby       0.955798
 stop       0.271154
 vanilla    0.266419
 play       0.234353
 girl       0.233796
 Name: topic_7, dtype: float64,
 real    1.245377
 tell    0.202606
 know    0.160885
 talk    0.131576
 hear    0.121321
 Name: topic_8, dtype: float64,
 high     0.693657
 weed     0.417051
 smoke    0.414025
 drink    0.319834
 roll     0.246393
 Name: topic_9, dtype: float64]
 ```

 So apparently, Hiphop and Reggae uses word that are more offensive, and the other genres tend to use words that is more neutral and focus on heart break and personal feelings.
