Customer Segmentation Project

This project explores user behavior in a subscription-based app and groups customers into segments using clustering techniques. The aim is to understand how different types of users interact with the product and to identify patterns that can help improve engagement and retention.

Project Summary

The dataset includes 10,000 users with information about their activity, subscription plan, session behavior, and churn status. To make the data more useful for analysis, additional features were created such as days since last activity, tenure, engagement score, and estimated lifetime value.

K-Means clustering was used to divide customers into four groups. The elbow method helped determine the ideal number of clusters, and PCA was used to visualize how the groups differ. Each cluster shows different behavior in terms of engagement, session activity, and likelihood of churn.

Main Steps

Cleaned and prepared the dataset

Created new features based on user activity

Standardized numerical variables

Applied K-Means clustering

Analyzed each cluster’s characteristics

Visualized clusters using PCA

Cluster Insights

The analysis resulted in four customer segments:

High Engagement Users – very active with strong usage patterns

Regular Users – moderate and consistent app activity

Low Engagement Long-Term Users – long tenure but low activity

New or At-Risk Users – recently joined and not very active

These segments can help guide decisions on retention and targeted communication.

customer churn analysis.ipynb
subscription_app_users_10k.csv
README.md
Tools Used

Python

Pandas

NumPy

Scikit-Learn

Matplotlib

Jupyter Notebook

Future Work

Build a churn prediction model

Add more user behavior metrics

Compare different clustering methods

Create dashboards for easier reporting

✨ Author

Arpit Kalwar
MBA Candidate | Aspiring Business Analyst
Passionate about data-driven problem solving.
