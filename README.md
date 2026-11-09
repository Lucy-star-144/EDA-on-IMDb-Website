## Business Problem

Streaming platforms and content producers need to understand:

- Which movie genres are most popular and receive the highest audience ratings.
- How factors such as runtime, release year, Metascore (critic ratings), and audience votes relate to audience ratings.
- Which content certifications (PG, PG-13, TV-MA, etc.) are associated with higher audience engagement.
- What characteristics distinguish highly rated titles from lower-rated ones.
- How audience ratings and critic scores vary across different genres.

## Domain: Entertainment / Media Analytics

- The entertainment industry generates large volumes of data related to movies and TV shows, including audience ratings, votes, genres, runtime, release year, content certifications, and critic scores.
- Analyzing this data helps streaming platforms, production houses, and content creators understand audience preferences, evaluate content performance, and identify trends.

## Use Case

A streaming platform or content provider wants to analyze movie and TV show data to understand:

- Which genres are most popular among viewers.
- What factors are associated with higher IMDb ratings.
- Whether critic scores (Metascore) align with audience ratings.
- Which content certifications (PG, PG-13, TV-MA, etc.) are associated with greater audience engagement.
- How runtime, genre, and release year relate to audience ratings and popularity.

## Project Objectives

- Analyze IMDb ratings and audience engagement patterns.
- Identify the most popular and highest-rated genres.
- Explore relationships between audience ratings, votes, runtime, release year, and Metascore.
- Compare audience ratings and engagement across different content certification categories.
- Identify patterns and generate insights to better understand audience preferences and content performance.

  ## Data Source

- **Website:** IMDb
- **Data Collected:** Movie and TV show information
- **Extraction Method:** Web scraping using Python
- **Dataset Size:** Approximately 500 movies and TV shows.

  ## Tools & Libraries Used

- **Python:** For data extraction, cleaning, and analysis.
- **Requests:** To send HTTP requests and retrieve webpage content.
- **BeautifulSoup:** To parse HTML and extract relevant information through web scraping.
- **Pandas:** For data manipulation, cleaning, and exploratory data analysis.

  ## Dataset Features

The dataset contains the following attributes:

- Title
- Release Year
- Genre
- IMDb Rating
- Runtime
- Certificate
- Metascore
- Number of Votes
  
## Project Workflow

The project followed the following steps:

1. **IMDb Website:** Identified the required movie and TV show information.
2. **Send HTTP Request:** Used the Requests library to send HTTP requests to IMDb.
3. **Retrieve HTML Content:** Retrieved the webpage's HTML content.
4. **Parse HTML:** Used BeautifulSoup to parse the HTML structure.
5. **Extract Required Fields:** Extracted relevant information such as title, release year, genre, ratings, runtime, certificate, Metascore, and votes.
6. **Store Data:** Organized the extracted information into a Pandas DataFrame.
7. **Data Cleaning & Preprocessing:** Cleaned missing values, duplicates, data types, and inconsistent formats.
8. **Exploratory Data Analysis:** Analyzed the cleaned dataset to identify patterns, relationships, and insights.

## Data Cleaning & Preprocessing

The following data cleaning and preprocessing steps were performed:

- Removed duplicate records.
- Handled missing values.
- Converted columns to appropriate data types.
- Extracted numerical values from text fields.
- Standardized Genre and Certificate fields.
- Created derived columns such as `Votes_K` for better analysis.

  ## Challenges Encountered

During web scraping and data preprocessing, the following challenges were encountered:

- **Missing Metascore Values:** Some titles did not have critic scores available.
- **Missing Runtime Values:** Runtime information was unavailable for certain titles.
- **Multiple Genres:** Some titles were associated with multiple genres stored together in a single field.
- **Inconsistent Formats:** Vote counts and ratings were represented in different formats, requiring data conversion and standardization before analysis.

  ## Data Manipulation & Feature Engineering

- Extracted and cleaned Genre information.
- Split multiple genres and used the `explode()` function to enable genre-level analysis.
- Converted vote counts into numerical format and created a derived feature `Votes_K`.
- Used grouping, pivot tables, and cross-tabulations for comparative analysis.
- Grouped data by Genre, Certificate, and Year to identify patterns and trends.

