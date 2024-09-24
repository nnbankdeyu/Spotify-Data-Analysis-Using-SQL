# Spotify-Data-Analysis-using-SQL
## Overview
This project aims to explore and analyze a dataset of Spotify tracks using SQL. By querying and manipulating the data, we gain insights into the relationships between various attributes of songs, such as their popularity, danceability, energy, and views. Additionally, we focus on identifying trends and answering business-driven questions to better understand what makes certain tracks or artists more successful than others on the platform.
```sql
-- CREATE DATABASE 'SPOTIFY_DB'
DROP TABLE IF EXISTS spotify;
CREATE TABLE spotify (
    artist VARCHAR(255),
    track VARCHAR(255),
    album VARCHAR(255),
    album_type VARCHAR(50),
    danceability FLOAT,
    energy FLOAT,
    loudness FLOAT,
    speechiness FLOAT,
    acousticness FLOAT,
    instrumentalness FLOAT,
    liveness FLOAT,
    valence FLOAT,
    tempo FLOAT,
    duration_min FLOAT,
    title VARCHAR(255),
    channel VARCHAR(255),
    views FLOAT,
    likes BIGINT,
    comments BIGINT,
    licensed BOOLEAN,
    official_video BOOLEAN,
    stream BIGINT,
    energy_liveness FLOAT,
    most_played_on VARCHAR(50)
);
```
## About the Dataset
The dataset consists of various attributes of tracks, albums, and artists from Spotify, including:

- Artist Name: The name of the performer.
- Track Title: The name of the song.
- Album Name: The title of the album the track belongs to.
- Attributes: Features such as danceability, energy, loudness, acousticness, etc.
- Popularity Metrics: views, likes, comments, streams.
- Additional Features: Whether the track is a licensed song or an official video, the platform with the most streams, and more.

## SQL Table Structure:
The main table spotify includes the following columns:

- **`artist`, track, album, album_type**
- Audio features like **danceability, energy, loudness, speechiness, acousticness, liveness, valence, tempo**
- Popularity measures: **views, likes, comments, stream**
- Flags: **licensed, official_video**
- Derived attributes like **energy_liveness, most_played_on**

## Steps Involved
1. Level 1: Basic SQL Queries
At this stage, I started with straightforward queries to extract key insights from the dataset. The focus is on filtering and selecting data, with some basic aggregation.

Techniques Used:

SELECT statements to retrieve data.
Filtering with WHERE.
Aggregation functions like COUNT, SUM, AVG to generate simple insights.

2. Level 2: Intermediate SQL Queries
Here, the queries become more complex with the use of JOIN, GROUP BY, and subqueries. The goal is to explore relationships between multiple attributes.

Techniques Used:

JOIN statements to combine data from multiple sources.
Subqueries to perform nested calculations.
Conditional filtering using CASE WHEN.

3. Level 3: Advanced SQL Queries
This phase focuses on applying window functions, CTE (Common Table Expressions), and performance optimization techniques to gain deep insights into the dataset.

Techniques Used:

Window Functions (ROW_NUMBER(), RANK(), OVER).
CTEs to break down complex queries into more readable parts.
Performance tuning via indexing and query optimization to reduce runtime and increase efficiency on large datasets.

## Optimization Techniques
To handle large datasets efficiently, certain optimization techniques were employed:

Indexing: Indexed columns frequently used in filtering conditions, like artist, track, and stream.
Reducing Redundancy: Used CTEs and subqueries to avoid repeated computations and improve readability.
Query Tuning: Rewrote certain queries using JOIN instead of subqueries where applicable to minimize execution time.
Optimization Example: For the query retrieving the top 5 most-viewed tracks per artist, using a CTE with window functions like ROW_NUMBER() was key to keeping the query performant without needing to run multiple subqueries.

# Conclusion
This project illustrates how SQL can be leveraged at different levels of complexity to analyze large-scale datasets like Spotify’s track data. Starting from basic data exploration, we advanced to more complex queries using window functions, CTEs, and optimizations for efficient query execution. The analysis uncovers interesting patterns in track popularity, artist performance, and the relationship between song attributes.
