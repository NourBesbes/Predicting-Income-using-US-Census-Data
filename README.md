# Predicting-Income-using-US-Census-Data
In this Exercice, the objective is to explore what kinds of employees will have more possibilities to earn more than 50K USD per year using the US Census dataset which contains informations for approximately 300,000 people.

# Exploring the Dataset
In order to understand better the dataset and the repartition of the variables, I made a series of plots describing continious variables,categorical variables and a correlation plot.
## Correlation plot
First, I Created a correlation plot in order to see if there is any relationship amongst the numerical variables and the income. However, income variable is a factor variable with levels +50000 and -50000 and is unable to be directly added to the correlation plot. Therefore, I made the income variable into a binary variable with levels 0 and 1 to overcome this problem.


Then, i wanted to explore the varibles capital Gain and capital loss, the best way to do it is with a histogram 





## Explore Categorical Data

In order to determine which feature had the biggest impact on the final class "income" of an individual i produced some visual data representation so i looked to what proportion of people earn more than 50K within different:workclass, education, martial status, race ,and sex.

### Work Class
We can see from the table that the private sector has the largest number of population that earn more than 50k per year . However,in termns of proportion we observe from the graph that the "Self-employed incorporated" category has the biggest ratio of high earners.

### Age
I used the command summary to determine the min, max , mean and the str to verify the type ...
summary(train$age) str(train$age) 

The ages range are from 0 to 90 years old with the majority of entries between the ages of 0 to 20 and 30 to 50.
I will segment the age ranges to 2 categories and then look to the class(income) distribution depending on age categories 
Young:(<20)
Adults: (>20)


We can observe from the graph that almost all the young people (age<20) have an income less than $50k. The category of Adult people earn more tha young people 

### Sex
Male employees are more competitive in terms of salary,if we look at the proportion of employees with more than 50k per year.However there is more female than male

### Education
Most of the people earning more than 50k have a bachelor but the highest proportion of them are for those within the "Prof school" category (55%).


### Race 
We can observe from the graph that the Whites are always advantageous in salary,they have the largest proportion of people earning more than 50k 

### Weeks worked
I first made a historgram describing the number of weeks worked 

We can observe that there a are a large number of different values of number of weeks worked (histogram),I decided to groupe them into two categories. 
Huge Work:<45
Normal Work:<=45

We can see that the more you work, the more you earn.The proportion of people winning more than 50k in the group of those working more than 45 weeks per year(HugeWork).

# Classification
I choosed to test the classification methods :  Decision Tree, Random Forest and Logistic Regression.
at the end of each classification i defined the accuracy in order to evaluate them 
## Decision Tree
## Random Forest
## Logistic Regression

# Predictive model evaluation
we conclude that the accuracy of the algorithms are roughly the same, but we can see a little improvement on the prediction of the ">50k" class.
After training all these models using the training data, I chose to keep the Logistic Regression as the most accurate.


RF:0.953088   DT:0.9536394 LR: 


# Conclusion
I divided the analysis into two parts, one serves the purpose of exploratory analysis and the other presents several classification models.The most challenging part for me was cleaning and exploring the data, it was the longest part and the most important to my opinion.
Finally, I have to say that this technical test was very interesting, I enjoyed working on it.