## Exploratory Data Analysis (EDA)

### Univariate Analysis

Analyzed individual variables to understand their distributions and characteristics.

**Numerical Variables:**
- Year
- IMDb Rating
- Runtime
- Metascore
- Votes_K

**Categorical Variables:**
- Genre
- Certificate

**Techniques Used:**
- Descriptive Statistics
- Histograms and KDE Plots
- Boxplots
- Frequency Counts and Countplots
- Percentage Distribution Analysis

### Bivariate Analysis

Explored relationships between pairs of variables to identify patterns, trends, and associations.

**Numerical vs Numerical:**
- Correlation Analysis (Pearson, Spearman, and Kendall)
- Scatter Plots
- Line Plots
- Pairplots

**Examples:**
- Rating vs Votes_K
- Runtime vs Rating
- Metascore vs Votes_K

**Categorical vs Numerical:**
- GroupBy Analysis
- Boxplots
- Violin Plots

**Examples:**
- Genre vs Rating
- Genre vs Runtime
- Certificate vs Rating

**Categorical vs Categorical:**
- Cross-tabulations
- Heatmaps
- Stacked Bar Charts
- Clustermaps

**Examples:**
- Genre vs Certificate
- Genre vs Year
- Certificate vs Year

### Key Business Insights
Which genres receive the highest IMDb ratings?
- Overall, most genres receive favorable ratings, with median ratings generally above 7.0.
[!GenrevsRating][ScreenShot/GenrevsRating.png]

Which genres attract the highest audience engagement (Votes)?
- Audience engagement varies across genres, with Fantasy, Sci-fi, Adventure , and Animation generally attracting higher vote counts.
- While most genres contain a few exceptionally popular titles, Comedy, Drama, and Thriller tend to receive lower audience engagement overall.The presence of several extreme outliers suggests that a small number of highly popular titles significantly influence audience participation within certain genres.

Is there a relationship between IMDb ratings and audience votes? 
- The scatter plot indicates a moderate positive association between IMDb ratings and audience engagement.
- Titles with higher ratings tend to receive more votes, suggesting that well-received content often attracts greater 
audience attention and participation.

Which certification categories (PG, PG-13, TV-MA, etc.) perform best in terms of ratings and popularity? 
- The analysis suggests a positive relationship between IMDb ratings and audience engagement. 
- Titles with higher ratings generally attract more audience votes, while certificate categories 
such as TV-MA contain several highly rated and highly engaged titles.

How do runtime and release year influence ratings? Do critic scores (Metascore) align with audience ratings?
- Spearman correlations are generally stronger than Pearson correlations, indicating that many relationships in the dataset are monotonic in nature and not strictly linear


## Conclusion

The analysis identified differences in audience ratings, engagement, and critic scores across genres and certification categories.

- Animation, Fantasy, and Adventure generally received higher audience ratings, while Comedy and Thriller showed comparatively lower ratings.
- A positive relationship was observed between IMDb ratings and audience votes, indicating that highly rated titles tended to attract greater audience engagement.
- Runtime showed a moderate positive association with ratings, with longer titles generally receiving better audience ratings.
- Metascore and IMDb ratings exhibited a positive relationship, suggesting some alignment between critic and audience opinions.
- Genre–Certificate combinations revealed variations in both ratings and popularity, highlighting the importance of content type and target audience.
- The dataset was heavily concentrated in recent years, so findings related to release year should be interpreted with caution.

Overall, the project demonstrated how exploratory data analysis can help identify patterns in audience preferences and content performance.

## Experience Gained

Through this project, I gained practical experience in:

- Collecting real-world data using web scraping techniques.
- Working with Python libraries such as Requests, BeautifulSoup, Pandas, Matplotlib, and Seaborn.
- Performing data cleaning, preprocessing, and feature engineering.
- Applying statistical techniques and visualizations to explore data patterns and relationships.
- Deriving meaningful insights from raw data through exploratory data analysis.
- Understanding the end-to-end data analytics workflow, from data collection to insight generation.
