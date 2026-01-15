# Gender Analysis For 21st Century Movies

## Overview 

Project aims to examine the hypothesis of women’s underrepresentation in the
film industry through a quantitative analysis of movie metadata 
and dialogue-based measures of characters' importance in 21st-century cinema. 

The analysis focuses on:
- differences in gender representation across movie subsets originating from
  various selection criteria
- the visibility of female characters through characters number, dialogue volume and word count
- differences in representation across time and genres
- the relationship between director gender and on-screen gender balance
- sentiment expressed in dialogues spoken by male and female characters

By translating narrative and structural data into measurable indicators,
the project aims to complement existing qualitative research with empirical
evidence.

## Data Sources 

### Movie Selection
Movies were selected from multiple publicly available lists:
- popular and high-grossing films
- critically acclaimed titles
- movies listed as feminist or female-centered

Only movies released in the 21st century were considered.

### Screenplay
- Movie scripts were collected from various publicly available online sources providing open-access screenplay data
- Scripts were included for analysis if available in PDF or TXT format
- Due to differences in file formats and original creators, scripts vary in layout, structure, and formatting

### Metadata
- Movie and cast metadata retrieved via TMDB API
- Key metadata variables included:
  - movie release year, genres, director, and plot description
  - cast list with gender and age
  - character names (to link with screenplay data)
  - character gender (when available)
 
## Data Collection & Preprocessing

### Screenplay Processing
- PDF scripts were parsed using text extraction
- Elements were identified based on:
  - text indentation
  - capitalization patterns
  - script layout structure
- Character names were extracted
- Dialogues were assigned to characters

### Data Integration
- Screenplay data was matched with TMDB metadata
- Characters were linked to movies and cast information
- The final data was organized into two datasets:
  - a movie-level dataset containing film metadata
  - a character-level dataset containing dialogue and character information

## Sentiment Analysis
- Sentiment analysis was performed on individual dialogue lines
- Model used:
  - `cardiffnlp/twitter-roberta-base-sentiment-latest`
- For each dialogue:
  - sentiment label (positive / neutral / negative)
  - model confidence score was stored

In addition, emotion classification was explored using multiple models with
emotion categories including *Anger, Fear, Joy, Love, Sadness,* and *Surprise*.
However, the results across models were inconsistent and visibly unreliable. 
As a result, emotion-level analysis was excluded from the final report.

## Analysis
The analysis includes:
- director gender distribution
- number of main characters, dialogue volume, and word count by gender
- yearly gender shares of characters
- genre-based gender distribution
- gender distribution of characters by actors’ age
- sentiment distribution across genders

## Key Findings (Summary)
- Male characters dominate dialogue volume across most years
- Female dialogue share increases slightly over time but remains lower overall
- Genre moderately influences gender representation
- Sentiment distributions show subtle gender differences



