# Netflix Data Visualization & Classification

This project performs **exploratory data analysis**, **visualization**, and **classification modeling** on a real-world Netflix dataset, aiming to classify whether a content entry is a *Movie* or a *TV Show* based on its features like genre, duration, rating, and country of origin.

## Dataset

The dataset is a cleaned version of the Netflix catalog, containing **8,790+** entries and includes the following key columns:

- `show_id`: Unique identifier for each title
- `type`: Movie or TV Show (target variable)
- `title`, `director`, `country`, `date_added`, `release_year`
- `rating`: Content age rating (e.g., PG, TV-MA)
- `duration`: Runtime (minutes or no. of seasons)
- `listed_in`: Genres/categories

A few additional columns were engineered:
- `main_genre`: Primary genre derived from `listed_in`
- `org_country`: Original country of production
- `num_dur`: Numeric duration (in mins or number of seasons)

## 🛠️ Preprocessing

Data preprocessing pipeline includes:

1. **Feature Engineering:**
   - Extracted numeric duration (`num_dur`)
   - Simplified main genre and country fields

2. **Encoding & Scaling:**
   - Numerical features (`release_year`, `num_dur`) ➝ Scaled with `StandardScaler`
   - Categorical features (`main_genre`, `rating`, `org_country`) ➝ Encoded with `OneHotEncoder`

3. **ColumnTransformer** is used to streamline numeric and categorical transformations.

## Model

A supervised learning model was built using:

- **Model**: `RandomForestClassifier`
- **Training Technique**: `Pipeline` with preprocessing + model
- **Parameters**: `n_estimators=1000`, `random_state=42`

### Feature Importance

The trained model provides insights into which features are most predictive. Top features include:

- `main_genre_Anime Features`
- `main_genre_Action & Adventure`
- `rating_TV-MA`
- `org_country_United States`

Some features like `release_year` and `num_dur` had very low importance, indicating limited predictive power in this context.

## Model Evaluation

Standard evaluation metrics were used:

- **Confusion Matrix**
- **Classification Report** (precision, recall, f1-score)
  
These performance metrics allow us to assess how well the classifier distinguishes between Movies and TV Shows.

## Requirements

The notebook uses the following libraries:

pandas
numpy
matplotlib
seaborn
scikit-learn


## How to Run

1. Clone this repository
2. Open the `Netflix_DV.ipynb` Jupyter Notebook
3. Run all cells in order

Make sure the dataset is preloaded, or modify the notebook to load the CSV file if needed.

---

## Project Structure
Netflix_DV.ipynb # Main notebook containing code and outputs
README.md # Project documentation


---

## Acknowledgements

Netflix's public dataset inspired this project. This notebook simplifies and analyzes key trends for educational purposes.




