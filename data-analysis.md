## Data Analysis (27 questions)

#### 1. (Given a Dataset) Analyze this dataset and tell me what you can learn from it.

#### 2. What is R2? What are some other metrics that could be better than R2 and why?
   - R2 is a statistical measure of how close the data are to the fitted regression line.  
   -              R2 = Explained variation / Total variation
   -  It indicates the percentage of the variance in the dependent variable that the independent variables 
     explain collectively. Therefore, the number should range from 0% to 100%. In general, the higher the 
     R-squared, the better the model fits the data.
   - Limitations: R2 will increase every time you add a predictor to a model, even if it may only due to 
     the increasing number of predictors. Therefore, it never decreases. Also, there will be random noise in the model when there are too
     many predictors, high R2 could be misleading.
   - Other metrics:
        - Adjusted R2: The adjusted R2 tells the percentage of variation explained by only the useful predicators.
        - RMSE: sqrt(MSE) = sqrt(mean((observed - predicted)^2). It measures the average difference between the observed
                outcome values and the values predicted by the model. The lower, the better.
        - MAE: MAE = mean(abs(obervered - predicted)). It measures the prediction error. The lower, the better.
                
#### 3. What is the curse of dimensionality?
   - When there are more features than observations, we might easily fall into the overfitting issue. And observations
     become harder to cluser. Too many dimensions causes every observation in dataset to be equidistant from the others.
     Since clustering techniques depend on "distance" to quantify the similarity between observations, when all the distances
     are euqal, then all the observations appear alike, therefore, no meaningful clusters can be formed. 
     (Tony Yiu, https://towardsdatascience.com/the-curse-of-dimensionality-50dc6e49aa1e)

#### 4. Is more data always better?
   - No. When there are more repeated data, or more biased data points.
#### 5. What are advantages of plotting your data before per- forming analysis?
   - We could understand the overall distribution, missingness  of data, finding out outliers, then generate 
     reasonable hypotheses.

#### 6. How can you make sure that you don’t analyze something that ends up meaningless?
    

#### 7. What is the role of trial and error in data analysis? What is the role of making a hypothesis before diving in?
   - Trail and error are parts of making decision. We make predictions based on prior information and update them according to the 
     new evidence we see. Therefore, trial and error are to make predictions more accurate.
     Reference: https://www.quora.com/What-is-the-role-of-trial-and-error-in-data-analysis
   - The role of making a hypothesis is to predict the results of the future experiment. Then we are going to see whether 
     the performance of the experiment supports our assumptions. It serves as a guide.

#### 8. How can you determine which features are the most important in your model?
   - Apply principle component analysis
   - Check feature importance by applying random forest
   - Check the absolute value of the Pearson’s correlation between the target and numerical 
     features in our dataset. We keep the top n features
   - Apply Lasso to choose important features
   
#### 9. How do you deal with some of your predictors being missing?
   - Here I assume that "missing predictors" means "missing value of predictors"
   - First, I check at the missing value pattern. 
     - If it's missing at completely random, which means that missing values are randomly distributing
       across all observations. For this situation we could check to compare two pars of data - One with missing 
       observations and the other without missing observations - through a t-test. If we do not find any difference
       in means between two samples, we could assume that they are missing at completely random. 
       - in such cases, we could delete them if the amount is small. Or we could replace them using mean or median
         of the non-missing values. But if the amount is large, it may result in loss of variation and it's better 
         to use imputations from the Python package sklearn impute like IterativeImputer, KNNImputer.
     - If it's not missing at random, which means it the missing data has a structure, then we have to treat them 
       carefully. We could use Listwise Deleteion, Pairwise deletion, Mean/Mode substituion, Regression Imputation
       and so on.
       
      Reference: https://blogs.oracle.com/datascience/3-methods-to-handle-missing-data
                 https://liberalarts.utexas.edu/prc/_files/cs/Missing-Data.pdf

#### 10. You have several variables that are positively correlated with your response, and you think combining all of the variables could give you a good prediction of your response. However, you see that in the multiple linear regression, one of the weights on the predictors is negative. What could be the issue?
   -  It may due to the multicollinearity, which refers to a situation in which two or more explanatory variables in a multiple regression model are highly linearly related.

#### 11. Let’s say you’re given an unfeasible amount of predictors in a predictive modeling task. What are some ways to make the prediction more feasible?
   - Run Lasso to find important variables
   - Run PCA
 
#### 12. Now you have a feasible amount of predictors, but you’re fairly sure that you don’t need all of them. How would you perform feature selection on the dataset?
   - Lasso
   - Run PCA
   - Keep variables with high variance, which contins more information
   - Choose features with Tree-based models like random forest based on feature importance
   - Chi-squared: calculate the chi-square metric between the target and the numerical variable and only select the variable with the maximum chi-squared values.
   
#### 13. Your linear regression didn’t run and communicates that there are an infinite number of best estimates for the regression coefficients. What could be wrong?
   - The number of features > observations.
   - Multicollinearity. If some of the explanatory varilables are perfectly correlated then the coefficients would not be unique.

#### 14. You run your regression on dierent subsets of your data, and  nd that in each subset, the beta value for a certain variable varies wildly. What could be the issue here?
   - The dataset might be heterogeneous. It's recommended to cluster datasets into different subsets  wisely,
     and then draw different models for different subsets. Or, use models like non parametric models like trees
     which can deal with heterogeneity.
     
     Reference: 500 Data Science Interview Questions and Answers

#### 15. What is the main idea behind ensemble learning? If I had many different models that predicted the same response variable, what might I want to do to incorporate all of the models? Would you expect this to perform better than an individual model or worse?
   - "Ensemble methods use multiple learning algorithms to obtain better predictive performance than could be obtained from any of the constituent learning algorithms alone."
   - There are some common techniques such as bagging, boosting, bayesian model averaging, bayesian model combination, and stacking.
     For example, when we use stacking, it involves training a learning algorithm to combine the predictions of several other learning algorithms. 
     First, all of the other algorithms are trained using the available data, then a combiner algorithm is trained to make a final prediction using all the predictions of the other algorithms as additional inputs. 
   
   Reference: https://en.wikipedia.org/wiki/Ensemble_learning
   
   
#### 16. Given that you have wi  data in your o ce, how would you determine which rooms and areas are underutilized and overutilized?
   - If the data is more used in one room, then that one is over utilized! Maybe account for the room capacity and normalize the data.

#### 17. How could you use GPS data from a car to determine the quality of a driver?
   - The average speed, the longest duration among all drives, the total miles, sharp conering and braking

#### 18. Given accelerometer, altitude, and fuel usage data from a car, how would you determine the optimum acceleration pattern to drive over hills?
   - Try several trials, during each the duration is fixed, and let the car run from the same start and end, then change 
     the acceleration pattern, such as accelerate slowly until it reach the certain pace, or accelerate slowly to the middle point
     then accelerate qucikly to the certain pace.
   - Each time we measure the consumption of the fuel usage to see which one is the most efficient.
   

#### 19. Given position data of NBA players in a season’s games, how would you evaluate a basketball player’s defensive ability?
   

#### 20. How would you quantify the influence of a Twitter user?
   - The number of follower, likes and retweets of each post, daily interactivity with other users frequency, power of followers(how many followers they have)
 
#### 21. Given location data of golf balls in games, how would construct a model that can advise golfers where to aim?
   - 

#### 22. You have 100 mathletes and 100 math problems. Each mathlete gets to choose 10 problems to solve. Given data on who got what problem correct, how would you rank the problems in terms of di culty?
   - 
 
#### 23. You have 5000 people that rank 10 sushis in terms of salt\- iness. How would you aggregate this data to estimate the true saltiness rank in each sushi?
   - use median

#### 24. Given data on congressional bills and which congressio- nal representatives co-sponsored the bills, how would you determine which other representatives are most similar to yours in voting behavior? How would you evaluate who is the most liberal? Most republican? Most bipartisan?
   - Collaborative filtering. Calculate the similarity for each representatives and select the most similar ones.
   - For liberal and repulican parties, find the mean vector and determine which representative is closest to the center point
   
   Reference: 

#### 25. How would you come up with an algorithm to detect pla- giarism in online content?
   - Calulate the characteristics similarity locally and globally, one takes pre-selected text segments
     as input, and the other takes from larger parts of the tet.
   - String matching. 
   - Bag of words analysis in NLP, where documnets are represented by one or multiple vectors and we could calculate the occurence of each word of each word and compare in two texs.

#### 26. You have data on all purchases of customers at a grocery store. Describe to me how you would program an algo- rithm that would cluster the customers into groups. How would you determine the appropriate number of clusters to include?


#### 27. Let’s say you’re building the recommended music engine at Spotify to recommend people music based on past listening history. How would you approach this problem?

