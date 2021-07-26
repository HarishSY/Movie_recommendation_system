# Movie_recommendation_system
Movie recommendation system using Cosine similiarity

The data using to predict the movie collected from Kaggle.
1) tmdb_5000_credits
2) tmdb_5000_movies and
3) bollywood_full_1950-2019

We created user login and register forms to enable any user activate and use movie recommendation system app.
The user data will be saved on SQL server. We used SQLAlchemy to store user information in this project

The first stage in the this project is to data collectiona and Data preparation.
This process saved on under datapreprocessing.ipynb Notebook.

The 2nd stage is to evaluate and model in production.
We used Cosine Similarity function to find the distance between the vector points.

Cosine similarity is a method to measure the difference between two non zero vectors of an inner product space. See the example below to understand.
Suppose I want to check if Bernard and Clarissa have similar movie preferences, and I only have two movie reviews. The reviews are scores from 1 to 5, where 5 is the best score and 1 the worst, and 0 means that a person has not watched the movie.

![image](https://user-images.githubusercontent.com/33517532/127052617-bd8f26d9-79a5-45d6-a05a-d24862005134.png)


I can represent each person’s reviews in a separate vector.
![image](https://user-images.githubusercontent.com/33517532/127052651-c68e1ce5-9bb7-4da2-a417-d605a5e909a9.png)


Vector b represents Bernard and vector c Clarissa.
The cosine similarity will measure the similarity between these two vectors which is a measurement of how similar are the preferences between these two people.

In the image, below each vector represents a person’s preferences and they have an angle θ between them. Similar vectors will have a lower angle θ, and dissimilar vectors (different film preferences) will have bigger θ.

![image](https://user-images.githubusercontent.com/33517532/127052683-098a0ba5-f8c7-4b67-9460-0e700f9be0f2.png)

In the example above the similarity 0.989 is close to the maximum value of 1, this means that given only two movie reviews the two users have similar preferences.
Theoretically, the cosine similarity can be any number between -1 and +1 because of the image of the cosine function, but in this case, there will not be any negative movie rating so the angle θ will be between 0º and 90º bounding the cosine similarity between 0 and 1. If the angle θ = 0º =>cosine similarity = 1, if θ = 90º => cosine similarity =0.
The cosine similarity can be calculated for more than 2 movies. In the example below I will add the ratings for a movie that Bernard liked and Clarissa disliked this should decrease cosine similarity value.

