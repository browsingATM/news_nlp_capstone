# news_nlp_capstone

The following project relied on the 20newsgroups dataset to explore different ways of analyzing topics. Using the appropriate regular expressions, I was able to prepare the data and test it with CountVectorizer to ensure the shape was the proper size. I tried doing this later in the notebook and realized it was more prudent to test how well the model could read the text earlier.

With temporal-based algorithms it can make sense to include stop words, yet I verified it was not helpful in this case. I did this by
instantiating the CountVectorizer model, one with and another without stop words. The model with stop words had 264 additional words. 
I was then able to visualize the most common words in the corpus as seen by the two models. Not surprisingly, the model with stop words had ~20 words that occurred between 3-4 times more frequently than the top 5 words in the model with no stop words.

To get an idea of what clusters would naturally appear in the corpus I relied on yellowbrick's TSNE visualizer. I also looked at the news sources themselves and could identify between 5-7 topics depending on context (religion can be political).

I then instantiated pyLDAvis for both models (with and without stop words) and among those two specified the number of topics
as 5 or 10 in order to determine which number of topics performed better in the two models. Because this is unsupervised data, there is no objective measure of goodness. Using subjective investigation of the data for its distribution and topic identification led to the conclusion that the 10 topic model was best. For example, the ten topic model was able to visualize and discern the subtelties between articles about religion in the Middle East and US political news in the Middle East. 

The same thing was done using TF-IDF. In both cases the 10-topic models performed best.

To further enhance standard approaches using SVD on a term frequency data set, Latent Dirichlet Analysis (LDA) was investigated. In addition to the term frequency embedding a second term topic matrix was calculated by statistical sampling methods. The tool pyLDAvis allows for the user to influence the clustering based on term topic information. The amount of influence the term-topic matrix provides is controlled by a lambda parameter. A lambda of 0 means how exclusive a word is to a topic (jargon), whereas a lambda of 1 means that how probable a word is to appear in a topic (common or colloquial terms). 


