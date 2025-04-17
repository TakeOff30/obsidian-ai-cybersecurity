
The rating matrix is a $M*N$ matrix that represents $M$ users and $N$ items. The rating matrix $R[i,j]$ stores the rating given by the user $i$ on the item $j$.
We identify with $I_u$ the set of items rated by user $u$ and $I_u∩I_v$ the items rated by both the users $u,v$.
It contains information about interaction between items and users with different possible metrics.

The values can depend on:
- explicit feedback, directly from user input, accurate but difficult to collect.
- implicit feedback, derived from actions, easier to obtain and does not bother the user.

The rating matrix often has long tail distribution, small number of items receives most of the ratings. This makes it harder to use the data to train models and popular items are utterly favored.