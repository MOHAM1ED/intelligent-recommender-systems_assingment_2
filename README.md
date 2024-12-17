# intelligent-recommender-systems_assingment_2
# TMDb-Based Collaborative Filtering Dataset Preparation

This project involves preparing a dataset for a collaborative filtering recommendation system using the TMDb API. The code fetches popular movie data, simulates user ratings, selects active users and target items based on specific criteria, and calculates thresholds for co-rated items.

## Features
- Fetch popular movie data from the TMDb API.
- Simulate user ratings for movies with configurable missing ratings.
- Select active users based on missing ratings.
- Identify target items based on missing percentage of ratings.
- Visualize the distribution of ratings per item.
- Calculate thresholds for co-rated items.
- Save the final user-item rating matrix as a CSV file.

## Prerequisites
- Python 3.7+
- Required Python libraries:
  - `requests`
  - `pandas`
  - `numpy`
  - `matplotlib`

Install the required libraries using pip:
```bash
pip install requests pandas numpy matplotlib
```

## Getting Started
1. **Clone the repository**:
   ```bash
   git clone <repository_url>
   cd <repository_directory>
   ```

2. **Add your TMDb API key**:
   Replace the placeholder `api_key` in the script with your TMDb API key.

3. **Run the script**:
   Execute the script to fetch data, simulate user ratings, and save the user-item matrix:
   ```bash
   python main.py
   ```

## Functions Overview

### 1. `fetch_popular_movies(api_key, total_pages=5)`
Fetches popular movies from the TMDb API over multiple pages.
- **Parameters**:
  - `api_key`: Your TMDb API key.
  - `total_pages`: Number of pages to fetch (default is 5).
- **Returns**: A list of popular movies.

### 2. `simulate_ratings(movies, num_users=50, missing_percentage=0.2)`
Simulates user ratings for movies with random values and missing ratings.
- **Parameters**:
  - `movies`: List of movie dictionaries.
  - `num_users`: Number of simulated users (default is 50).
  - `missing_percentage`: Fraction of missing ratings (default is 0.2).
- **Returns**: A user-item rating matrix as a Pandas DataFrame.

### 3. `pick_active_users_and_items(user_item_matrix)`
Selects active users based on specific missing ratings and target items based on missing percentages.
- **Parameters**:
  - `user_item_matrix`: User-item rating matrix.
- **Returns**: A dictionary of active users and target items.

### 4. `plot_ratings_distribution(user_item_matrix)`
Plots the number of ratings for each item in the dataset.
- **Parameters**:
  - `user_item_matrix`: User-item rating matrix.

### 5. `calculate_threshold(user_item_matrix, active_users)`
Calculates thresholds for co-rated items for active users.
- **Parameters**:
  - `user_item_matrix`: User-item rating matrix.
  - `active_users`: Dictionary of active users.
- **Returns**: Thresholds for each active user.

## Output
- **User-Item Rating Matrix**: Saved as `user_item_matrix.csv` in the project directory.
- **Active Users and Target Items**: Displayed in the console output.
- **Ratings Distribution Plot**: Shown during execution.

## Example Console Output
```text
Dataset prepared successfully.
Active Users: {'U1': 'U3', 'U2': 'U7', 'U3': 'U12'}
Target Items: {'I1': '12345', 'I2': '67890'}
Thresholds: {'U1': 25, 'U2': 20, 'U3': 18}
```

## License
This project is licensed under the MIT License. See the `LICENSE` file for details.

## Acknowledgements
- [TMDb API](https://www.themoviedb.org/documentation/api) for movie data.
- Python libraries for data processing and visualization.

## Author
Mohamed Ibrahim

