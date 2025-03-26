# Movie Recommender System

## Overview:
This project is a content based Movie Recommender System built using Natural Language Processing (NLP) and Machine Learning. It provides personalized movie recommendations based on content similarity. The application is deployed using Streamlit and fetches movie details from the TMDB API.

## Features:
1) Provides movie recommendations based on content similarity.
2) Uses TF-IDF & Cosine Similarity for recommendations.
3) Fetches movie posters dynamically from TMDB API.
4) Interactive Streamlit user interface.
5) Uses Google Drive to store and fetch large files efficiently.

## Dataset:
1) The model is trained on TMDB 5000 Movies Dataset taken from kaggle, which consists of:
   a) Movie details such as title, genres, keywords, cast, and crew.
   b) Metadata processing to generate a content-based recommendation system.

## Installation
1) Install Dependencies:Ensure you have Python 3.x installed, then run:   pip install -r requirements.txt

## How to Run the Application:
1) streamlit run main.py   or
2) https://movie-recommender-system-hc2hbbhdtmny2fxmvble6k.streamlit.app

## File Structure:
Movie-Recommender-System/
1) │── recommendation_system.ipynb  # Jupyter Notebook for training
2) │── main.py                      # Streamlit App
3) │── movie_list.pkl                # Pickle file containing movie metadata
4) │── similarity.pkl                 # Pickle file containing similarity matrix
5) │── requirements.txt              # Required libraries
6) │── README.md                     # Project Documentation

## Methodology:

1) Data Preprocessing:
  a) Merging movies.csv and credits.csv.
  b) Extracting relevant features (genres, keywords, cast, and crew).
  c) Removing spaces and converting text data into tokens.

2) Feature Engineering:
  a) Constructing tags by combining relevant metadata.
  b) Converting text data into numerical vectors using CountVectorizer.
  c) Computing Cosine Similarity to measure content similarity.

3) Building the Recommender System:
  a) Selecting a movie title.
  b) Identifying the top 5 similar movies using similarity scores.
  c) Fetching movie posters dynamically using the TMDB API.

4) Deployment Strategy:
  a) The trained model is saved as a .pkl file for faster loading.
  b) Large files (e.g., similarity.pkl) are stored on Google Drive and fetched dynamically to reduce local storage issues.

5) API Usage: We use TMDB API to fetch movie posters dynamically:

def fetch_poster(movie_id):
    url = "https://api.themoviedb.org/3/movie/{}?api_key=YOUR_API_KEY&language=en-US".format(movie_id)
    data = requests.get(url).json()
    return "https://image.tmdb.org/t/p/w500/" + data['poster_path']

## Technologies Used:
  a) Python (Pandas, NumPy, Scikit-Learn)
  b) Natural Language Processing (NLP)
  c) Machine Learning (Content-Based Filtering)
  d)  Streamlit (for Web UI)
  e) Pickle (for model serialization)
  f) Google Drive API (for fetching large files)
  g) TMDB API (for fetching movie posters)

## Application link:
https://movie-recommender-system-hc2hbbhdtmny2fxmvble6k.streamlit.app
