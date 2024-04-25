# Data-Sourcing-Challenge

I worked with a LA on AskBSC-308443, 308584, 308614, tutor Mohammed Fauwaaz in a Tutor Session on BCS and ChatGPT to complete this assignment.

## Overview
Prepare data for a recommendation system to help people find movie reviews and related movies.

## Purpose
To extract data from The New York Times API and The Movie Database, then merge and clean the data for later use with natural language processing methods.

## Business Advantage [^1]

Due to the abundance of streaming content, recommender systems have become popular to help personalize platforms and help users find preferred content.
Recommender systems personalize the user experience which is a key business advantage because the more relevant the product, the higher the user engagement, resulting in an increase in revenue for the platform.

## Landscape

![Content_Recommendation](images/movie_system-1.webp)

Content-Based Movie Recommendation Systems use content-based machine learning algorithms to provide recommendations based on the similarity of movie attributes. For example, when the user watches a action movie starring Bruce Willis, the system recommends movies in the same genre, or starring the same actor, or both.

## Results

### Part 1
Using the base URL included in the starter code, a "query_url' was created that included string search variables filter_query, sort filter, field_list, and query dates, based on the NYT Article Search API documentation. A GET request, time.sleep function, and a try-except clause were included in several loops structured to go through a 20 page article query search and retrieve movie reviews while adhering to the API requirements. The reviews were stored in list that was converted into a dataframe using json_normalize due to the nested structure. A "title" column was created by extracting the unicode characters between \u2018 and \u2019 using the following lambda function: lambda title: title[title.find("\u2018")+1:st.find("\u2019 Review"). Additional dataframe manipulation also included turning the keywords columns into a string. Lastly the title column was turned into a list to be used in the query for The Movie Database.

### Part 2
A GET request, request_counter, time.sleep function, and a try-except clause were included in several loops structured to retrieve movies data from The Movie Database, per the API search & query documentation and based on the list of movies titles created from the reviews dataframe. Certain movie details were extracted from data and turned into lists. These lists were turned into a dictionary and appended to the tmdb_movies_list, that was later turned into a dataframe using the DataFrame function instead of json_normalize function given there were no nested objects.

### Part 3
The TMDB and reviews dataframe were merged together based on the movie titles. The merged dataframe was manipulated by converting certain columns to strings in order to remove unwanted characters, removing duplicate rows, and reseting the index. Lastly the data was exported to CSV without the dataframe index.

  
## Recommendations

![Content_Recommendation](images/movie_system-2.webp)

Collaborative Filtering Movie Recommendation Systems algorithm may provide a better user experience by incorporating past data of interactions between users and movies instead of making recommendations based on movie attributes. The combination of both the Content-Based & Collaborative Filtering systems is what is incorporated into most streaming platforms.

[^1]: https://towardsdatascience.com/how-to-build-a-movie-recommendation-system-67e321339109
