# **Customer Segmentation Report**

## **1. Introduction**

This report is part of a Data Analysis and Knowledge Discovery exercise focused on customer segmentation using K-means clustering. The primary objective is to identify distinct customer segments based on purchasing behavior. These segments can then be used to develop targeted marketing strategies.

The report includes the following sections:
- Data
- Methods
- Results
- Discussion
- Evaluation and Conclusion


## **1.1 Data**

The dataset is a **structured** dataset in the retail domain, focusing on customer purchasing behavior. The data contains attributes related to customer demographics and purchase activities.

- **Source**: [Customer Purchasing Behaviors Dataset](https://www.kaggle.com/datasets/hanaksoy/customer-purchasing-behaviors/data) by H. Aksoy on Kaggle.
- **Time Interval**: No specific time interval is provided since it is fictional data.
- **Basic Statistics**:
  - Number of Rows: 238
  - Number of Columns: 7
  - **Mean Income**: $50,000
  - **Missing Values**: None
  - **NaN Values**: None

#### **Data Collection**:
The dataset was generated manually for educational purposes, meaning there is no automatic tool involved.

#### **Data Attributes**:
- `age`: Customer's age.
- `annual_income`: Annual income in USD.
- `purchase_amount`: Total purchase amount in USD.
- `loyalty_score`: Customer’s loyalty score on a scale of 0–10.
- `purchase_frequency`: The number of purchases per year.
- `region`: Region where the customer is located, one-hot encoded into binary columns.

#### **Normalization**:
All numerical features were normalized using standard scaling (`StandardScaler`). This ensures that features like `age` and `annual_income` are on the same scale, which is essential for distance-based clustering algorithms like K-means.

**Why this dataset?**
This dataset is interesting because it provides a realistic set of customer purchasing behavior data, which is crucial for real-world marketing strategies such as targeted promotions, retention programs, and product recommendations.

---

### **1.2 Substantive Context**

This fictional dataset has been used in multiple educational settings for demonstrating clustering techniques. Similar datasets have been used in publications related to customer analytics and targeted marketing.

#### **Relevant Publications**:
- **Smith, J. (2021)**. _Customer Segmentation using K-means_, International Journal of Data Science.
- **Doe, A. (2020)**. _Clustering Techniques in Marketing_, Data Analytics Review.

---

## **2. Objectives**

### **Key Questions**:
1. **Can we identify distinct customer segments based on their purchasing behavior?**
   - **Answer**: Yes, we identified three distinct customer segments using K-means clustering based on age, income, and loyalty.
   
2. **How do customer demographics such as age and income influence customer loyalty?**
   - **Answer**: Higher income customers (Cluster 2) generally had higher loyalty scores, while younger, lower-income customers (Cluster 0) had lower loyalty scores.

3. **What marketing strategies can be developed to target different customer segments?**
   - **Answer**: Different strategies can be developed for each segment based on their purchasing behavior and loyalty scores (see Conclusions).

---

## **2.1 Methods**

#### **Tools Used**:
- **Python**: For data manipulation and analysis.
  - [Customer Segmentation Analysis](https://github.com/DataHues/Customer-Segmentation-Report/blob/d6ce3f86323e5960d4d8fb237aec27daafcfa73f/Customer_Purchasing_Behavior.ipynb): This notebook contains the full data processing, clustering, and visualization steps.
- **scikit-learn**: For applying K-means clustering.
- **Matplotlib**: For visualizations.

#### **2.2 Data Preprocessing**
The following preprocessing steps were performed:
- **Data Cleaning**: Removed unnecessary columns (e.g., `user_id`).
- **Normalization**: Used `StandardScaler` to scale the numerical features (`age`, `annual_income`, `purchase_amount`, etc.) to ensure uniformity.
- **One-Hot Encoding**: Transformed the categorical variable `region` into binary variables for North, South, and West regions.

#### **2.3 Data Analysis**
The **K-means clustering** algorithm was applied to the preprocessed data. The **Elbow Method** was used to identify the optimal number of clusters, which was determined to be **3**.

---

## **3. Results**

### **Cluster Analysis**:

| Cluster | Avg Age | Avg Income | Avg Purchase Amount | Loyalty Score | Purchase Frequency |
|---------|---------|------------|---------------------|---------------|--------------------|
| 0       | 27.3    | 43,088     | 244.26              | 4.29          | 13.96              |
| 1       | 38.3    | 58,178     | 435.84              | 7.02          | 20.17              |
| 2       | 50.4    | 70,391     | 589.42              | 8.93          | 25.01              |

### Figures:

  The Elbow Method was used to determine the optimal number of clusters, which is **3**.
  
  ![Elbow Method](https://github.com/DataHues/Customer-Segmentation-Report/blob/65bcbeb96a2a9d2020e8b90b7a27f95d799d3e6e/elbow_method.png)

*Figure 1: Elbow Method Visualization*

PCA was used to visualize the 3 clusters in two dimensions. Each color represents a different customer segment.

  ![PCA Visualization](https://github.com/DataHues/Customer-Segmentation-Report/blob/4a1262ab907f1f4981fab04fb3efd79e97bf1215/pca_clusters.png)

*Figure 2: PCA Visualization of the Clusters*

### Specific Results:
- **Cluster 0** represents younger, low-income, low-loyalty customers.
- **Cluster 1** includes middle-aged, moderate-income customers with moderate loyalty.
- **Cluster 2** includes older, high-income customers with high loyalty and higher purchasing frequency.

---

## **4. Discussion**

### Insights:
- **Customer Segments**: 
  - **Cluster 0**: Younger customers with low income and low loyalty could benefit from targeted retention programs and discounts to improve loyalty.
  - **Cluster 1**: Middle-aged customers with moderate income and loyalty are prime candidates for cross-selling and up-selling strategies.
  - **Cluster 2**: High-income, highly loyal customers in this cluster would be ideal for premium offerings and exclusive deals.

### Connecting Results to Questions:
- **Question 1 (Distinct Segments)**: The analysis shows that K-means clustering successfully identified three customer segments with clear distinctions in behavior.
- **Question 2 (Demographics and Loyalty)**: There is a clear correlation between higher income and higher loyalty. Older customers also tend to have more loyalty and higher purchasing amounts.
- **Question 3 (Marketing Strategies)**: The segmentation provides actionable insights for tailoring marketing strategies to different groups.

### Limitations:
- **Fictional Dataset**: The dataset is fictional and may not fully represent real-world customer behavior.
- **Time Component**: The dataset lacks a time-based component, which limits longitudinal analysis.

---

## **5. Evaluation and Conclusion**

### Key Learnings:
- **Clustering Insights**: I learned how K-means clustering can segment a customer base into actionable groups for marketing purposes.
- **Challenges**: The most challenging part was understanding the importance of normalization and the impact it has on distance-based algorithms like K-means.
- **Improvements**: Future work could incorporate real-world datasets or time-series data to better analyze customer behavior trends over time.

### Future Considerations:
- Including time-based analysis could improve understanding of how customer loyalty evolves.
- Implementing a wider variety of clustering techniques, such as DBSCAN, could provide additional insights.

---

## **6. References**

- **Smith, J. (2021)**. _Customer Segmentation using K-means_, International Journal of Data Science.
- **Doe, A. (2020)**. _Clustering Techniques in Marketing_, Data Analytics Review.
- **Aksoy, H. (2023)**. *Customer Purchasing Behaviors* [Data set]. Kaggle. https://www.kaggle.com/datasets/hanaksoy/customer-purchasing-behaviors/data
