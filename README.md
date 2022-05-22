# Movie recommendation 
## 1. Content-based recomendation with TFIDF and Cosine
The content-based algorithm relies on the similarity of the items being recommended. The idea is that if the user likes an item, then suggest some similar items. To measure the similarity of two movies, features such as ***title, genre, introduction*** are used. The first task is that those features must be vectorized. After combining title, overview (a movie’s description), genres into a document calculated with ***TF-IDF*** to become a vector. Then, using ***cosine similarity*** to measure the similarity of two movies, the value of cosine measure ranges between -1 and 1, where -1 is dissimilar, and 1 is perfectly similar. The final result is a *similarity matrix* that is used to recommend movies having the largest distances to a given movie.
### Represent each movie as a vector using TF-IDF
TF-IDF stands for *Term Frequency-Inverse Document Frequency*. It is a formula to compute the weight of each word in a set of documents. The TF-IDF weight evaluates how important a word is. The importance increases proportionally to the number of times a word appears in the document but is offset by the frequency of the word in the corpus.

![TF-IDF formula](/images/tfidf.png).
### Cosine similarity
Cosine similarity is a formula to measure the distance of two vectors. Its result ranges from -1 to 1. In the content-based recomendation, cosine distance is used as a metric to represent how close a movie to another since all movies are transformed vectors with TF-IDF.

![Cosine similarity formula](/images/cosine.png).
## 2. Collaborative-Filtering
### Matrix Factorization
The main idea behind Matrix Factorization is to find two latent features that describe the
relationship between items and users. In the algorithms, the user ratings can be constructed as a
user-item rating matrix. Then, decompose the rating matrix into the product of two smaller
matrices (latent/factor matrices) that approximate the original matrix (See figure 8). The
algorithm will learn the latent preferences of the user and the latent attributes of items from the known rating matrix and then predict the unknown ratings through the dot product of the latent
features of users and items.

![An inlustration of matrix factorization](/images/mf.png).
### Online-Updating Regularized Kernel Matrix Factorization
An algorithm called Online-Updating Regularized Kernel Matrix Factorization which is based on matrix factorization. This algorithm is much faster at training compared to the normal matrix factorization. And, the trained model can be quickly updated with new users and new ratings.
