Aims to find the most similar users or items to a target element. Based on the similarity the items or users are filtered to generate recommendations. 

This method is further classified as neighborhood-based because the goal is to find the most similar entities in a given space.

The core assumption of collaborative filtering is that similar users exhibit similar rating patterns and similar items receive similar ratings.

Types of Neighborhood-Based Collaborative Filtering:
- [[User-based collaborative filtering]]
	- Strengths: captures **user similarity** well and it can generalize across **diverse tastes**.
	- Weaknesses: the recommentations are difficult to explain to the user, it needs frequent updates and struggles when users have distinct interests.
- [[Item-based collaborative filtering]]
	- Strengths: tends to be more peronalized, provides higher accuracy, it is easier to explain and more stable over time because item catalogues remain relatively stable.
	- Weaknesses: requires high quality item metadata and may overfit on a users' history reducting diversity.

All Neighborhood-Based Collaborative Filtering algorithms rely on a **[[Rating matrix]]**.

In general collaborative filtering methods have the following streghts and weaknesses:
- Strengths:
	- simple becasue the formulas reflect real world user behaviour
	- easy to implement
	- debuggable and easy to maintain
	- stable and interpretable
- Weaknesses:
	- computational complexity
	- sparsity problem because many user-item interaction are unobserved

Often user-based and item-based models are combined:
- Compute **row-wise similarities (user-based)** and **column-wise similarities (item-based)**.
- Take a **weighted average of both similarity scores** to generate predictions.

To speed up computation **dimensionality reduction** can be applied with techniques such as PCA or SVD but before applying them the missing ratings have to be estimated. PCA introduces bias meaning that two items may have identical ratings but different computed covariance values. To reduce bias we can use probabilistic techniques such as Maximum Likelihood Estimation.

As an alternative we can also formulate rating predictions as a regression problem.
We can predict the right rating $r_{u,j}$ using the following formulation:
$$
\hat{r}_{uj}=\mu_{u}+
\frac
{\sum_{v \in P_{u}(j)} Sim(u,v)*s_{vj}}
{\sum_{v \in P_{u}(j)}{|Sim(u,v)|}} 
$$
where ${P_{u}(j)}$ is the nearest $k$ nearest users.
Ratings are predicted as a **weighted LINEAR COMBINATION** of ratings of the same item. That is very similar to linear regression formula.
This can be applied to both **user-based and item-based filtering**.

This formulation however only allows us to catch direct relationships between user-user or item-item. To introduce nonlinearity and capture more complex relationships we should use alternative machine learning methods (such as [[Neural Network]]s).

We can refine the user-based predictions introducing a parameter $w_{vu}^{user}$ which is an explicit weight to be learned for each user-item pair:
$$
\hat{r}_{uj}=\mu_{u}+\sum_{v\in P_{u}(j)} w_{vu}^{user}*(r_{vj}-\mu_{v})
$$
where $P_{u}(j)$ in this case is define by determining the closest peers for each users and then retaining those for which we have ratings.

With gradient descent algorithms and cost functions such as:
$$
J_{u}=\sum_{j\in I_{u}} (r_{uj}-\hat{r}_{uj})^2
$$
This minimizes the squared difference between **true and predicted ratings,** similarly to traditional **regression models**.

**_We still have bias and sparsity issues_**, so we can introduce regularization and bias:
$$
\hat{r}_{uj}=b_{u}^{user}+b_{j}^{item}+\frac{\sum_{v\in P_{u}(j)} w_{vu}^{user}*(r_{vj}-b_{u}^{user}+b_{j}^{item})}{\sqrt{|P_{u}(j)|}}
$$
where:
- $b_{u}^{user}$ is the user bias (captures user-specific tendencies)
- $b_{j}^{item}$ is the item bias (captures item-specific popularity effects)

To obtain the most generic neighborhood based model we can merge the user-based and item-based models:
$$
\hat{r}_{uj}=b_{u}^{user}+b_{j}^{item}
+\frac{\sum_{v\in P_{u}(j)} w_{vu}^{user}*(r_{vj}-B_{vj})}{\sqrt{|P_{u}(j)|}}
+\frac{\sum_{j\in Q_{t}(u))} w_{jt}^{item}*(r_{uj}-B_{uj})}{\sqrt{|Q_{t}(u)|}}
$$
where $B_{ut}=b_{u}^{user}-b_{t}^{item}$.
By implementing this general framework:
- **The best-performing bias estimators can be selected per domain**.
- **Machine learning algorithms can be easily plugged into the model**
- **Performance can be optimized by fine-tuning individual components**.
