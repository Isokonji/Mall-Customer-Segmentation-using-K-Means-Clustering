# Mall-Customer-Segmentation-using-K-Means-Clustering
 
Overview

This project applies K-Means Clustering to segment mall customers based on their income and spending behavior.
The aim is to uncover meaningful customer groups that can help businesses personalize marketing strategies, design loyalty programs, and optimize targeting.



Objective

To compare the impact of using two vs. three features on cluster quality and interpretability, and identify which approach provides the most actionable segmentation.



Dataset

Mall_Customers.csv — contains 200 records with the following features:

CustomerID

Gender

Age

Annual Income (k$)

Spending Score (1–100)



Project Workflow



1️ Exploratory Data Analysis (EDA)

Checked for missing values, data distribution, and outliers.

Analyzed relationships among Age, Annual Income, and Spending Score.

Found that income and spending score were the most influential factors driving customer segmentation.



2️ Model 1: Three Variables (Age, Income, Spending Score)



Approach:
Used all three features to perform clustering.



Findings:

The 3-variable model resulted in overlapping clusters with less distinction between groups.

Silhouette Score = 0.43, indicating moderate separation.

Age introduced noise, making the boundaries between clusters less clear.


Conclusion:
Adding Age reduced interpretability — customers of different ages still exhibited similar spending patterns when income levels were alike.



3️ Model 2: Two Variables (Income, Spending Score)



Approach:
Focused on only the two strongest behavioral indicators: income and spending.



Results:

Achieved a Silhouette Score of 0.55, showing strong cluster separation and distinct group formation.



Produced five clear and interpretable customer segments:

Cluster	Description
0	Low income, low spending
1	High income, high spending
2	Moderate income, moderate spending
3	High income, low spending
4	Low income, high spending



Insight:
Income and spending score alone capture the main behavioral patterns. This simpler model delivers more actionable insights than the 3-variable version.



4️ Model Evaluation

Used Elbow Method and Silhouette Analysis to determine the optimal number of clusters (k = 5).

Evaluated each model with silhouette_score() from scikit-learn.

Compared cluster boundaries visually using 2D and 3D plots.



5️ Key Business Insights

-High income–high spending → Best target for premium offers and loyalty programs.

-Low income–high spending → Price-sensitive group responsive to promotions.

-Low income–low spending → Low-value segment, limited engagement.

-Moderate income–moderate spending → Stable, middle-market group.

-High income–low spending → Potential customers for upselling strategies.



6️ Technologies Used

Python

Pandas, NumPy — Data Wrangling

Matplotlib, Seaborn — Visualization

Scikit-learn — Clustering and Model Evaluation




7️ Model Files

models/kmeans_2var.pkl → Trained model using 2 variables (Income & Spending Score)

models/kmeans_3var.pkl → Trained model using 3 variables (Age, Income & Spending Score)

models/scaler.pkl → StandardScaler used for feature normalization



8️ How to Run

# Run scripts

python scripts/kmeans_2var.py
https://colab.research.google.com/drive/1SjQidZL_7ydIy9hf-hweXZ0XaFTxqDZa?usp=sharing


python scripts/kmeans_3var.py
https://colab.research.google.com/drive/1HB65MmNtCO0mT_Fnb7B-pkVMRj_ntgoT?usp=sharing



9️ Visualizations
2D Clustering (2 Variables)


<img width="1395" height="750" alt="image" src="https://github.com/user-attachments/assets/00c3dcbc-2958-443d-a36f-4eae372bddac" />




3D Clustering (3 Variables)

<img width="426" height="435" alt="image" src="https://github.com/user-attachments/assets/1e8ee85d-31bd-4240-b386-a67d1cccb545" />





Conclusion

This project demonstrates how K-Means clustering can uncover customer groups that are useful for targeted marketing and business decisions.
The 2-variable model (Income & Spending Score) achieved a higher Silhouette Score (0.55) and more interpretable segments compared to the 3-variable model (0.43).




Takeaway:
In customer segmentation, focusing on a few key behavioral metrics can reveal clearer, more actionable insights than using too many features.
