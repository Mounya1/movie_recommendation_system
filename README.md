# movie_recommendation_system



#  Movie Recommendation System

##  Overview

This project explores different approaches to building a **movie recommendation system**, starting from simple popularity-based logic to more advanced **collaborative** and **content-based filtering** techniques.

The goal is to recommend movies that users are most likely to enjoy — either by analyzing overall trends, understanding user behavior, or studying the content of the movies themselves.

---

##  Dataset

The dataset used is the **MovieLens dataset**, one of the most widely used sources for building recommender systems. It includes:

* **movies.csv** — Movie titles and genres.
* **ratings.csv** — User ratings (user ID, movie ID, rating, timestamp).

The data was merged using the `movieId` column to create a unified dataset for analysis.

---

##  Data Preprocessing

The preprocessing steps involved:

* Removing missing and duplicate values.
* Merging movie and rating datasets.
* Calculating each movie’s **average rating** and **total number of ratings**.
* Filtering out movies with very few ratings to maintain statistical significance.

The resulting dataset provided a clean foundation for analysis and model building.

---

##  Exploratory Data Analysis (EDA)

EDA was performed to understand user behavior and rating patterns.

**Key observations:**

* Most users rated movies between **3.0 and 4.5**, showing moderate-to-high satisfaction.
* Genres such as *Drama*, *Action*, and *Comedy* were the most frequent.
* A few timeless classics consistently scored high ratings across different users.

Visualizations, including histograms, bar charts, and correlation plots, were created to better understand the dataset’s distribution and trends.

---

##  1. Popularity-Based Recommendation System

The **popularity-based approach** recommends movies based on two metrics:

* **Average Rating** (user satisfaction)
* **Number of Ratings** (movie popularity)

By combining both, we avoid recommending rarely rated but high-scoring movies.

<img width="1076" height="468" alt="image" src="https://github.com/user-attachments/assets/91906b53-0074-4d9d-913e-926d7d947b6d" />


**Visualization Output:**
A bar chart showing the top-rated movies was generated.

* The **x-axis**: Average Rating
* The **y-axis**: Movie Titles
* **Color intensity**: Number of Ratings

This helped visually identify both quality and popularity.



##  2. Collaborative Filtering

Collaborative Filtering focuses on **user behavior** rather than movie attributes. It assumes that **users who rated similar movies similarly in the past will share future preferences**.

###  Two main types of collaborative filtering:

1. **User-Based Filtering:**

   * Finds users with similar rating histories.
   * Recommends movies liked by those similar users.

2. **Item-Based Filtering:**

   * Finds movies similar to the ones a user already liked.
   * Recommends those similar movies based on correlation scores.

###  Key Insights:

* Collaborative filtering produces **personalized** recommendations.
* It adapts over time as more users rate movies.
* However, it struggles with **new users or movies** (the *cold start problem*).

**Example Output:**
Movies recommended for user 15:
→ *Legends of the Fall (1994)*, *Wallace & Gromit: A Close Shave (1995)*, *Godfather, The (1972)* — based on similarity of user preferences.




---

##  3. Content-Based Filtering

Content-based filtering recommends movies based on their **features**, such as genres, keywords, or descriptions.

###  How it works:

* Each movie is represented as a **feature vector** (e.g., genre, actors, director).
* The system calculates **similarity scores** (using cosine similarity or TF-IDF).
* Movies with the highest similarity to the ones a user liked are recommended.

###  Example Output:

If a user likes *Toy Story (1995)*, the system might recommend:
→ *Missing Link (2019)*, *Toy Story Toons: Small Fry (2011)*, *Toy Story Toons: Hawaiian Vacation (2011)*, *Boxtrolls, The (2014)*, *Aladdin (1992)*

###  Advantages:

* No need for user data — works even for **new users**.
* Provides **explainable recommendations** (“because you liked X”).
* Best used when metadata (genre, keywords, descriptions) is rich.

---



## Future Enhancements

* Combine models into a **Hybrid Recommender System** for better accuracy.
* Incorporate **deep learning-based embeddings** for advanced similarity detection.
* Deploy as an interactive web app using **Streamlit or Flask**.


---

Would you like me to add a **diagram or flowchart** section showing how the three recommendation systems (Popularity, Collaborative, Content-Based) work and connect? It’ll make your README visually stronger for presentations or GitHub.
