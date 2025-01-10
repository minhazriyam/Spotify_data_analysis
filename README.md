# Spotify_data_analysis
 Data analysis project exploring Spotify tracks, engagement, and insights using SQL queries.
![Spotify vs YouTube Streams](/spotify.jpeg)



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

```
## Project Objectives
- Identify the most engaging tracks and artists.
- Analyze engagement trends across platforms.
- Understand how audio features impact track performance.
- Explore licensing and official video effects on engagement.
- Derive actionable insights for platform-specific optimization.

---

## Key Insights and Queries

### 1. Which tracks or artists have the highest engagement (likes/comments/views)?
```sql
SELECT track, STRING_AGG(artist, ', ') AS all_artists, SUM(likes + comments + views) AS total_engagement
FROM spotify
GROUP BY track
ORDER BY total_engagement DESC
LIMIT 3;
```

### 2. How does engagement vary across different channels or platforms?

```sql
SELECT channel, AVG(likes + comments + views) AS avg_engagement
FROM spotify
GROUP BY channel
ORDER BY avg_engagement DESC
LIMIT 3;
```

### 2. How does engagement vary across different channels or platforms?

```sql
SELECT channel, AVG(likes + comments + views) AS avg_engagement
FROM spotify
GROUP BY channel
ORDER BY avg_engagement DESC
LIMIT 3;
```

### 3. What is the optimal track duration for maximizing streams and engagement?


```sql
SELECT duration_min, AVG(stream) AS avg_streams, AVG(likes + comments) AS avg_engagement
FROM spotify
GROUP BY duration_min
ORDER BY avg_streams DESC
LIMIT 10;
```


### 4. Are licensed tracks associated with higher streams or engagement compared to non-licensed ones?


```sql
SELECT licensed, AVG(stream) AS avg_streams, AVG(likes + comments) AS avg_engagement
FROM spotify
GROUP BY licensed
ORDER BY avg_streams DESC;

```

### 5. Retrieve the track names streamed on Spotify more than YouTube.

```sql
SELECT track, artist, stream AS spotify_streams, views AS youtube_views
FROM spotify
WHERE stream > views;
```



```sql
SELECT duration_min, AVG(stream) AS avg_streams, AVG(likes + comments) AS avg_engagement
FROM spotify
GROUP BY duration_min
ORDER BY avg_streams DESC
LIMIT 10;
```



```sql
SELECT duration_min, AVG(stream) AS avg_streams, AVG(likes + comments) AS avg_engagement
FROM spotify
GROUP BY duration_min
ORDER BY avg_streams DESC
LIMIT 10;
```

