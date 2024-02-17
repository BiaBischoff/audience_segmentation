# Audience Segmentation (topics covered: data analysis, unsupervised learning, machine learning)

Exploring K-Means and Hierarchical Clustering for Effective Marketing Strategies

![aa3f1b2c2711b7a72cc4164369ebfbb7_cjflhqhjr-008-l-0-qfckonz-87-fm](https://github.com/BiaBischoff/audience_segmentation/assets/104466669/c88d1c55-9a8c-4422-9248-9e4cf31c5653)

**Case Description**

To what extent does our platform’s acquisition channel influence the learning outcomes of our students?

Are there any geographical locations where most of our students discover the platform, specifically through social media platforms like YouTube or Facebook?

You will work on real-world customer data to perform market segmentation—crucial for businesses to understand customer behavior and improve marketing efficiency. The project will involve data preprocessing, exploratory data analysis (EDA), feature engineering, implementation of clustering algorithms, and interpretation of results. You’ll use two popular clustering techniques: k-means and hierarchical clustering.

In the Customer Segmentation in Marketing with Python project, you’ll delve into the diversity of customer behavior and identify distinct segments that could be targeted with personalized marketing strategies.

In the provided dataset, we have information about the country of residence, customer lifetime value, and overall engagement. 

After loading the data, we notice that we have some missing values in the minutes watched column. Meaning that some customers purchased a product but havent watched it yet. So it doesn't make sense to remove them. That's why I replaced the missing values with 0.

Feature Engineering: To perform a quantitative analysis of the groups, we’ll create dummy variables for the region of countries and the survey answers. These are categorical answers, so having them as dummy variables makes sense.

Data Visualization and Correlation Analysis: We can use standard exploratory data analysis after preprocessing and introducing the dummy variables. We start by estimating the correlation index between the variables.

![corr](https://github.com/BiaBischoff/audience_segmentation/assets/104466669/ff0da015-3654-4aac-8579-f9416d281813)

This analysis does not reveal strong or positive correlations within the data. We must employ more sophisticated learning methods to understand the relationships within the data.

Next, we want to create a scatter plot of the two numerical values in our data: minutes watched and the CLV.

![Unknown](https://github.com/BiaBischoff/audience_segmentation/assets/104466669/b84188c7-4d10-4c90-8a61-556b4a06bc36)

Hierarchical clustering: After the data standardization is complete, we can finally utilize the necessary clustering techniques, starting with hierarchical clustering. We’ll use Ward’s method for clustering.

![hierarchical](https://github.com/BiaBischoff/audience_segmentation/assets/104466669/1417e479-239f-4906-a6f6-a373e191270d)

The results of the algorithm point to eight separate clusters. 

K-means clustering: In this step we will implement the k-means algorithm. We perform an iteration with 10 steps, utilizing the k-means++ as the initializer. We've set the random state to 42…

![line_chart](https://github.com/BiaBischoff/audience_segmentation/assets/104466669/80116159-13cf-4d8a-8c4e-f7f950ea3379)

If we use the elbow method, we observe that the results of the k-means algorithm point to two, four, or nine different clusters. These results differ from the eight clusters found by the hierarchical clustering with the elbow method.

In this case, we’ll opt for the hierarchical clustering results and apply them in the k-means—i.e., perform k-means clustering with eight clusters and analyze the resulting clusters using a summary table.

Finally, I opted for hierarchical clustering results because it can determine the number of clusters, whereas k-means doesn’t, and it’s up to us to choose them with such techniques as the elbow method.




