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


