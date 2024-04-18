# Data-Sourcing-Challenge

## Overview
Prepare data for a recommendation system to help people find movie reviews and related movies. Extract data from The New York Times API and The Movie Database, then merge the data together. Keep in mind, the text extracted from these APIs can later be used with natural language processing methods.

## Purpose

## Business Advantage

## Landscape

## Results
Part 1
1. The base URL is included in started code, along with the search string and query dates. Consult the NYT Article Search API documentation to help build "query_url" using the variables.

2. Create an empty list called "review_list" to store the reviews you retrieve from the API.

3. To bypass the Article Search API limiit of 10 per page (need to retrieve 200) create a "for" loop to loop through 20 pages (starting from page 0). Peform the following actions inside the loop:
  - Extend the "query_url" created in Step 1 to include the "page" parameter
  - Make a "GET" request to retrieve the page of results, and store the JSON data in a variable called "reviews."
  - Add a 12-second interval between queries to stay within API query limits. (NYT limits requests to 500 per day     and 5 per minute.
  - Write a try-except clause that performs the following actions:
    * "try": loop through the "reviews['respone']['docs 

## Recommendations
