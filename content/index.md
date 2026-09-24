# Database Design: Destination Recommender

[< Back Home](/..)

###### [See the code](https://github.com/chancecarr/destination-recommender)

### Explanation

This project served two purposes: first, to showcase what I learned in my Database Modeling Concepts class; second, to experiment with letting AI generate a frontend for me. There were a couple of complex pieces that I worked through:

#### Database Prep

1. I found and cleaned a database of all of the sites in the U.S. under the care of the federal government as listed by the National Parks Service. 
2. I designed my own database which included this cleaned information as well as an image of each site scraped from Google Maps and geolocation data provided by the Google Maps API. 
3. I also wrote a script that queried Chat-GPT 4-o mini and had it write a short description of each site, and I included those descriptions in my dataset. 
4. As a final piece of data, I used SentenceTransformer to generate a vector embedding of the site description for later use.

#### Backend Utility

1. For the core utility of the project, I created a vector-based natural language search engine. This meant that a user could type in a search for any sort of place they wanted to visit, my system would use the same SentenceTransformer model I used to encode my sites database to encode their query, and then it would find the most similar destination to what they requested based upon the cosine similarity of the embedded vectors and return it. 
2. For fun, I gave users the ability to submit their own destinations to my database. Submitted sites would get their own picture scraped from Google Maps, geolocation data, a new description written by Chat-GPT 4-o mini, and vector embedding. These sites would be included in the database in future searches.

Finally, I utilized Cursor to create a simple frontend for my sites list and search engine. This project was a lot of fun!

(**See my final dataset [here](/documents/destinations-db.csv).** Note that the last few rows were user-submitted!)