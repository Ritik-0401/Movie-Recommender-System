# Movie-Recommender-System
## Overview

This project implements a content-based movie recommendation system using the TMDB 5000 Movie Dataset. The system recommends movies based on their similarity to a given movie, leveraging features such as genres, keywords, cast, crew, and overview. The recommendation model uses text processing and cosine similarity to identify movies with similar content.

## Dataset

The dataset used for this project is the TMDB 5000 Movie Dataset available on Kaggle. It consists of two main files:

tmdb_5000_movies.csv: Contains movie details such as genres, keywords, overview, budget, revenue, and more.

tmdb_5000_credits.csv: Includes cast and crew information for each movie.

## Project Structure
Notebook: Movie Recommender System (Content-based).ipynb
Contains the complete code for data preprocessing, feature engineering, vectorization, similarity computation, and recommendation logic.

Output Files:

movie_dict.pkl: Pickle file containing the processed movie dataset as a dictionary.

similarity.pkl: Pickle file storing the cosine similarity matrix for movie recommendations.



## Methodology

### Data Preprocessing:

Merged the movies and credits datasets on the title column.

Selected relevant features: movie_id, original_title, genres, keywords, overview, cast, and crew.

Processed text data by converting lists to strings, removing spaces from multi-word entries (e.g., "Science Fiction" to "ScienceFiction"), and applying stemming to normalize words.

Combined features into a single tags column for each movie.



### Feature Vectorization:

Used CountVectorizer from scikit-learn to convert the tags column into a numerical vector representation, with a maximum of 5,000 features and English stop words removed.

### Similarity Computation:

Computed cosine similarity between movie vectors to measure content similarity.



### Recommendation Function:

Created a recommend function that takes a movie title as input and returns the top 5 most similar movies based on cosine similarity scores.


### Serialization:

Saved the processed dataset and similarity matrix using pickle for use in deployment.


## Dependencies

Python 3.11

Libraries: pandas, numpy, nltk, scikit-learn, pickle
  
Install dependencies using: pip install pandas numpy nltk scikit-learn

