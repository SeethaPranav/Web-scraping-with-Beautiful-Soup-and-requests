# Web-scraping-with-Beautiful-Soup-and-requests
Web scraping project using Beautiful Soup and Requests to extract and parse data from websites.

As part of a 75-day data analysis challenge, this work on Jupyter Notebook covers web scraping using Beautiful soups and requests.

Import libraries
import requests from bs4 import BeautifulSoup import csv

URL of the movies data page
url = "https://scrapethissite.com/pages/simple/"

Send a GET request to fetch the HTML content
response = requests.get(url)

Check if the request was successful
if response.status_code == 200: print("Page fetched successfully!") else: print(f"Failed to fetch the page. Status code: {response.status_code}")

Parse the page content using BeautifulSoup
soup = BeautifulSoup(response.text, 'html.parser')

Find all movie entries on the page
movies = soup.find_all('div', class_='movie')

Initialize a list to store movie data
movies_data = []

Loop through each movie entry and extract details
for movie in movies: # Extract the movie title title = movie.find('h2', class_='movie-title').text.strip()

