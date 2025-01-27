# Bonk-Analysis-in-Knime
Analysis of Bonk meme coin using Knime
# BONK Transactions Analysis Workflow

This repository contains a KNIME workflow designed to analyze **BONK** cryptocurrency transactions. The workflow aggregates and visualizes transaction data to identify peak trading hours and high-value trades for a specific date, **November 28**.

## Workflow Overview

The KNIME workflow connects to multiple MongoDB clusters, extracts transaction data, and performs the following operations:

### 1. Data Extraction:
- **MongoDB Connector**: Connects to MongoDB clusters.
- **MongoDB Reader**: Reads the transaction data stored in MongoDB.
- **JSON to Table**: Converts the JSON data into a structured table format for easier analysis.

### 2. Data Preparation:
- **Joiner and Column Filter**: Merges datasets from multiple clusters and filters relevant columns such as:
  - `transaction_id`
  - `block_month`
  - `block_time`
  - `amount_usd`
  
### 3. Data Aggregation:
- **Grouping by Hour**: Groups transactions by hour (from `block_time`) and sums the `amount_usd` for each hour.
- **Filtering High-Value Transactions**: Identifies and isolates high-value trades where `amount_usd > 50`.

### 4. Data Visualization:
- **Line Plot**: Displays trading volumes by hour on November 28.
- **Bar Chart**: Highlights the top 5 largest transactions by USD value on November 28.
- **Pie Chart**: Shows the contribution of each high-value trade to the overall trades on November 28.

## Key Insights

The analysis will provide the following insights:

- **Peak Trading Hours**: Identify the hours with the highest transaction volumes on November 28.
- **High-Value Trades**: Analyze and rank the top transactions by USD value.

## Prerequisites

To use this workflow, ensure you have the following prerequisites:

- **KNIME Analytics Platform** installed. You can download it from [here](https://www.knime.com/downloads).
- **MongoDB Access**: Ensure you have access to the MongoDB clusters containing BONK transaction data. You will need MongoDB credentials to configure the MongoDB Connector nodes.

## How to Use

Follow these steps to run the analysis:

- Clone this repository
- Open the workflow file (Bonk_Project3_Team9.knwf) in KNIME Analytics Platform.
- Configure the MongoDB Connector nodes with your MongoDB credentials.
- Execute the workflow to generate insights and visualizations.

## Results
The workflow generates the following output visualizations:

- Trading Activity Trends: Visualizes trading activity patterns throughout the day, showing how trading volume varies.
- Largest Trades by Value: Identifies and visualizes the largest trades, categorized by trade value.
- Proportional Contributions of High-Value Trades: Shows the proportional contribution of trades with the highest values to the overall trading activity.
- These visualizations provide actionable insights into BONK trading patterns, helping to analyze the market behavior and make informed decisions.
