# Rap Genius
### Contents:
- [Problem Statement](#Problem-Statement)
- [Project Files](#Project-Files)
- [Executive Summary](#Executive-Summary)
 - [Data Import and Cleaning](#Data-Import-and-Cleaning)
 - [EDA](#EDA)
 - [Model Interpretation](#Model-Interpretation)
- [Conclusions and Next Steps](#Conclusions-and-Next-Steps)
- [Source Documentation](#Source-Documentation)
### Problem Statement
Drake aka Aubrey Drake Graham is one of the most successful rappers of all time.  4 time grammy winner, including his most recent win for his hit song "God's Plan". His latest album Scorpion became his eighth number 1 album on the Billboard 200 album charts. Riding the wave of Hip Hop becoming a potent commercial force and the rise of streaming, Drake has garnered the attention that a canadian rapper what not have only 2 decades ago. The only other rappers that really rivals Drake in terms of commericial viability is Jay-z and Eminem. He has an uncanny knack to be able to combine hip-hop, pop, and R&B effortlessly while also being relatable in his unique storytelling. He is a force to be reckoned with. 

 However he is not the best. There is a difference. Drake in many people's eyes is an amazing singer, songwriter, rapper, and the occassional dancer. Yet, he would not be compared to the likes of Jay-z, Nas, J.Cole, or the contemporary creative standard that is Kendrick Lamar. Why? The same things that make him successful are his downfall in that regard: mass relatability, genre-infusion, and maybe topic selection.
 
 I want to know what sets Drake apart and makes him one of the most successful rappers today despite not being considered a top lyricists.

Compared to other rappers artistry, what makes him stand out?

### Project Files
Project notebooks follows the data science workflow of: 
- Determine Problem Statement
- Gather information
- Clean Information
- Perform EDA
- Model the data
- Evaluate the Data
- Answer the problem

There are four notebooks that will walk through all of this. Please visit each one below:

- [Cleaning](./https://github.com/johnsovo44/Rap_Genius--NLP/blob/master/Code/Rap%20Genius%20-%20Cleaning.ipynb)
- [Collection](./https://github.com/johnsovo44/Rap_Genius--NLP/blob/master/Code/Rap%20Genius%20-%20Collection.ipynb)
- [EDA](./https://github.com/johnsovo44/Rap_Genius--NLP/blob/master/Code/Rap%20Genius%20-%20EDA.ipynb)
- [Model](./https://github.com/johnsovo44/Rap_Genius--NLP/blob/master/Code/Rap%20Genius%20-%20Model.ipynb)

### Executive Summary
#### Data Import and Cleaning
To distinguish Drake I need to surround him with other artist of different calibers. I gathered my data from the Genius API. I decided my scope will just be the 10 most popular songs according to the Genius API and put the lyrics into a giant corpus for each artist. Next steps were to clean the data. This meant taking out the line breaks, unnecessary punctuation, lower casing, and removing section headers. I did not replace or remove any profanity to avoid fudging the data. Once cleaned I ended up with two dataframes: A corpus of Text and a Countvectorized version. The two versions will be used to do different types of analysis. 
#### EDA
For EDA I took a look at 4 areas to get a sense of who Drake is. 
- Common Words: What words will the rapper most often use in their songs? What does this say about them or the genre?
- Unique Words: This gives us a sense of the rappers lexical diversity. 
- Profanity: The use of profanity can give us a sense of how aggressive someone is. Drake often comes off as braggadocious more than aggressive and that shows up in the data. 
- Sentiment Analysis: Is the rapper's full set of lyrics more negative or positve? Are they more opinionated or fact based?

What seems to emerge from this EDA is that Drake is more of a reflective rapper on past situations with women, his life. On second pass after more cleaning you get this sense of longing and regret in his lyrics. He also doesn't use that many words when he raps, he seems to be quite positive (this is reinforced in how he uses bad words, not many) and opinionated. 
#### Model Interpretation
To get a further sense of how Drake is different from other rappers I used two models, a Latent Dirichlet Allocation (LDA) for Topic Modeling and a Markov Chains Model for Text Generation. The LDA model was able to pull out associated words with a particular topic. The disadvantage of the model is it does not tell you what the topic just the association. Words included: 'love', 'world', 'man', 'time', and 'real'. Nas was also closely associated with this, while other rappers seemed to be consumed with themselves, a past life or money. 

The Markov Chains Model was used to see what kind of lyrics would be pulled out if we gave the creative reins over to the computer. Would it pull out similar topics? Lyrics that often showed up seemed to reference love or a relationship. So those themes seem to to carry through with Markov Chains. The disadvantage of Markov Chains is they do not have memory, predictions are based off the previous word used and the probability of the new word coming after the previous word. Often sentences are not grammatical. Here is a sample below.

- 'Perspective i did you cause youre talkin boasy and shit 0 to do it i dont even know it you.'
- 'All me no more time where where i see i been cookin with my cell phone late night late night.'
- 'Cuddle with the goats for someone else you left your advances god damn chorus gods plan i had a lot...'
- 'Million off and when she say youll never ever leave from beside me cause i was a good girl and...'
### Conclusion and Next Steps
In conclusion, we know that Drake combined the genres of rap, pop, and r&b, and it seems to shine through given his low key vibes (lack of aggression), topic selection (love, relationships, reflection, and regret), and overall positivity compared to other rappers. He is not your typical rapper. In fact from this hard to pull out a typical rapper given that most rap about a wide range of topics. That could be part of their rise as the top genre. However Drake is a really gifted artist in that he can be relatable, sentimental and instrospective while pumping out hit after hit. He clearly has a formula and he sticks to a small set of topics, which could speak why he has such a small lexicon, to continue be one of the most successful rappers alive. 

Next steps after this include the following:
- Compare the Markov Chain Model to an RNN model to see if I can get grammatically correct lyrics.
- Generate random lyrics from each artist and see if a classification model can properly identify them
- Since LDA is a fuzzy unsupervised model, use DBSCAN or KNN to create clear topics and see where the artists' corpus falls. 
- Continue to clean the lyrics and add more artist to further understand Drake as a lyricst.
### Source Documentation
There were some additional resources that helped me understand the scope of my project and how to complete it. The following are resources I used to:

1. https://github.com/johnwmillr/LyricsGenius 
2. https://stackoverflow.com/questions/47400466/using-genius-api
3. http://www.storybench.org/download-song-lyrics-genius-using-python/
4. https://www.johnwmillr.com/trucks-and-beer/
5. http://jdaytn.com/posts/download-blink-182-data/
6. https://github.com/Hugo-Nattagh/2017-Hip-Hop
7. https://towardsdatascience.com/does-country-music-drink-more-than-other-genres-a21db901940b
8. https://towardsdatascience.com/49-years-of-lyrics-why-so-angry-1adf0a3fa2b4
9. https://medium.com/@RareLoot/how-to-download-an-artists-lyrics-from-genius-com-using-python-984d298951c6
10. https://www.youtube.com/channel/UCyv-PL-QgkAXEfDRcKrYMeA