# news_nlp_capstone

The following project relied on the 20newsgroups dataset to explore different ways of analyzing topics. Using the proper regex, 
I was able to prepare the data and test it with CountVectorizer to ensure the shape was the proper size. I tried doing this later in 
the notebook and realized it was more prudent to test how well the model could read the text earlier.

In some cases, it makes sense to include the stop words in english and I verified it was not helpful in this case. I did this by
instantiating(?) the CountVectorizer model with and without stop words, which made a difference of 264 words/(lemmas?). 
I was then able to visualize the most common words in both corpuses(?). Not surprizingly, the corpus(?) with stop words had ~20 words
that were printed between 3-4x more frequently than the top words in the corpus(?) with no stop words.

Then, I wanted to get an idea of what clusters would naturally appear in the corpus so I relied on yellowbrick's TSNE visualizer.
I also looked at the news sources themselves and could identify between 5-7 topics depending on context (religion can be political).

I then instantiated (?) pyLDAvis between both corpuses(?)(with and without stop words) and among those two specified the number of topics
as 5 or 10. I wanted to see how well the model was able to differentiate topics better with 5 or 10. I did the same thing for TF-IDF. 

In both the case of CountVectorizer and TF-IDF, including the stop words confused the model and there was no discernable topic recognition.
Also, both cases the 10-topic models performed better and were more specific with what words were associated with which topic. 

Left lambda = 0 means that you value how exclusive a word is to a topic

Right lambda = 1 means that you value how probable a word is to appear in a topic


