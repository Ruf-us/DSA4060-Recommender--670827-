# DSA 4060 Personalized Movie Recommender

## Student Details
* **Student Name:** Rufinus Ogutu
* **Student ID:** 670827
* **Assigned User ID:** 17

## Project Objective
This project implements a personalized content-based movie recommender system for a streaming company. The system analyzes an assigned user's historical ratings to identify preferred genres and recommends five relevant movies that the user has not yet rated.

## Datasets
* **movies.csv:** Contains movie metadata including unique `movie_id`, `title`, and associated `genres`.
* **ratings.csv:** Contains historical user-item interactions including `user_id`, `movie_id`, and numerical `rating`.

## Method / Approach
1. **User Profiling:** Filtered ratings for Assigned User 17 and extracted positively rated movies ($\ge 4.0$).
2. **Feature Extraction:** Transformed movie genres into numerical feature vectors using scikit-learn's `CountVectorizer`.
3. **Similarity Calculation:** Computed cosine similarity across the genre matrix to measure how closely unrated movies match the user's liked movies.
4. **Filtering & Ranking:** Excluded already-rated movies and ranked remaining titles by aggregate similarity score.

## How to Run the Notebook
1. Ensure Python and Jupyter Notebook / VS Code are installed along with required packages (`pandas`, `numpy`, `scikit-learn`).
2. Place `movies.csv`, `ratings.csv`, and `DSA4060_Recommender_123456.ipynb` in the same directory.
3. Run the notebook cells sequentially from top to bottom.

## Recommendation Results
1. **Edge of Tomorrow** (Sci-Fi|Action)
2. **Inception** (Sci-Fi|Thriller)
3. **Interstellar** (Sci-Fi|Drama)
4. **Black Panther** (Action|Superhero)
5. **Avengers: Endgame** (Action|Superhero)

*Interpretation:* The recommended titles successfully target User 17's affinity for Sci-Fi and Action films, leveraging positive past engagement with movies like *The Matrix* and *Blade Runner 2049*.

## Limitation and Suggested Improvement
* **Limitation:** Relying solely on categorical genres ignores plot semantics and textual descriptions.
* **Improvement:** Implement TF-IDF vectorization on movie plot summaries weighted by user rating scores.
