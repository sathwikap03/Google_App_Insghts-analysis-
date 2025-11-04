#  Google Play Store Data Analysis – Power BI Dashboard  


##  Overview  
This Power BI project explores **Google Play Store app data** to uncover trends in **ratings, installs, pricing, and user engagement**.  
The goal is to identify the key factors influencing **app popularity** and **user satisfaction**, helping businesses make data-driven marketing and development decisions.  

 **Tool Used:** Microsoft Power BI   

##  Dataset Description  
The dataset contains details about Android apps available on the Google Play Store.  

| Column | Description |
|--------|-------------|
| **App** | Name of the application |
| **Category** | Broad app category (e.g., Tools, Games, Education) |
| **Genres** | Specific app genre |
| **Rating** | Average user rating |
| **Reviews** | Number of user reviews |
| **Installs** | Total number of app installs |
| **Price** | App price (0 for free apps) |
| **Size** | App size in MB |
| **Type** | Free or Paid |
| **Content Rating** | Age appropriateness |
| **Last Updated** | Date of the last update |


## 📈 Dashboard Design  

Two dashboards were developed to present insights visually.  

###  **Dashboard 1 – MARKET_VIEW**

**Purpose:** Explore genre-wise and pricing-wise performance patterns.  

| Visual | Description | Insight |
|--------|--------------|----------|
|  **Bar Chart** | Average Rating by Genre | Identify best-rated genres |
|  **Scatter Chart** | Price vs Rating (Paid Apps Only) | Understand pricing impact on satisfaction |
|  **Treemap** | Top Genres by Installs (1M+ Only) | Highlight genre popularity |
|  **Bar Chart** | Top 5 Categories by Installs | Focus on demand-heavy categories |

**Filters:**  
- Genre  
- Rating Range  
- App Type  

**KPIs:**  
-  Avg Rating by Genre  
-  Total Installs by Category

### 🧭 **Dashboard 2 – App Performance Overview**

**Purpose:** Analyze the relationship between installs, ratings, and engagement.  

| Visual | Description | Insight |
|--------|--------------|----------|
**Scatter Chart** | Installs vs Rating (size = Reviews) | Understand if popularity aligns with satisfaction |
**Table** | Top 10 Highest-Rated Apps (App, Rating, Installs, Reviews) | Identify standout performers |
**Line Chart** | Updates Over Time | Observe app update trends |
**Bar Chart** | Most Reviewed Apps (colored by Rating) | Measure user engagement |
**Treemap** | Top 5 Categories by Installs | Identify leading categories by popularity |

**Filters:**  
- App Type (Free/Paid)  
- Content Rating  
- Category  

**KPIs:**  
-  Average Rating  
-  Total Installs  
-  Total Reviews  
  

##  DAX Measures Used  

DAX
Average Rating
Avg_Rating = AVERAGE('googleplaystore'[Rating])

-- Total Installs
Total_Installs = SUM('googleplaystore'[Installs])

-- Total Reviews
Total_Reviews = SUM('googleplaystore'[Reviews])

-- Average Rating by Category
Category_Avg_Rating =
AVERAGEX(VALUES('googleplaystore'[Category]), [Avg_Rating])

-- Genre Rating Summary Table
Genre_Rating_Summary =
SUMMARIZE(
  'googleplaystore',
  'googleplaystore'[Genres],
  "AvgRating", AVERAGE('googleplaystore'[Rating]),
  "MedianRating", MEDIAN('googleplaystore'[Rating]),
  "AppCount", COUNTROWS('googleplaystore')
)
ainment and Communication as high-demand areas with room for quality improvement.


## Future Improvements

To enhance the analysis further, future versions of this project could include:

 -Time-Series Modeling: Adding trend forecasting to predict installs or ratings over time.

 -Sentiment Analysis: Integrating review text data to perform NLP-based sentiment scoring.

 -Predictive Analytics: Using Power BI + Python integration for churn prediction or app success scoring.

 -Regional Insights: Adding geographical dimensions (if available) for market-based insights.

 -Automated Refresh: Connecting to live Google Play API for real-time dashboard updates.

## Tools & Technologies
Tool	Purpose
Power BI Desktop,	Dashboard creation, data modeling, DAX analysis
Power Query Editor	Data cleaning and transformation
DAX	Custom measures and calculated columns
CSV Dataset	Source data for analysis


## Author

# Name: Sathwika Pudota
Focus Areas: Data Analysis, Business Intelligence, Power BI, Data Storytelling
Contact:
 | sathwikap03@gmail.com
