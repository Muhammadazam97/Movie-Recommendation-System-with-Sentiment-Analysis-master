
# Content-Based Movie Recommender System with Sentiment Analysis

This project recommends movies similar to the ones the user likes and performs sentiment analysis on user reviews for those movies.

## How It Works
The recommender system fetches movie details (title, genre, runtime, rating, poster, etc.) using the [TMDB API](https://developer.themoviedb.org/docs/getting-started). Using the IMDB ID, it retrieves user reviews from IMDB via web scraping with BeautifulSoup4 and performs sentiment analysis on these reviews.

### The Movie Cinema
I've developed a similar application called "The Movie Cinema," which supports movies in all languages. The main difference is that "The Movie Cinema" uses TMDB's recommendation engine. In this project, the recommendation part is customized but doesn’t support multi-language movies as it requires substantial RAM to process the Count Vectorizer matrix for over 700,000 movies on TMDB, even after deploying on Heroku.

Don't worry if your desired movie isn’t auto-suggested—just type the name and press "Enter" to continue, even with minor typos.

## Getting the API Key
1. Create an account on [TMDB](https://www.themoviedb.org/).
2. In your account settings, select the API option from the sidebar and fill out the required details to request an API key.
3. If asked for a website URL, enter "NA" if you don't have one.
4. Once approved, the API key will be visible in your API settings.

## Running the Project
1. Clone or download this repository to your local machine.
2. Install the required libraries using:
   ```bash
   pip install -r requirements.txt
   ```
3. Obtain your API key from TMDB (see above).
4. Replace `YOUR_API_KEY` in both occurrences (lines 15 and 29) in `static/recommend.js`.
5. From your project directory, run:
   ```bash
   python main.py
   ```
6. Open your browser and go to `http://127.0.0.1:5000/`.
7. Hurray! The project should be running.

## Project Architecture
![Architecture Diagram](https://github.com/Muhammadazam97/Movie_Recommendation_System_with_Sentiment_Analysis_master/blob/main/Arcitecture.PNG?raw=true)



## Similarity Score
The recommender system uses similarity scores to determine the most similar movies to those the user likes. A similarity score ranges from 0 to 1, where a higher score indicates higher similarity based on the textual details of each item.

### Cosine Similarity
Cosine similarity is used to calculate the similarity between documents, regardless of their size. It measures the cosine of the angle between two vectors projected in a multi-dimensional space, where a smaller angle signifies greater similarity. Cosine similarity is particularly useful as it remains reliable even if two documents are significantly different in length.

![Cosine Diagram](https://github.com/Muhammadazam97/Movie_Recommendation_System_with_Sentiment_Analysis_master/blob/main/Cosine.PNG)

Learn more about [Cosine Similarity here](https://www.machinelearningplus.com/nlp/cosine-similarity/).

## Dataset Sources
- [IMDB 5000 Movie Dataset](https://www.kaggle.com/carolzhangdc/imdb-5000-movie-dataset)
- [The Movies Dataset](https://www.kaggle.com/rounakbanik/the-movies-dataset)
- [List of Movies in 2018](https://en.wikipedia.org/wiki/List_of_American_films_of_2018)
- [List of Movies in 2019](https://en.wikipedia.org/wiki/List_of_American_films_of_2019)
- [List of Movies in 2020](https://en.wikipedia.org/wiki/List_of_American_films_of_2020)

