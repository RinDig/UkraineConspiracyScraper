# Reddit Ukraine Funding Sentiment Analysis

## Overview
This project analyzes discussion sentiment and network dynamics around Ukraine funding posts on Reddit's r/conspiracy subreddit. Using API integration, natural language processing, and network analysis, the tool collects posts related to Ukraine funding, analyzes sentiment using GPT-4, and visualizes user interaction networks through Gephi.

![image](https://github.com/user-attachments/assets/123ad122-e7ce-46b5-870b-a5eedd3ee855)

## Methodology

### Data Collection
- Used PRAW (Python Reddit API Wrapper) to access Reddit's API
- Searched r/conspiracy for posts containing Ukraine funding-related keywords
- Collected 3 posts per year from 2022-2024 (9 posts total)
- Extracted all comments and user interactions from these posts

### Sentiment Analysis
- Utilized OpenAI's GPT-4 to classify post and comment sentiment
- Classification categories:
  - Strongly Pro-Ukraine
  - Mildly Pro-Ukraine
  - Neutral
  - Mildly Anti-Ukraine
  - Strongly Anti-Ukraine
- Processed text in batches to optimize API usage

### Network Analysis
- Built user-interaction networks where:
  - Nodes represent users
  - Edges represent interactions (replies)
  - Node size correlates with user influence
- Visualized networks using Gephi
- Analyzed community structures and influencer patterns

## Key Findings

The analysis collected 9 posts (3 from each year) with 764 comments from 682 unique users.

### Sentiment Distribution
- Neutral: 438 users (64.2%)
- Mildly Anti-Ukraine: 86 users (12.6%)
- Strongly Pro-Ukraine: 65 users (9.5%)
- Mildly Pro-Ukraine: 54 users (7.9%)
- Strongly Anti-Ukraine: 39 users (5.7%)

### Network Analysis by Year

#### 2022
![image](https://github.com/user-attachments/assets/85c8cfce-fd24-4bcf-b20e-b74556ba4735)


- Three primary authors: FutureisAsian (A), Sabremesh (B), and Far-Somewhere-1366 (C)
- Author A shows highest influence (largest node, most connections)
- Author B functions as the main intermediary and bridge between communities A and C
- Author C has the least engagement but remains connected to the network
- Note: Olliethegoldsmith appears relatively isolated from the main network

#### 2023
![image](https://github.com/user-attachments/assets/1d54e665-95db-45a7-861a-4dc903e09268)

- Three connected authors: jdhmdo (D), Fuzzy-Arm-6016 (E), and Ok-Imagination-2308 (F)
- Author E serves as the central bridge between potential distinct communities
- Authors D and F demonstrate higher engagement rates
- Interactions show greater distribution compared to 2022

#### 2024
![image](https://github.com/user-attachments/assets/cc99ea2c-da91-4d9f-adea-2c82d0e8fe1d)


- All posts authored by Reasonable_Mess_3327 (X)
- Author X shows significant dominance in the network
- Multiple small clusters surround the central node
- Suggests either more engaging content or expanding discussion reach

## Visualization in Gephi

This project used Gephi for network visualization. Network data was exported as:
- ukraine_funding_nodes.csv - Contains user data and sentiment classifications
- ukraine_funding_edges.csv - Contains interaction data between users

![image](https://github.com/user-attachments/assets/4ae21ead-6c30-4bf1-bd43-12241c98822e)


### How to Create Similar Visualizations

1. Import the node and edge CSV files into Gephi
2. Apply the ForceAtlas2 layout algorithm
3. Size nodes based on degree (connection count)
4. Color nodes based on sentiment classification
5. Apply community detection algorithm
6. Adjust visual parameters for clarity

## Code Structure

- `search_ukraine_financial_posts()` - Finds relevant posts on r/conspiracy
- `extract_post_data()` - Pulls metadata from posts
- `get_all_comments()` - Retrieves comments from posts
- `classify_sentiment()` - Uses GPT-4 to analyze sentiment
- `aggregate_user_sentiment()` - Combines data at user level
- `create_network_data()` - Prepares network for visualization
- `analyze_ukraine_funding_network()` - Main function orchestrating the analysis

## Future Improvements

- Implement sentiment analysis error handling
- Add temporal analysis of sentiment shifts
- Expand to additional subreddits for comparison
- Develop interactive visualization dashboard
- Improve classification with fine-tuned models

## Requirements

- Python 3.8+
- PRAW
- OpenAI API access
- pandas
- Gephi (for visualization)

## Setup Instructions

1. Clone this repository
2. Install required packages: `pip install -r requirements.txt`
3. Add your API credentials to the configuration
4. Run the main analysis script
5. Import the resulting CSV files into Gephi

## License

[Insert your license information here]

## Acknowledgments

[Insert your acknowledgments here]
