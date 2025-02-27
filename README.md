# Team_OA2_Unsupervised_Learning_Streamlit/ The Phoenix Team

# Streamlit Anime Recommendation App

## Overview
The Streamlit Anime Recommendation App is a web-based application that provides personalized anime recommendations. Users can register, log in, search for anime, receive recommendations, rate anime, and maintain a watchlist. The app leverages various machine learning techniques to enhance the user experience and improve recommendation accuracy.

### Features
1. User Authentication:
* Registration and Login functionality.
* Password protection for user accounts.
* Logout option to end user sessions.

2. Anime Search:
* Search for anime by name.
* Display details of the searched anime.
* Show top 10 recommendations based on the searched anime.

3. Recommendations:
* Personalized anime recommendations based on user preferences and ratings.
* Genre-based recommendations.

4. Watchlist Management:
* Add anime to a personal watchlist.
* View and manage the watchlist.

5. Rating System:
* Rate anime to improve recommendations.
* Display average user ratings for each anime.


### Installation

#### Prerequisites
* Python 3.12 or more
* Streamlit
* pandas
* numpy
* scikit-learn
* scipy
* difflib
* requests
* re


### Installing Required Packages

#### You can install the required packages using pip:
* bash
* * pip install streamlit pandas numpy scikit-learn scipy difflib requests

### Running the App

#### To run the app, execute the following command in your terminal:
* bash
* * streamlit run prototypee_notebook.py



### Detailed Functionality

#### User Authentication
* Registration: Users can register with a unique username and password. The user profiles are stored in st.session_state.
* Login: Users can log in using their registered credentials. Successful login sets the current_user in st.session_state.
* Logout: Users can log out, which clears the current_user from st.session_state and forces a rerun of the app to redirect to the login/register page.

#### Anime Search
* Users can search for an anime by entering the name in the search bar.
* The app displays the details of the searched anime first.
* Below the searched anime, the app displays the top 10 recommendations based on the searched anime.

#### Recommendations
* Genre-based Recommendations: The app provides recommendations based on specific genres like Comedy, Action, and Romance.
* Personalized Recommendations: The app uses KMeans clustering on PCA-reduced features to recommend anime similar to the user's preferences.

#### Watchlist Management
* Users can add anime to their watchlist by clicking the "Add to Watchlist" button.
* The watchlist is stored in the user's profile within st.session_state.
* Users can view and manage their watchlist from the Watchlist page.

#### Rating System
* Users can rate anime on a scale of 1 to 10.
* The app stores the ratings in st.session_state.
* Average user ratings for each anime are displayed on the anime detail page.


### Code Structure
The main file app.py contains the entire code for the application, including user authentication, search functionality, recommendations, watchlist management, and the rating system.


### Key Functions
1. register_user(username, password): Registers a new user.
2. login_user(username, password): Logs in a user.
3. logout_user(): Logs out the current user.
4. recommend_anime_by_name(anime_name, kmeans_model, features_reduced, anime_df, num_recommendations): Recommends anime based on the searched anime.
5. get_recommendations_by_genre(anime_df, genre, num_recommendations): Recommends anime based on a specific genre.
6. fetch_image_url(anime_name): Fetches the image URL of an anime from the Jikan API.
7. display_anime_info_with_button(anime_row, page): Displays anime information with an image and buttons.
8. add_to_watchlist(anime_row): Adds an anime to the user's watchlist.
9. submit_rating(anime_id, rating): Submits a user rating for an anime.
10. calculate_average_rating(anime_id): Calculates the average user rating for an anime.
11. update_anime_df_ratings(): Updates the anime DataFrame with user ratings.


### Data
* cleaned_anime.csv: Contains the cleaned anime dataset.
* cleaned_train.csv: Contains the cleaned training dataset with user ratings.

### Custom CSS
Custom CSS is used to style the sidebar and main content areas of the app.


### Known Issues and Limitations
* The app requires internet access to fetch images from the Jikan API.
* The current implementation stores data in st.session_state, which may not be persistent across sessions.
* Error handling for CSV file loading should be improved.


### Future Enhancements
* Implement persistent storage for user profiles and ratings.
* Enhance error handling and validation.
* Add more advanced recommendation algorithms.
* Improve UI/UX design.
