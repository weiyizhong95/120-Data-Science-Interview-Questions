## Communication (5 questions)


#### 1. Explain to me a technical concept related to the role that you’re interviewing for.
   - Overfitting often occurs when we are building  a model. When we train a model that fits very well on the traning data, but it does bad job on test data,
   there is a high possibility that the model is overfitting. Because the model learns all details and noises in the training data, but not every dataset comes 
   the same, and it will not fit the new data.
   - Overfitting comes usually with nonparametric and nonlinear models, such as random forest, decision trees. 
   - How to solve: 1. feed more data. 2. use L1 or L2 to make regularization. 3. drop out unimportant features. 4. do cross-validation 5. reduce dememsion
#### 2. Introduce me to something you’re passionate about.
#### 3. How would you explain an A/B test to an engineer with no statistics background? A linear regression?
  - A/B testing is a process to show two versions(only one place would be changed) of the same web page to differnt segmemts of users at the same time,
  and then we measure and compare the result according to our metrics.
  - Linear regression model explain the relationship between quantitative independent variables and one quantitative dependent variable. 
#### 4. How would you explain a confidence interval to an engineer with no statistics background? What does 95% confidence mean?
  - The confidence interval is a range that we believe it will cover the true number at a certain level. Supposed we select 300 
    students at six grade from a school to estimate their heights, we will try to observe a sample of 100 students and calculate the sample mean, 
    then repeat this process. Each sample mean will differ from each other, so that we get an interval, which contains the upper bound(the highest
    sample mean) and a lower bound(the lowest sample mean). There is a high chance that this interval will cover the mean of all studetns' heights.
  - Since we could not let this interval grow unlimitedly, therefore, we put the confidence level. Usually we take 95%, which means that  
    95% of the interval will cover the mean of all studetns' height. One more example is, we repeatedly draw a sample 10000 times, there will be 
    10000 different interval, then there are approximately 9500 intervals
    will cover the true value(chance of 100%), and the other 500 intervals will not(chance of 0%).
#### 5. How would you explain to a group of senior executives why data is important?
  -  First, data tells truth. Some people will tell a lie, others won't. When a person says that he goes to the gym 5 times a week, but the record 
     shows that he just does that 2 times a week for three months. Now, who to believe?
  -  Second, data records the past and helps to improve. How has the sales/revenue changed over the past few years? 
     Which marketing channel does the best for us? It's a resource for us predict the future. 
  -  Thrid, data helps us understand the performance in time or even at a real time, so that we could quickly response to the shifting market.
  -  Last but not least, it helps us understand our customers better. Where and how to find new customers? What do customers like most now, by segments? 
    