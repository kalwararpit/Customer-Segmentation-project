# Customer Segmentation for a Subscription App

**Which users should a retention team focus on, and with what message?** K-Means clustering on 10,000 subscription users, turning raw activity data into four behavioural segments with a clear action for each.

## Result

| Segment | Users | Share | What defines it | Churn rate | Suggested action |
|---|---|---|---|---|---|
| **Power users** | 2,682 | 27% | Highest engagement score (4,366) and widest feature use (7.5 features) | **15%** (lowest) | Protect and reward: referral and upsell offers |
| **High-value premium** | 1,029 | 10% | Highest plan fee (35/month) and highest lifetime value (563) | 17% | Priority support, since each loss costs the most revenue |
| **New and active** | 3,314 | 33% | Shortest tenure (~203 days), active in the last 4 days, lowest lifetime value (98) | 18% | Onboarding nudges to widen feature use |
| **Lapsing long-tenure** | 2,975 | 30% | Longest tenure (~571 days) but inactive for ~101 days on average | **26%** (highest) | Win-back campaign before they cancel |

Overall churn in the dataset is 19.7%. The lapsing long-tenure segment churns at 26%, well above that average, and is the clearest retention priority.

## Business problem

A subscription business that treats every user the same wastes retention budget. Grouping users by how they actually behave shows where churn risk is concentrated and which users are worth the most to keep.

## Approach

1. **Data:** 10,000 users with signup date, last active date, plan, monthly fee, sessions, average session duration, features used, support tickets, device type and churn flag. No missing values.
2. **Feature engineering:**
   - `days_since_last_active` (recency) and `tenure_days`
   - `engagement_score` = total sessions × average session duration × features used
   - `ltv` (estimated lifetime value) = tenure in months × monthly fee
3. **Scaling:** nine numerical features standardised with `StandardScaler`.
4. **Clustering:** K-Means, with the elbow method (k = 2 to 10) used to choose **k = 4**.
5. **Profiling:** average recency, tenure, engagement, lifetime value and churn compared across clusters.
6. **Visualisation:** PCA to two components to plot the segments.

## Other findings

- Churn varies little by plan (Basic 20.4%, Standard 19.4%, Premium 17.9%) or by device (Android 19.5%, iOS 19.7%, Web 20.3%).
- Behaviour separates users better than plan or device: recency and engagement drive the gap between 15% and 26% churn.

## Files

| File | Purpose |
|---|---|
| `customer_segmentation.ipynb` | Data preparation, feature engineering, clustering, profiling and PCA plot |
| `subscription_app_users_10k.csv` | User-level dataset (10,000 rows, 11 columns) |

## How to run

```bash
pip install pandas numpy scikit-learn matplotlib jupyter
jupyter notebook customer_segmentation.ipynb
```

## Next steps

- Build a churn prediction model on top of the segments
- Compare K-Means with other clustering methods
- Publish the segment profiles as a Power BI dashboard

## Tools

Python (Pandas, NumPy, scikit-learn, Matplotlib) · Jupyter Notebook

---

**Arpit Kalwar** · [LinkedIn](https://www.linkedin.com/in/arpit-kalwar) · [More projects](https://github.com/kalwararpit)
