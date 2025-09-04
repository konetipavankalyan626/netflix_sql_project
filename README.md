# Netflix Movies and TV Shows Data Analysis using SQL

![Netflix Logo](https://github.com/konetipavankalyan626/netflix_sql_project/blob/main/netflix.jpg)

## Overview

The Netflix Data Analysis project aims to explore the Netflix Titles dataset using SQL queries to uncover trends and patterns in content distribution. The dataset includes details about movies and TV shows such as title, director, cast, country, release year, rating, duration, and genre.

By analyzing this dataset, we gain insights into content diversity, regional representation, rating distribution, and release trends on Netflix.

# Objectives

• Compare the number of Movies vs TV Shows available on Netflix.

• Analyze the distribution of content ratings.

• Identify top countries, genres, directors, and actors with the most contributions.

• Examine regional representation by comparing countries like USA and India.

# Dataset

The data for this project is sourced from the Kaggle dataset:

• Dataset Link: https://github.com/konetipavankalyan626/netflix_sql_project.git

# Schema

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



	
	
	
