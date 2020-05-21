This is an example of using Doc2Vec and HDBSCAN.

I produce a representation of IMDB film reviews and cluster them. For the representation I use Doc2Vec, following Linan Qiu's example: http://linanqiu.github.io/2015/10/07/word2vec-sentiment/
I then apply UMAP and HDBSCAN as described in the UMAP documentation: https://umap-learn.readthedocs.io/en/latest/clustering.html

Doc2Vec extends the Word2Vec algorithm by concatenating a document vector along with word vectors while training a Neural Net to predict the missing word. Documents are therefore embedded along with the words and should represent the topic of the document taking word order into account. 

One possible use for this embedding is to find clusters of similar documents. I attempt this using Hierarchical DBSCAN. HDBSCAN extends DBSCAN into a hierarchical clustering algorithm. I like DBSCAN for this excercise because it doesn't require that every document be part of a cluster. However, Density clustering works best with low dimensionality so I apply UMAP which can work well with DBSCAN.