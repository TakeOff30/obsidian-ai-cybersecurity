Easy recsys implementation:
	data_matrix = user x item interactions
	look at how similar user and items are: pairwise packet in sklearn (cosine metric)
	recommend the top k recommendations for a specific user

Content based:
	tf-idf on film description: this allows later to define content based recsys. TfidfVectorizer allows to compute a vector for each entry in a list.
	We could also embed with Bert each entry and then compute the cosine similarity between different vectors.