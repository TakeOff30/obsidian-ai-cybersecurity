Models which identify users who have similar rating patterns to a given user in order to generate preferences. 
Users with similar preferences in the past will have similar preferences in the future.

To identify the neighborhood of a user we compute the similarity score using a similarity function. This doesn't alwasy adapt good to reality because some users are more critical with ratings and others are more generous.

The first step to calculate similarity is to **normalize** the ratings by calculating the **mean rating** for each user $u$ and subtracting it to each rating. This normalization ensures that the differences in rating scales are accounted for making the comparisons more fair.

The most common similarity measure is the **Pearson Correlation** between users $u$ and $v$:
$$
Pearson(u, v) = \frac{
\sum_{k \in I_u \cap I_v} (r_{uk} - \mu_u)(r_{vk} - \mu_v)
}{
\sqrt{\sum_{k \in I_u \cap I_v} (r_{uk} - \mu_u)^2} \cdot \sqrt{\sum_{k \in I_u \cap I_v} (r_{vk} - \mu_v)^2}
}
$$
This formula focuses on $I_u\cap I_v$ items that both users have rated. 
It normalizes the ratings by subtracting the mean and computes the covariance between user ratings normalized by the standard deviation and outputs a value $[-1,1]$. 
The output is 0 if there is no correlation, -1 if the users are opposite and 1 if they are similar.
The **numerator** computes the **sum of products** of the centered ratings. This measures the degree to which two users’ ratings **deviate** from their respective means in the same direction.
The **denominator** ensures that:
- Differences in absolute rating magnitudes do not dominate similarity calculations.
- The final score remains within a bounded range (-1 to 1).

In production environments the user ratings are being updated often so we need to adopt a structured approach to understand when to update similarity.

We can use the Pearson Correlation to predict missing ratings for users:
$$
\hat{r}_{uj} = \mu_u + \frac{
\sum_{v \in P_u(j)} Pearson(u, v) \cdot s_{vj}
}{
\sum_{v \in P_u(j)} |Pearson(u, v)|
}
$$
Here $P_u(j)$ is the set of top-k most similar users to user $u$.
The **numerator** computes the weighted sum of deviations from mean ratings.
The **denominator** normalizes by total similarity values.
The **similarity score** (Pearson) weight the contribution of each neighbour
This ensures that *highly similar users have a stronger influence on predictions*.

To prevent the effect of the long tail distribution we can introduce a normalization factor 
$$
w_j=\log{\frac{m}{m_j}} \space \forall j \in \{1,...,n\}
$$
where $m_j$ is the number of ratings for the item $j$.
The Pearson similarity function becomes:
$$
Pearson(u, v) = \frac{
\sum_{k \in I_u \cap I_v} w_k (r_{uk} - \mu_u)(r_{vk} - \mu_v)
}{
\sqrt{\sum_{k \in I_u \cap I_v} w_k (r_{uk} - \mu_u)^2} \cdot \sqrt{\sum_{k \in I_u \cap I_v} w_k (r_{vk} - \mu_v)^2}
}
$$
This ensures that the system does not become overly biased toward frequently rated items.