# Market Basket Analysis with Instacart Dataset

This project performs an in-depth market basket analysis using the Instacart dataset from Kaggle. The primary goal is to understand customer shopping patterns, segment customers based on their behavior, and derive actionable insights.

---

##  Dataset

The analysis is based on the "Instacart Market Basket Analysis" dataset, which contains a sample of over 3 million grocery orders from more than 200,000 Instacart users. The dataset is relational and split into the following files: `aisles.csv`, `departments.csv`, `order_products__prior.csv`, `order_products__train.csv`, `orders.csv`, and `products.csv`.

---

## 💡 Concepts Used

-   **Data Cleaning and Preprocessing**: Merging multiple data sources, handling missing values, and optimizing data types (downcasting) for memory efficiency.
-   **Exploratory Data Analysis (EDA)**: Investigating the data to uncover trends, patterns, and anomalies. This includes analyzing order frequency, basket size, and peak shopping times.
-   **Customer Segmentation**: Using **K-Means clustering**, an unsupervised machine learning algorithm, to group customers into distinct segments based on their purchasing habits.
-   **Data Visualization**: Creating informative plots and charts using `matplotlib` and `seaborn` to present the findings in an easy-to-understand format.

---

## 💻 Code Overview

1.  **Data Loading and Merging**: The script begins by loading the various CSV files into pandas DataFrames and then merging them into a single comprehensive DataFrame.
2.  **Data Preprocessing**: Missing values in the `days_since_prior_order` column are handled, and numerical columns are downcast to more memory-efficient data types.
3.  **User and Behavioral Insights**:
    -   A user-level DataFrame is created by grouping the data by `user_id` and aggregating key metrics such as total orders, total items, average days between orders, and reorder rate.
    -   The distributions of total orders per user and average items per order are visualized, along with the relationship between total orders and reorder rate.
    -   Order patterns are analyzed by day of the week and hour of the day to identify peak shopping times.
4.  **Customer Clustering**:
    -   The Elbow Method is used to determine the optimal number of clusters for K-Means.
    -   Customers are segmented into four distinct clusters based on their ordering behavior.
    -   The characteristics of each cluster are analyzed and visualized using bar and radar charts to create clear customer profiles.

---

## 📊 Results and Conclusion

### User Behavior Insights

-   **Order Distribution**: A majority of customers place a small number of orders, but there is a highly loyal group of customers who order frequently (up to 100 times).
-   **Basket Size**: The typical shopping basket contains 5 to 10 items, suggesting that most orders are for quick refills rather than large stock-ups.
-   **Loyalty and Reordering**: There is a strong positive correlation between the number of orders a customer places and their reorder rate. Loyal customers are more likely to reorder the same products.

### Peak Shopping Times

-   **Day of the Week**: Shopping activity peaks on **Sunday (Day 0)** and **Monday (Day 1)**, with a slump in the middle of the week.
-   **Hour of the Day**: The busiest shopping hours are between **10 AM and 4 PM**.

### Customer Segments

The K-Means clustering algorithm identified four distinct customer segments:

-   **Cluster 0: Loyal Power Shoppers**: This group has the highest number of total orders and items, a high reorder rate, and a short average time between orders. They are Instacart's most valuable customers.
-   **Cluster 1: Occasional, Low-Engagement Shoppers**: These customers have the lowest number of orders and items, a low reorder rate, and a long average time between orders.
-   **Cluster 2: Large-Basket Shoppers**: This segment is characterized by a large number of items per order, although their total number of orders is moderate.
-   **Cluster 3: Regular, Consistent Shoppers**: This is a large group of customers with a moderate number of orders, a good reorder rate, and a consistent shopping schedule.

---

## 🚀 Scope for Improvement

-   **Association Rule Mining**: Apply algorithms like Apriori or FP-Growth to find frequently co-occurring items in customers' baskets.
-   **Predictive Modeling**: Build a model to predict which items a customer is likely to reorder.
-   **Deeper Segmentation**: Incorporate product-level features (aisle, department) into the clustering to create more granular customer segments.