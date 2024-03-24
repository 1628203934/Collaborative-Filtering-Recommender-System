# Collaborative-Filtering-Recommender-System
## Data Source
The movie ratings and user Info comes from GroupLens website: https://grouplens.org/datasets/movielens/1m/. The dataset contains 1m ratings to support building a recommender system
## Tools used in this project:
### Recommender System Implementation:
Pandas,
Numpy,
Sklearn
### API:
streamlit
Plotly
## Idea
This project aims to use user-based collaborative filtering to recommend movies to a given user. There are following main step:
### 1. Acquiring movie ratings and movie information dataset and merge them into one based on movie Id
### 2. Generating user-item interaction matrix for CF
### 3. compute cosine similarity between each user and other users to find most similar users
### 4. Ultilize the cosine similarity matrix to compute/ predict the movies out target user has not been watched yet
### 5. Find similar users based on similarity matrix, then use "similarity * rating of the movie" to get movies ratings of these similar users and recommend to target user based on the computed score.
### 5. Build an automation function such as given a user_id, top-N movies' names will be provided
## reflection
### 1. During the similarity score computing process, we only consider movies that similar users has rated before. Hence, movies that has never been interacted by any user (in real world, especially those recent released movies) will not have a chance to be considered until there are ratings for them. This is what is called cold-start for recommender systems, which could be solved by content based filtering method
### 2. While exploring the interaction matrix, we compute the sparsity and get the value of 0.9553, which is of high sparsity and could lead to rather low accuracy for recommendations. This could be solved by filling each 0 / NA rating with 1(Bad) or 3(Average). However, we also need t o consider the impact of accuracy of the recommender system if we arbitrarily consider so.
