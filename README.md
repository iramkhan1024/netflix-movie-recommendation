# Netflix-movie-recommendation
Project based on Netflix movie recommendation for making recommendation system by analyzing customer movie ratings.
# 🎬 Netflix Movie Recommendation System And Data Analytics

An end-to-end data analytics and recommendation engine built on the Netflix Prize Dataset (~24M user reviews). This project performs large-scale data wrangling, threshold benchmarking , exploratory data analysis, and implements collaborative filtering using Singular Value Decomposition (SVD).

---

## Project Overview ?
1. **Cleans Data:** Cleans over 24 million movie ratings and handles missing values.
2. **Filters Outliers:** Removes inactive users and movies with very few ratings to improve performance.
3. **Builds a Recommendation Model:** Uses **Singular Value Decomposition (SVD)** from the `scikit-surprise` library to predict what rating a user would give to movies they haven't watched yet.
4. **Gives Top Recommendations:** Generates top personalized movie recommendations for a user.

---

## 📊 Dataset Summary
* **Raw Ratings:** 24,058,263 interactions
* **Unique Customers:** 470,758
* **Unique Movies Evaluated:** 4,499
* **Source:** Netflix Prize Dataset (Kaggle)

---

## ⚙️ Methodology & Architecture

### 1. Data Cleaning & Transformation
- **Fixing the Layout:** The original raw file had movie titles and user ratings mixed together. The script separated them neatly so every rating matches the correct movie and user.
- **Null & Duplicate Handling:** Removed blank, broken, or duplicate rows to keep the data clean and accurate.

### 2. Filtering Out Inactive Data
Working with 24 million rows can slow down the computer, and items with few ratings confuse the model. A **60% cutoff rule** was applied to keep only high-activity data:
- **Unpopular Movies:** Removed movies with fewer than ~908 ratings (dropped ~2,700 titles).
- **Inactive Users:** Removed users who rated fewer than ~36 movies (dropped ~282,000 accounts).
- **Clean Result:** Reduced the data to **19.7 million high-quality ratings**, making it faster to train and more accurate.

### 3. Model Building & Cross Validation
- **Algorithm:** Used **Singular Value Decomposition (SVD)** from `scikit-surprise` to find rating patterns and predict scores for unseen movies.
- **Validation:**  Tested the model across 3 separate splits of data to confirm reliable predictions.
- **Performance Metric:** Root Mean Squared Error (RMSE) achieved ~**0.968**.

---

**Top 5 Recommended Titles:**
| Rank | Movie Title | Release Year | Predicted Score (1-5) |
| :--- | :--- | :--- | :--- |
| 1 | **Sex and the City: Season 4** | 2001 | **4.30** |
| 2 | **Chappelle's Show: Season 1** | 2003 | **4.28** |
| 3 | **North by Northwest** | 1959 | **4.23** |
| 4 | **Star Trek: Deep Space Nine: Season 5** | 1996 | **4.23** |
| 5 | **Aqua Teen Hunger Force: Vol. 1** | 2000 | **4.21** |

---
## 🛠️ Tools Used

- **Python**: Main programming language
- **Pandas & NumPy**: For cleaning and organizing data
- **Matplotlib & Seaborn**: For making charts and graphs
- **Scikit-Surprise**: For building the movie recommendation model


---
