A **recommender system** is an information filtering system that predicts and suggests items to users based on their preferences, behaviors, or interactions. These systems are commonly used in online platforms like e-commerce sites, streaming services, and social media to enhance user experience by providing personalized recommendations.

A recommender system, or a recommendation system (sometimes replacing 'system' with a synonym such as platform or engine), is a subclass of information filtering system that seeks to predict the "rating" or "preference" a user would give to an item

- Useful to filter information and prevent overload
- User experience/personalization
- Long tail phenomenon (physical institutions provide only the most popular items, while online services provide the entire range of items)

Recommender systems can either be personalized, non personalized (new customers, collective preferences), collaborative filtering, content based, hybrid.

Filter bubble: when developing a recsys the things you like will be pushed more by the algorithm. Can make people more biased

Metrics in RecSys are important: while **ACCURACY** (correctly predicting ratings) is a fundamental metric, it is **not the only factor** in recommendation quality, for example we care also for:

1.       **DIVERSITY** – ensuring recommendations **span different genres, categories, or interests**.

2.       **SERENDIPITY** – Introducing **unexpected but relevant** recommendations to enhance user discovery.

3.       **NOVELTY** – Prioritizing **new content** over repeatedly recommending the same items.

4.       **EXPLAINABILITY** – Providing users with reasons for recommendations (e.g., "Because you watched X").

Without considering these additional metrics, recommendation systems can become **too predictable**, leading to user fatigue.

