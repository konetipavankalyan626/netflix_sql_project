# Netflix Movies and TV Shows Data Analysis using SQL

![Netflix Logo](https://github.com/konetipavankalyan626/netflix_sql_project/blob/main/netflix.jpg)

## Overview

The Netflix Data Analysis project aims to explore the Netflix Titles dataset using SQL queries to uncover trends and patterns in content distribution. The dataset includes details about movies and TV shows such as title, director, cast, country, release year, rating, duration, and genre.

By analyzing this dataset, we gain insights into content diversity, regional representation, rating distribution, and release trends on Netflix.

## Objectives

• Compare the number of Movies vs TV Shows available on Netflix.

• Analyze the distribution of content ratings.

• Identify top countries, genres, directors, and actors with the most contributions.

• Examine regional representation by comparing countries like USA and India.

## Dataset

The data for this project is sourced from the Kaggle dataset:

• Dataset Link: https://github.com/konetipavankalyan626/netflix_sql_project.git

## Schema

```sql
DROP TABLE IF EXISTS netflix;
CREATE TABLE netflix
(
	show_id	VARCHAR(5),
	type    VARCHAR(10),
	title	VARCHAR(250),
	director VARCHAR(550),
	casts	VARCHAR(1050),
	country	VARCHAR(550),
	date_added	VARCHAR(55),
	release_year	INT,
	rating	VARCHAR(15),
	duration	VARCHAR(15),
	listed_in	VARCHAR(250),
	description VARCHAR(550)
);
SELECT * FROM netflix;
```
## Business Problems and Solutions

## 1. How many Movies and TV Shows are there
```sql
SELECT type, COUNT(*) AS total
FROM netflix
GROUP BY type;
```

## 2. What are the most common ratings for Movies and TV Shows
```sql
SELECT type, rating, COUNT(*) AS total
FROM netflix 
GROUP BY type, rating
ORDER BY total DESC;
```

## 3. Which country has the highest number of Netflix titles
```sql
SELECT country, COUNT(*) AS total
FROM netflix 
WHERE country IS NOT NULL
GROUP BY country
ORDER BY total DESC
LIMIT 10;
```

## 4. Which year had the highest number of releases on Netflix 
```sql
SELECT release_year, COUNT(*) AS total
FROM netflix
GROUP BY release_year
ORDER BY total DESC
LIMIT 1;
```

## 5. Find the longest movie on Netflix
```sql
SELECT title, duration
FROM netflix
WHERE type = 'Movie'
LIMIT 1;
```

## 6. How many TV Shows have more than 5 season
```sql
SELECT COUNT(*) AS total_tvshows
FROM netflix
WHERE type = 'TV Show'
```

## 7. Who are the top 10 directors with the most Netflix titles
```sql
SELECT director, COUNT(*) AS total
FROM netflix
WHERE director IS NOT NULL
GROUP BY director
ORDER BY total DESC
LIMIT 10;
```

## 8. List all Movies released in 2020
```sql
SELECT title
FROM netflix
WHERE type = 'Movie' AND release_year = 2020;
```

## 9. Find all Indian Movies and TV Shows
```sql
SELECT title, type
FROM netflix
WHERE country LIKE '%India%';
```

## 10. Which genre has the most titles
```sql
SELECT listed_in, COUNT(*) AS total
FROM netflix
GROUP BY listed_in
ORDER BY total DESC
LIMIT 1;
```

## 11. Who are the top 10 most frequent actors
```sql
SELECT casts, COUNT(*) AS total
FROM netflix
WHERE casts IS NOT NULL
GROUP BY casts
ORDER BY total DESC
LIMIT 10;
```

## 12. List the top 10 countries with the most content on Netflix
```sql
SELECT country, COUNT(*) AS total
FROM netflix
WHERE country IS NOT NULL
GROUP BY country
ORDER BY total DESC
LIMIT 10;
```

## 13. What is the average number of Movies released per year
```sql
SELECT ROUND(AVG(movies_per_year), 2) AS avg_movies_per_year
FROM (
    SELECT release_year, COUNT(*) AS movies_per_year
    FROM netflix
    WHERE type = 'Movie'
    GROUP BY release_year
) sub;
```

## 14. What are the top 5 genres in India
```sql
SELECT listed_in, COUNT(*) AS total
FROM netflix
WHERE country LIKE '%India%'
GROUP BY listed_in
ORDER BY total DESC
LIMIT 5;
```

## 15. Find all content where “Salman Khan” appears
```sql
SELECT title, type
FROM netflix
WHERE casts LIKE '%Salman Khan%';
```
## Findings and Conclusion

#### • Content Distribution: Netflix hosts a diverse range of movies and TV shows, but movies dominate the catalog. TV shows have seen rapid growth in recent years.

#### • Audience Ratings: The most frequent rating is TV-MA, followed by TV-14. This shows Netflix primarily caters to adult and mature audiences.

#### • Geographic Presence: The USA has the largest number of titles, followed by India, UK, and Canada, highlighting Netflix’s global reach and India’s importance as a growth market.

#### This findings present a clear picture of Netflix’s growth, audience targeting, and global reach, making it a useful reference point for shaping future content strategies and business decisions

# Author - Pavan Kalyan Koneti
This project is part of my portfolio, showcasing the SQL skills essential for data analyst roles. If you have any questions, feedback, or would like to collaborate, feel free to get in touch!

-Linkedin:https://www.linkedin.com/in/pavankalyan585/
-Gmail:konetipavankalyan225@gmail.com



















	
	
	
