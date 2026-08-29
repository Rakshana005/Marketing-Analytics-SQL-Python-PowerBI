# Marketing Analytics — SQL, Python & Power BI

## Project Overview

This project is an end-to-end marketing analytics solution developed using SQL Server, Python, and Power BI.

The project focuses on preparing marketing and customer data, analyzing customer journeys and engagement, enriching customer reviews through sentiment analysis, and presenting the results in an interactive Power BI dashboard.

The workflow demonstrates a practical data analytics process:

**Data Preparation → SQL Analysis → Python Sentiment Analysis → Power BI Data Modeling and Visualization**

---

## Business Problem

Marketing teams need to understand how customers interact with products and campaigns, where customers drop off during their journey, how customers engage with marketing content, and how customers perceive the products they purchase.

This project applies multiple analytical techniques to transform raw data into structured datasets and business intelligence.

### Key Areas Analyzed

* Customer information and geographical attributes
* Product information and price categories
* Customer journey data
* Customer reviews and ratings
* Review sentiment
* Marketing engagement data
* Data prepared for Power BI reporting

---

## Project Objectives

1. Clean and standardize marketing-related datasets using SQL.
2. Identify and handle duplicate customer journey records.
3. Handle missing customer journey duration values.
4. Transform and prepare customer review data.
5. Perform sentiment analysis on customer reviews using Python.
6. Enrich reviews with sentiment scores and sentiment categories.
7. Prepare analytical datasets for Power BI.
8. Build an interactive business intelligence dashboard.
9. Demonstrate an end-to-end data analyst workflow.

---

## Tools and Technologies

| Tool                 | Purpose                                          |
| -------------------- | ------------------------------------------------ |
| **SQL Server**       | Data cleaning, transformation, and analysis      |
| **Python**           | Customer review sentiment analysis               |
| **Pandas**           | Data manipulation and processing                 |
| **NLTK / VADER**     | Sentiment analysis                               |
| **Power BI**         | Data modeling and dashboard development          |
| **DAX**              | Calculated measures and date analysis            |
| **Jupyter Notebook** | Python analysis and documentation                |
| **GitHub**           | Project version control and portfolio management |

---

## Project Workflow

```text
Raw Marketing Data
        ↓
SQL Server
        ↓
Data Cleaning and Transformation
        ↓
Python Sentiment Analysis
        ↓
Enriched Analytical Data
        ↓
Power BI Data Model
        ↓
Interactive Dashboard
        ↓
Business Insights
```

---

# 1. SQL Data Preparation and Analysis

SQL Server was used to clean, transform, and prepare the marketing datasets.

### Customer Data

Customer information was enriched by joining customer data with geographical information to obtain attributes such as:

* Customer ID
* Customer name
* Email
* Gender
* Age
* Country
* City

### Product Data

Product data was prepared and products were categorized based on price:

* Low
* Medium
* High

This classification was implemented using SQL `CASE` logic.

### Customer Journey Data

Customer journey data was cleaned using SQL techniques including:

* Common Table Expressions (CTEs)
* `ROW_NUMBER()`
* Duplicate identification
* Duplicate removal
* `UPPER()`
* Missing-value handling
* Window functions
* Average duration calculation

Duplicate journey records were identified by partitioning records using customer, product, visit date, stage, and action.

Missing duration values were handled using an average duration calculated by visit date.

### Customer Reviews

Customer review text was cleaned by standardizing whitespace within the review text.

### Marketing Engagement Data

Engagement data was transformed by:

* Standardizing content types
* Separating views and clicks from combined fields
* Formatting engagement dates
* Filtering out newsletter records

---

# 2. Python Sentiment Analysis

Python was used to enrich the customer review dataset with sentiment information.

The analysis uses:

* **Pandas**
* **NLTK**
* **VADER SentimentIntensityAnalyzer**

### Sentiment Processing

The Python workflow:

1. Connects to SQL Server.
2. Retrieves customer review data.
3. Calculates a VADER compound sentiment score.
4. Combines the sentiment score with the customer rating.
5. Assigns a sentiment category.
6. Groups sentiment scores into sentiment buckets.
7. Exports the enriched dataset to a CSV file.

### Sentiment Categories

The project classifies reviews into categories such as:

* Positive
* Mixed Positive
* Mixed Negative
* Negative
* Neutral

### Output

The enriched review dataset contains fields including:

```text
ReviewID
CustomerID
ProductID
ReviewDate
Rating
ReviewText
SentimentScore
SentimentCategory
SentimentBucket
```

---

# 3. Power BI Dashboard

The cleaned and enriched datasets were used to build a Power BI dashboard for interactive analysis.

The Power BI component provides a business intelligence layer over the processed marketing data.

The dashboard can be used to explore areas such as:

* Customer-related metrics
* Product performance
* Customer journey
* Marketing engagement
* Customer reviews
* Sentiment analysis
* Time-based analysis

The Power BI project file is available in the `PowerBI` folder.

---

# Repository Structure

```text
Marketing-Analytics-SQL-Python-PowerBI/
│
├── SQL/
│   ├── dim_customers.sql
│   ├── dim_products.sql
│   ├── fact_customer_journey.sql
│   ├── fact_customer_reviews.sql
│   └── fact_engagement_data.sql
│
├── Python/
│   └── customer_reviews_enrichment.ipynb
│
├── Data/
│   └── customer_reviews_with_sentiment.csv
│
├── PowerBI/
│   └── MarketingSalesAnalysis.pbix
│
├── Database/
│   └── MarketingData.bak
│
└── README.md
```

---

# How to Use This Project

## SQL

1. Restore the database backup in SQL Server.
2. Open the SQL scripts from the `SQL` folder.
3. Execute the queries against the appropriate database.
4. Review the cleaned and transformed datasets.

## Python

1. Open the notebook:

```text
Python/customer_reviews_enrichment.ipynb
```

2. Install the required Python packages:

```bash
pip install pandas nltk pyodbc sqlalchemy
```

3. Configure the SQL Server connection for your local environment.
4. Run the notebook cells.
5. Generate the enriched customer review dataset.

## Power BI

1. Open:

```text
PowerBI/MarketingSalesAnalysis.pbix
```

2. Update the data source connections if required.
3. Refresh the dataset.
4. Explore the dashboard.

---

# Key Data Analyst Skills Demonstrated

### SQL

* Data cleaning
* Joins
* CTEs
* `CASE` statements
* Window functions
* `ROW_NUMBER()`
* Missing-value handling
* Data transformation

### Python

* Pandas
* Data extraction from SQL Server
* Data transformation
* VADER sentiment analysis
* Feature enrichment
* CSV export

### Power BI

* Data modeling
* Interactive dashboards
* DAX
* Data visualization
* Business reporting

---

# Key Takeaway

This project demonstrates how different analytics tools can be combined into a single workflow:

**SQL** prepares and transforms the data,
**Python** performs customer review sentiment enrichment, and
**Power BI** presents the processed data for business analysis.

---

# Author

**Rakshana Girirajan**

B.Tech Computer Science and Engineering — Data Science

Aspiring Data Analyst

---

