# Movie Recommendation System

## Project Overview
This project implements a movie recommendation system using collaborative filtering.
The goal is to recommend relevant movies to users based on historical rating behavior.

The project follows a complete recommendation workflow, starting from exploratory data analysis,
building a baseline model, implementing item-based collaborative filtering, and evaluating the system
using ranking-based metrics.


## Dataset
- Source: MovieLens Dataset (GroupLens)
- Version: MovieLens 100K
- Files used:
  - `ratings.csv`: user–movie ratings
  - `movies.csv`: movie titles and genres

Each row in the ratings dataset represents an explicit rating given by a user to a movie.


## Tools & Technologies
- Python
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn


## Exploratory Data Analysis (EDA)
The following steps were performed:
- Inspection of dataset structure and size
- Analysis of rating distribution
- Identification of sparsity in the user–item matrix
- Exploration of movie popularity based on rating counts

Key observation:
- Ratings are skewed toward higher values, indicating positive feedback bias, which is common in real-world recommender systems.


## Baseline Model: Popularity-Based Recommendation
Before applying machine learning, a popularity-based recommender was implemented.
Movies with a sufficient number of ratings were ranked by average rating to provide a simple baseline.

This approach helps address cold-start scenarios and provides a reference point for model evaluation.


## Collaborative Filtering (Item-Based)

### Approach
An item-based collaborative filtering approach was used:
- A user–item rating matrix was created
- Movies with very few ratings were filtered out to reduce noise
- Cosine similarity was computed between movie vectors
- Movies with the highest similarity scores were recommended

This approach recommends movies that are frequently rated similarly by users.


## Evaluation

### Metric
The system was evaluated using **Precision@K**, a ranking-based metric commonly used in recommender systems.

### Method
- A time-aware train/test split was applied
- The most recent interaction of each user was held out for testing
- Recommendations were generated based on training data only to avoid data leakage

Precision@K values are expected to be modest due to data sparsity and the simplicity of the model.
The goal of evaluation was to validate recommendation logic rather than optimize performance.


## Key Insights
- User–item interaction data is highly sparse
- Popular movies tend to dominate similarity-based recommendations
- Collaborative filtering captures user behavior patterns rather than content similarity
- Evaluation metrics should be interpreted carefully due to positive rating bias



## What I Learned
- How recommendation systems differ from traditional prediction problems
- How to build a collaborative filtering model from scratch
- How to handle sparsity and popularity bias
- How to evaluate recommender systems using ranking-based metrics
- How to interpret and communicate model results effectively



## Future Improvements
- Incorporate content-based features (genres, tags)
- Experiment with user-based collaborative filtering
- Apply matrix factorization techniques
- Improve evaluation with additional metrics

