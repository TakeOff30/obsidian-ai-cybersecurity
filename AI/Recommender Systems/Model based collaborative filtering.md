Model based methods introduce Machine Learning models to generailize and predict ratings based on learned patterns.
This is possible because collaborative filtering is closely related to classical Machine Learning problems, however, there are differences that make collaborative filtering a more abstract generalization and this means that we cannot apply any ML algorithm directly:
- when we consider a [[Rating matrix]] we cannot identify a test set and training set without removing specific users or features from the training.
- data could be sparse and some ratings could need to be predicted.

Latent models such as *Matrix factorization* are widely used because allow to handle sparse data. Other advantages are:
- space efficiency: no need to store the entire user-item matrix but only the model parameters
- training efficiency: no need to calculate the entire matrix all over again but rather use learned parameters and update them.
- we can adopt **regularization** parameters to reduce overfitting.
- scalability: recommendations are optimized in a single forward pass.

The easier way to implement ML is to use Naive Bayes collaborative filtering.
We compute the probability of a user u will rate an item j with a specific value:
$$
	P(r_{uj}=v_{s}|observed ratings in l_{u}), \forall s \in \{1,...,l\}
$$
$$
P(r_{uj}=v_{s}|observed ratings in l_{u})=\frac{P(r_{uj}=v_{s})*P(observed ratings in l_{u}|r_{uj}=v_{s})}{P(observed ratings in l_{u})}
$$
where:
- $P(r_{uj}=v_{s})$ estimated as the fraction of users that have rated with $v_{s}$ the $j-th$ item.
- assuming independence:$$
	\prod_{k \in l_{u}} P(r_{uk}|r_{uj}=v_{s})$$
- the denominator is used as a normalization factor.
This formula allows us to estimate missing ratings by computing probabilities for all possible rating values (e.g., 1 to 5 stars) and selecting the most probable one. Then we compute the estimated score for $r_{uj}$ in the rating matrix.
The complexity of the procedure is $O(n)$ where n is the number of missing values in the matrix. While the complexity is reduced, being that in practice user-item matrices are 99% sparse it is still not a feasible solution.

The state of the art in RecSys is instead the family of **Latent Factor Models**. The idea is to use dimensionality reduction and compressing the user-item matrix which can be obtained by reducing, rotating and estimating even from a highly incomplete matrix.
The idea is to take the $R$ user-item matrix $(n\times m)$ and factorize it such that:
$$
R=U\times V^T
$$
where:
- $U (m\times k)$: Represents users in a K-dimensional latent space.
- $V (n\times k)$: Represents items in the same latent space.
- $K$ is much smaller than m and n, making computation efficient.
This works because real world data is redundant and the relationships between similar users are caught in these low-rank aproximations.


