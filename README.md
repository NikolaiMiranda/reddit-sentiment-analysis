# Reddit Sentiment Analysis Dashboard

This project performs sentiment analysis on Reddit posts and comments using Python and the VADER sentiment analysis tool. The output is then visualized through an interactive Tableau dashboard. The goal is to provide an intuitive way to explore public sentiment and engagement around any subreddit over a custom time period.

## Project Overview

With this tool, you can:

- Scrape all **posts** and **comments** from a specified subreddit within a user-defined date range  
- Perform sentiment analysis using the **VADER lexicon**  
- Classify each piece of content as **Positive**, **Neutral**, or **Negative**  
- Export results to a clean **CSV file**  
- Explore key sentiment and engagement trends in a **Tableau dashboard**  

## Tech Stack

- Python (data scraping, cleaning, and sentiment analysis)  
- `asyncpraw` (asynchronous Reddit API access)  
- `VADER` via NLTK (for sentiment scoring)  
- `pandas` (data manipulation)  
- Google Colab (notebook environment)  
- Tableau (data visualization)  

## Features

### Custom Subreddit & Date Range Input

Users are prompted to input:
- A subreddit name (e.g., `biltrewards`)
- A start and end date (e.g., `07-20-2025` to `07-30-2025`)

### Data Collected

For each post and comment, the following fields are collected:

- Title and body text  
- Score (upvotes/downvotes)  
- Number of comments  
- Created timestamp  
- Author  
- Parent ID  
- URL  

### Sentiment Analysis

Sentiment is calculated using NLTK’s VADER `SentimentIntensityAnalyzer`, which outputs:

- `neg`: Negative score  
- `neu`: Neutral score  
- `pos`: Positive score  
- `compound`: Aggregated sentiment score  

Based on the compound score:

- `Positive` (>= 0.05)  
- `Neutral` (between -0.05 and 0.05)  
- `Negative` (<= -0.05)  

### CSV Export

The processed data is exported to a `.csv` file containing all metadata and sentiment columns. This file can be used for further analysis or dashboarding.

### Tableau Dashboard

The exported CSV is used to power a Tableau dashboard featuring:

- Filters for sentiment, date range, and content type  
- Word clouds of common terms by sentiment  
- Time series views of engagement and sentiment trends  
- Drill-down into individual posts and comments  
