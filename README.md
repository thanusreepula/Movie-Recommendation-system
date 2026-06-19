# Movie-Recommendation-system
A content-based movie recommendation engine that suggests similar movies based on genre, keywords, and plot overview. Built in Google Colab using the TMDB 5000 dataset.

# Problem/Goal

Given a movie a user likes, recommend other movies they're likely to enjoy — without relying on other users' ratings (i.e., no collaborative filtering). This is solved with content-based filtering: each movie is represented as a text "tag" built from its genre, keywords, and overview, and similarity between movies is computed directly from that text.

# Dataset

The TMDB 5000 Movie Dataset, loaded from Google Drive as two CSVs:
tmdb_5000_movies.csv — 4,803 rows, 20 columns (budget, genres, keywords, overview, vote averages, etc.)
tmdb_5000_credits.csv — 4,803 rows, 4 columns (cast and crew)
Only the movies file is used in the final model. The columns kept were id, title, genres, keywords, overview, vote_average, and vote_count. The genres and keywords fields arrive as stringified lists of dictionaries (e.g. [{"id": 28, "name": "Action"}, ...]) and were parsed with ast.literal_eval to extract just the genre/keyword names. The overview text was tokenized by splitting on whitespace, then combined with the genre and keyword lists into a single lowercase tags string per movie — this tags field is what the model is actually trained on.

# Tech Stack
Python(pandas, numpy, scikit-learn )
Google Colab
# How to Run It
1. Download the notebook and both dataset CSVs.
2. Upload both to your Google Drive.
3. Open notebook in Colab, run first cell to mount Drive.
4. Update both file paths to your Drive location.
4. Run all cells, then call recommend('Movie Title') with an exact title from the dataset.
