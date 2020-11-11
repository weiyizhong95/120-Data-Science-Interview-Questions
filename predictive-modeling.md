## Predictive Modeling (19 questions)
#### 1. (Given a Dataset) Analyze this dataset and give me a model that can predict this response variable.


#### 2. What could be some issues if the distribution of the test data is significantly different than the distribution of the training data?
   - Covariate shift: training and test input follow different distributions, but functional relation remains unchanged.
   - Sample selection bias: the training examples have been obtained through a biased method, such as non-uniform selection.
   - Non-stationary environments: Training environment is different from the test one, whether it's due to a temporal or a spatial change. One typical scenario is adversarial classification problems, such as spam filtering and network intrusion detection.

     Reference:http://iwann.ugr.es/2011/pdf/InvitedTalk-FHerrera-IWANN11.pdf
#### 3. What are some ways I can make my model more robust to outliers?
   - Use Tree-based models, which are not affected much by outliers
   - Run non-parametric test when performing a statistical test
   - Use a more robust error metric like mean absolute difference to reduce the infulence of outliers.
   - Make change on data set: transform data or remove outliers
   
     Reference: https://www.quora.com/What-are-methods-to-make-a-predictive-model-more-robust-to-outliers
#### 4. What are some differences you would expect in a model that minimizes squared error, versus a model that minimizes absolute error? In which cases would each error metric be appropriate?
   -  A model learnt by minimizing absolute error might have more variance in the error values in the training data, whereas a model which minimizes squared error would tend to learn a model where errors do not vary a lot.
   -  Mean Absolute Error (MAE): This measures the absolute average distance between the real data and the predicted data, but it fails to punish large errors in prediction.
       If there are more outliers in target values, minimizing absolute error would be better.
   -  Mean Square Error (MSE): This measures the squared average distance between the real data and the predicted data. Here, larger errors are well noted (better than MAE). 
      It's used when you want to penalize much bigger errors versus smaller errors, then minimize the squared error.
      
      Reference: https://www.quora.com/How-would-a-model-change-if-we-minimized-absolute-error-instead-of-squared-error-What-about-the-other-way-around
#### 5. What error metric would you use to evaluate how good a binary classifier is? What if the classes are imbalanced? What if there are more than 2 groups?
   - Precision and Recall, ROC, AUC
   - False Positive Rate, True Positive Rate, Cohen Kappa Metric(how much better is your model over the random classifier)
   - Multi-class: accuracy through confusion matrix

#### 6. What are various ways to predict a binary response variable? Can you compare two of them and tell me when one would be more appropriate? What’s the difference between these? (SVM, Logistic Regression, Naive Bayes, Decision Tree, etc.)
   - Logistic Regression, svm
   - The decision boundary produced by Logistic Regression will always be linear and can not emulate a circular decision boundary. Therefore, it works well for 
     classification problems where classes are approximately lineary separable.
   - SVM works by projecting your feature space into kernel space and making the classes linearly separable. An easier explanation to that process would be that SVM 
     adds an extra dimension to your feature space in a way that makes classes linearly separable. This planar decision boundary when projected back to original feature 
     space emulates non-linear decision boundary.

#### 7. What is regularization and where might it be helpful? What is an example of using regularization in a model?
   - It's used to reduce the error by fitting a function appropriately on the given training set and avoid overfitting without increasing bias.
   - Where there are too many parameters, we use L1 regularization to reduce overfitting

#### 8. Why might it be preferable to include fewer predictors over many?
   - Redundancy
   - Too many predictors will cause overfitting

#### 9. Given training data on tweets and their retweets, how would you predict the number of retweets of a given tweet after 7 days after only observing 2 days worth of data?
   - Build a time series model with the training data with a seven day cycle and then use that for a new data with only 2 days data.
   - Build a regression function to estimate the number of retweets as a function of time t
     to determine if one regression function can be built, see if there are clusters in terms of the trends in the number of retweets
     if not, we have to add features to the regression function
   - features + # of retweets on the first and the second day -> predict the seventh day

     Reference: https://www.besanttechnologies.com/data-science-interview-questions-and-answers

#### 10. How could you collect and analyze data to use social media to predict the weather?
   - Crawl the data from Twitter, Facebook, Instagram filtered by location, then run the NLP processes over the content
   - Then for example, we could construct features from each tweet, e.g. the date, number of favorites, the features we extract from the NLP processes,
     and run multi-variate time series to predict the weather.

     Reference: https://www.quora.com/How-could-you-collect-and-analyze-data-to-use-social-media-to-predict-the-weather
#### 11. How would you construct a feed to show relevant content for a site that involves user interactions with items?
   - Build a recommendation system using item-based filtering

#### 12. How would you design the 'people you may know' feature on LinkedIn or Facebook?
   - Calculate similarity between users using collaborative filtering based on number of connections in between, educations, work experience, interests
     and recommend the ones with high scores

#### 13. How would you predict who someone may want to send a Snapchat or Gmail to?
   - Data processing: feature engineering: contact frequency, also sent/responded ratio, whether content ended with a question mark or
    sentence like "talk soon", "looking forward for your reply".

#### 14. How would you suggest to a franchise where to open a new store?
   - Build master dataset consists of demographic data like local income level, traffic proximity, population density
   - Build a reference dataset on local, regional and national macroeconomic conditions(e.g. unemployment rate, inflation etc.)
   - Collect data on the local frachises
   - Identify a set of KPIs acceptable to the management that had requested the analysis concerning the most desirable factors surrounding a franchise
     such as quarterly operating profit, ROI, EVA, pay-down rate, etc.
   - Run econometric models to understand the relative significance of each variable
   - Run ml models to predict the performance of each location candidate
    
     Reference: https://www.quora.com/How-would-you-suggest-to-a-franchise-where-to-open-a-new-store
#### 15. In a search engine, given partial data on what the user has typed, how would you predict the user’s eventual search query?
   - Historical search frequency of words and sort them from high to low as top candidates
   - Partial string match with past history of words, set a threshold of matchness, and recommend to users
   - Popularity of words searched by other users based on location, date
   
#### 16. Given a database of all previous alumni donations to your university, how would you predict which recent alumni are most likely to donate?
   - Construct logistic regression based on features like family background, GPA, awards, majors, amount of donation

#### 17. You’re Uber and you want to design a heatmap to recommend to drivers where to wait for a passenger. How would you approach this?
   - Based on the frequency of pick-up location passengers requested before as well as the time of the day, the traffic rules
   - Consider the special event happening during the day(information from Facebook or Twitter)

#### 18. How would you build a model to predict a March Madness bracket? 
   - Pick two teams and assign them as two vectors. Take the difference of the two vectors and use that as an input to predict the probability that team A would win by training the model. 
   - Trained the models with historical data containing scores achieved, budget, hit rate of players etc.
   - Predict for the new match by running the model for each round of the match
  
   - Some extensions:
     - Experiment with different ways of consolidating the 2 team vectors into one (e.g concantenating, averaging, etc)
     - Consider using a RNN type model that looks at time series data.

     Reference: https://adeshpande3.github.io/Applying-Machine-Learning-to-March-Madness
#### 19. You want to run a regression to predict the probability of a flight delay, but there are flights with delays of up to 12 hours that are really messing up your model. How can you address this?
   - Run models that are robust to outliers e.g. tree-based model
   - Handle outliers like removing them, replace them with values of neighbors or mean or median
   
