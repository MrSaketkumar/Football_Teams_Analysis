# Football_Teams_Analysis
Exploratory descriptive Analysis of Football teams 
Through a comprehensive analysis of the dataset, we've gained valuable insights into the characteristics and performance metrics of strikers. By segmenting and classifying the strikers based on their attributes and performance and develop predictive models. This involves multiple stages of data handling and analytical techniques to derive actionable insights. Specifically, the goals are to:

Clean and prepare the dataset by identifying and handling missing values, verifying data types, and eliminating duplicates to ensure accuracy and completeness.

Explore and visualize player performance attributes through descriptive statistics and graphical representations, helping to identify key patterns and distributions.

Apply statistical tests (such as ANOVA and Shapiro-Wilk) to determine whether significant differences exist across nationalities and performance metrics.

Engineer new performance metrics, particularly a holistic 'Total Contribution' score, to better represent a player's all-around effectiveness.

Use unsupervised learning (K-Means clustering) to group players into distinct performance tiers—'Best Strikers' and 'Regular Strikers'—based on multidimensional attributes.

Build a classification model (Logistic Regression) to predict striker performance categories using scaled and encoded features, validating its predictive power through accuracy metrics.

Provide data-driven conclusions and recommendations for talent identification, performance improvement strategies, and future modeling enhancements.

Data Cleaning & Preprocessing.

    Imputed with mean values for: Movement off the Ball, Penalty Success Rate,Big Game Performance.

Exploratory Data Analysis (EDA)

    1) Footedness Distribution: Right-footed: 53.4% , Left-footed: 46.6%

    2) Nationality vs. Footedness:  Spain had the most balanced footedness distribution, England had the highest number of right-footed players.

    3) Average Goals by Nationality:

Nation	Avg Goals

    Brazil	15.80

    Spain	15.20

    France	14.90

    Germany	14.86

    England	14.47

4) Avg Conversion Rate by Footedness:

       Left-footed	0.198
       Right-footed	0.201


5)Statistical Analysis.

a) Shapiro-Wilk Test: Both Consistency and Hold-up Play followed normal distributions.

b) ANOVA: Tested if Consistency varied by nationality.

    p-value = 0.192, so no significant difference found.

c) Correlation: Weak positive correlation between:

    Consistency and Hold-up Play: r = 0.145

d) Linear Regression:

     Dependent Variable: Consistency

     R-squared: 0.021

     p-value (Hold-up Play): 0.00114 (significant)
 
     Small but statistically significant effect of Hold-up Play on Consistency.

e) Clustering (K-Means)
  
     Elbow Method: Determined optimal clusters = 2 based on WCSS plot.

 e.1) KMeans Application:

     kmeans = KMeans(n_clusters=2)

     Cluster 0: Best Strikers

     Cluster 1: Regular Strikers

6) Labeling: Created Strikers_Type based on cluster label.

   Cluster Averages:

       Best Strikers: Avg Total Contribution = 143.5

       Regular Strikers: Avg Total Contribution = 118.4

7) Classification Model

   Objective: Predict Strikers_Type using logistic regression.

8) Data Preparation:

 a) Features scaled using both StandardScaler and MinMaxScaler

       Final model used MinMaxScaler

 b) Train-Test Split: 80% train, 20% test

9) Model Training:

        model = LogisticRegression()

        model.fit(x_train, y_train).

The analysis successfully integrated data preprocessing, EDA, statistical evaluation, clustering, and classification to offer a robust assessment of striker performanance.

Most features were complete or easily imputed with minimal information loss.

Right-footed players slightly outperformed left-footed players in goal conversion.

No statistically significant difference in consistency was found across nationalities.

Weak but significant correlation exists between consistency and hold-up play.

Clustering revealed two meaningful groups: Best and Regular Strikers.

A derived metric, Total Contribution, helped quantify holistic performance.

Logistic Regression achieved perfect classification accuracy when predicting striker type.






