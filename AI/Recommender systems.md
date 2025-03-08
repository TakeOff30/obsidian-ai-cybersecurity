A **recommender system** is an information filtering system that predicts and suggests items to users based on their preferences, behaviors, or interactions. These systems are commonly used in online platforms like e-commerce sites, streaming services, and social media to enhance user experience by providing personalized recommendations.

A recommender system, or a recommendation system (sometimes replacing 'system' with a synonym such as platform or engine), is a subclass of information filtering system that seeks to predict the "rating" or "preference" a user would give to an item

- Useful to filter information and prevent overload
- User experience/personalization
- Long tail phenomenon (physical institutions provide only the most popular items, while online services provide the entire range of items)

Recommender systems can either be personalized, non personalized (new customers, collective preferences), collaborative filtering, content based, hybrid.

Filter bubble: when developing a recsys the things you like will be pushed more by the algorithm. Can make people more biased

the best possible algorithm is not the optimal one

Big data is the most valuable asset in this context

initially we let people interact and observe behaviours

ethical concerns: every policy implemented in the recsys can have effects and bad stuff on others

For the user we should help the user find resources it likes based on its interests, easy to use, no query, no explicit feedback

dual time

scalability

General RecSys
	user item interaction matrix, it records any kind of data that can correlate a user with a specific item. Users and items have specific features which can be fitted into a model and return recommendations
	
	
Shadow profile: a much more complex profile for each user can be built without requesting data to a user

