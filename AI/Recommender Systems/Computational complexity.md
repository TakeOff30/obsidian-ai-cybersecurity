Both [[User-based collaborative filtering]] and [[Item-based collaborative filtering]] predict ratings for a given user-item combination. A Naive approach is to compute all the possible predictions and rank them but this is inefficient.

Modern systems adopt a two-phase computation strategy:
- **offline phase**: involves performing expensive tasks in advance such as precomputing similarit matrices. It takes $O(m^2 * n)$ or $O(n*n^2)$ time and wastes quadratic space.
- **online phase**: generates faster recommendations by performing lightweight operations at query time for example the final recommendation score is computed by multipling the precomputed similarity values with user ratings. It takes $O(k*n)$ or $O(k*m)$ where $k$ is the number of nearest neighbours.
This ensures low latency recommentations.