# news_nlp_capstone

The following project relied on the 20newsgroups dataset to explore different ways of analyzing topics. Using the appropriate regular expressions, the data was prepared and tested on CountVectorizer to ensure the model was reading the text properly. This was done early in the notebook to avoid complications with the tokens later on.

With temporal-based algorithms it can make sense to include stop words, yet in this case it was not helpful to include them. To do this,
the CountVectorizer model was instantiated, one model with and another model without stop words. The model with stop words had 264 additional words. Using yellowbrick's Frequency Distribution Visualizer (FreqDistVisualizer), it was clear that the model with stop words had ~20 words that occurred between 3-4 times more frequently than the top 5 words in the model with no stop words.

To get an idea of what clusters would naturally appear in the corpus, yellowbrick's TSNE visualizer to see the total number of documents and how they are by newsgroup. In the list of newsgroups one can identify between 6-8 topics depending on context (religion can be political; electronics can be in both a scientific paper and a consumer's digest).

After instantiating pyLDAvis for both models (with and without stop words), each model was tested using a different number of topics (5 and 10) to judge model performance. Because this is unsupervised data, there is no objective measure of goodness. Using subjective investigation of the data for its distribution and topic identification led to the conclusion that the 10 topic model was best. For example, the ten topic model was able to visualize and discern the subtleties between articles about religion in the Middle East and US political news in the Middle East. 

The same thing was done using TF-IDF. In both cases the 10-topic models performed best.

To further enhance standard approaches using SVD on a term frequency data set, Latent Dirichlet Analysis (LDA) was investigated. In addition to the term frequency embedding a second term topic matrix was calculated by statistical sampling methods. The tool pyLDAvis allows for the user to influence the clustering based on term topic information. The amount of influence the term-topic matrix provides is controlled by a lambda parameter. A lambda of 0 means how exclusive a word is to a topic (jargon), whereas a lambda of 1 means that how probable a word is to appear in a topic (common or colloquial terms). 

Jensen-shannon info:
