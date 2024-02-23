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

![0a27787e-c3ea-4039-af47-aa9546772368](https://github.com/BiaBischoff/audience_segmentation/assets/104466669/a3bb281b-1077-44f9-8b5c-070e28168ceb)

The results of the algorithm point to eight separate clusters. 

K-means clustering: In this step we will implement the k-means algorithm. We perform an iteration with 10 steps, utilizing the k-means++ as the initializer. We've set the random state to 42…

![2d9a6898-cd43-4098-9847-d3e8feeb6eb4](https://github.com/BiaBischoff/audience_segmentation/assets/104466669/614b0172-7041-40df-8a93-437b10be10a3)

If we use the elbow method, we observe that the results of the k-means algorithm point to two, four, or nine different clusters. These results differ from the eight clusters found by the hierarchical clustering with the elbow method.

In this case, we’ll opt for the hierarchical clustering results and apply them in the k-means—i.e., perform k-means clustering with eight clusters and analyze the resulting clusters using a summary table.

Finally, I opted for hierarchical clustering results because it can determine the number of clusters, whereas k-means doesn’t, and it’s up to us to choose them with such techniques as the elbow method.

**Model Eval and Results!**

I'll create a summary table to analyze the algorithm's results and the resulting clustering to group the data by segments. Additionally, I’ll add the number of observations it contains and the proportion of these observations for each segment.

Segment	min_watched	CLV	region	Anglo-Saxon	WE	World	Google	Facebook	YouTube	LinkedIn	Twitter	Instagram	Friend	Other	N Obs	Prop Obs
Instagram Explorers	1299.33	115.18	1.19	0.31	0.19	0.50	0.00	0.0	0.00	0.00	0.0	1.0	0.00	0.00	289	0.08
LinkedIn Networkers	1801.27	91.12	2.00	0.00	0.00	1.00	0.00	0.0	0.00	1.00	0.0	0.0	0.00	0.00	391	0.10
Friends' Influence	2018.97	109.12	1.42	0.29	0.00	0.71	0.00	0.0	0.00	0.00	0.0	0.0	1.00	0.00	424	0.11
Google-YouTube Mix	2326.89	103.94	2.00	0.00	0.00	1.00	0.35	0.0	0.54	0.00	0.0	0.0	0.00	0.11	939	0.24
Anglo-Saxon Multi-Channel	1539.15	136.33	0.00	1.00	0.00	0.00	0.25	0.0	0.43	0.18	0.0	0.0	0.00	0.14	1055	0.28
European Multi-Channel	1874.75	157.92	1.00	0.00	1.00	0.00	0.22	0.0	0.34	0.19	0.0	0.0	0.15	0.11	372	0.10
Twitter Devotees	985.33	93.15	1.60	0.17	0.05	0.78	0.00	0.0	0.00	0.00	1.0	0.0	0.00	0.00	58	0.02
Facebook Followers	2767.64	108.26	1.32	0.29	0.10	0.61	0.00	1.0	0.00	0.00	0.0	0.0	0.00	0.00	306	0.08
The columns of the regions are renamed for better readability, here is the original mapping:

Anglo-Saxon - USA, Canada, United Kingdom, Australia
WE - Western Europe
World - Rest of the world

Based on that information, we can formulate the following clusters.

Segment 0 – Instagram (289 Observations): These customers are from all regions, with a slightly larger group from the rest of the world. They discovered the platform through Instagram and have a relatively moderate level of engagement and expenditure.

Segment 1 – LinkedIn (391 Observations): This segment consists entirely of customers from the rest of the world who have heard about your platform via LinkedIn. They have a high level of engagement but slightly lower spending.

Segment 2 – Friends (424 Observations): This group primarily comprises customers from the rest of the world who discovered the platform through friends. They have high engagement and moderate spending.

Segment 3 – Google-YouTube Mix (939 Observations): These customers from the rest of the world discovered the platform via a mix of Google and YouTube. They have very high engagement and moderate spending.

Segment 4 – Anglo-Saxon Multi-Channel (1055 Observations): This segment includes customers from the US, Canada, The UK, and Australia who discovered the platform through a mix of Google, YouTube, and LinkedIn. They have high engagement and higher-than-average spending.

Segment 5 – European Multi-Channel (372 Observations): These customers are from Western Europe and heard about the platform from various sources, including Google, YouTube, LinkedIn, and friends. They have high engagement and the highest spending level.

Segment 6 – Twitter (58 Observations): This small group of customers discovered the platform via Twitter. They’re from all regions, with a majority from the rest of the world. They have the lowest engagement but moderate spending.

Segment 7 – Facebook (306 Observations): This group mainly heard about the platform from Facebook. They are from all regions but predominantly from the rest of the world. They have the highest level of engagement and moderate spending.
