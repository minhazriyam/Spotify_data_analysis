# Spotify_data_analysis
 Data analysis project exploring Spotify tracks, engagement, and insights using SQL queries.



# Spotify Data Analysis Project 🎵

This project analyzes Spotify data using SQL to extract insights about engagement, track performance, and platform optimization strategies. The analysis includes queries on track popularity, artist performance, and various audio features like danceability and valence.

## Table of Contents
- [Introduction](#introduction)
- [Dataset Overview](#dataset-overview)
- [Project Objectives](#project-objectives)
- [Key Insights and Queries](#key-insights-and-queries)
- [How to Run the Queries](#how-to-run-the-queries)
- [Results and Visualizations](#results-and-visualizations)
- [Technologies Used](#technologies-used)
- [Contributing](#contributing)
- [License](#license)

---

## Introduction

Spotify data is a goldmine for understanding audience behavior, track performance, and engagement metrics. In this project, we leverage SQL to analyze various aspects of tracks, albums, and artists, answering key business and professional questions.

---

## Dataset Overview

The dataset includes:
- Artist and track metadata
- Audio features (danceability, energy, valence, etc.)
- Engagement metrics (likes, comments, views, streams)
- Licensing and platform information (e.g., `official_video`, `licensed`)

### Database Schema
```sql
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
