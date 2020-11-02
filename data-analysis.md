## Data Analysis (27 questions)

#### 1. (Given a Dataset) Analyze this dataset and tell me what you can learn from it.

#### 2. What is R2? What are some other metrics that could be better than R2 and why?
   - R2 is a statistical measure of how close the data are to the fitted regression line.  
   -             R2 = Explained variation / Total variation
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
    

#### 8. How can you determine which features are the most important in your model?
   - Apply principle component analysis
   - Check feature importance by applying random forest
   - Check the absolute value of the Pearson’s correlation between the target and numerical 
     features in our dataset. We keep the top n features
   - Apply Lasso to choose important features
   
#### 9. How do you deal with some of your predictors being missing?
   - 

#### 10. You have several variables that are positively correlated with your response, and you think combining all of the variables could give you a good prediction of your response. However, you see that in the multiple linear regression, one of the weights on the predictors is negative. What could be the issue?


#### 11. Let’s say you’re given an unfeasible amount of predictors in a predictive modeling task. What are some ways to make the prediction more feasible?
 
 
#### 12. Now you have a feasible amount of predictors, but you’re fairly sure that you don’t need all of them. How would you perform feature selection on the dataset?


#### 13. Your linear regression didn’t run and communicates that there are an infinite number of best estimates for the regression coefficients. What could be wrong?


#### 14. You run your regression on di erent subsets of your data, and  nd that in each subset, the beta value for a certain variable varies wildly. What could be the issue here?


#### 15. What is the main idea behind ensemble learning? If I had many different models that predicted the same response variable, what might I want to do to incorporate all of the models? Would you expect this to perform better than an individual model or worse?


#### 16. Given that you have wi  data in your o ce, how would you determine which rooms and areas are underutilized and overutilized?


#### 17. How could you use GPS data from a car to determine the quality of a driver?


#### 18. Given accelerometer, altitude, and fuel usage data from a car, how would you determine the optimum acceleration pattern to drive over hills?


#### 19. Given position data of NBA players in a season’s games, how would you evaluate a basketball player’s defensive ability?


#### 20. How would you quantify the influence of a Twitter user?
 
 
#### 21. Given location data of golf balls in games, how would construct a model that can advise golfers where to aim?


#### 22. You have 100 mathletes and 100 math problems. Each mathlete gets to choose 10 problems to solve. Given data on who got what problem correct, how would you rank the problems in terms of di culty?
 
 
#### 23. You have 5000 people that rank 10 sushis in terms of salt\- iness. How would you aggregate this data to estimate the true saltiness rank in each sushi?


#### 24. Given data on congressional bills and which congressio- nal representatives co-sponsored the bills, how would you determine which other representatives are most similar to yours in voting behavior? How would you evaluate who is the most liberal? Most republican? Most bipartisan?


#### 25. How would you come up with an algorithm to detect pla- giarism in online content?



#### 26. You have data on all purchases of customers at a grocery store. Describe to me how you would program an algo- rithm that would cluster the customers into groups. How would you determine the appropriate number of clusters to include?


#### 27. Let’s say you’re building the recommended music engine at Spotify to recommend people music based on past lis- tening history. How would you approach this problem?

