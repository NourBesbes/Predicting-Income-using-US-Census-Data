# Predicting-Income-using-US-Census-Data
In this Exercice, the objective is to explore what kinds of employees will have more possibilities to earn more than 50K USD per year using the US Census dataset which contains informations for approximately 300,000 people For each one, we have 42 socioeconomic variables.<br/>
The steps of cleaning and exploring the data are described in the Cleaning and exploring Data.R file.<br/>
The steps of The Classification are described in the Classification.R file.
# Exploring the Dataset
In order to understand better the dataset and the repartition of the variables, I made a series of plots describing continious variables,categorical variables and a correlation plot.
## Correlation plot
First, I Created a correlation plot in order to see if there is any relationship amongst the numerical variables and the income. However, income variable is a factor variable with levels +50000 and -50000 and is unable to be directly added to the correlation plot. Therefore, I made the income variable into a binary variable with levels 0 and 1 to overcome this problem.

![Alt text](./Plots/Rplot.png?raw=true)

## Explore Categorical Data

In order to determine which feature had the biggest impact on the final class "income" of an individual i produced some visual data representation so i looked to what proportion of people earn more than 50K within different:workclass, education, martial status, race ,and sex.

### Work Class
We can see from the table that the private sector has the largest number of population that earn more than 50k per year . However,in termns of proportion we observe from the graph that the "Self-employed incorporated" category has the biggest ratio of high earners.

![Alt text](./Plots/workclass.png?raw=true)

![Alt text](./Plots/TableWorkClass.png?raw=true)
### Age
I used the command summary to determine the min, max , mean and the str to verify the type ...
summary(train$age) str(train$age) 

![Alt text](./Plots/ageSummary.png?raw=true)

The ages range are from 0 to 90 years old with the majority of entries between the ages of 0 to 20 and 30 to 50.
I will segment the age ranges to 2 categories and then look to the class(income) distribution depending on age categories 
Young:(<20)
Adults: (>20)

![Alt text](./Plots/Age.png?raw=true)

We can observe from the graph that almost all the young people (age<20) have an income less than $50k. The category of Adult people earn more tha young people 

### Sex
Male employees are more competitive in terms of salary,if we look at the proportion of employees with more than 50k per year.However there is more female than male

![Alt text](./Plots/sex.png?raw=true)


### Education
Most of the people earning more than 50k have a bachelor but the highest proportion of them are for those within the "Prof school" category (55%).

![Alt text](./Plots/education.png?raw=true)
![Alt text](./Plots/TabeEducation.png?raw=true)

### Race 
We can observe from the graph that the Whites are always advantageous in salary,they have the largest proportion of people earning more than 50k.

![Alt text](./Plots/races.png?raw=true)

### Weeks worked
I first made a historgram describing the number of weeks worked 

![Alt text](./Plots/histWeek.png?raw=true)

We can observe that there a are a large number of different values of number of weeks worked (histogram),I decided to groupe them into two categories. 
Huge Work:<45
Normal Work:<=45

![Alt text](./Plots/week.png?raw=true)

We can see that the more you work, the more you earn.The proportion of people winning more than 50k in the group of those working more than 45 weeks per year(HugeWork).

# Classification
I choosed to test the classification methods :  Decision Tree, Random Forest and Logistic Regression.
at the end of each classification i defined the accuracy in order to evaluate them.
First we will want to split our training set into subsets for training and testing. We will do a 70/30 split
## Decision Tree
I created a simple decision tree with default parameters,as a result i got a  simple tree (9 leaves) . The attributes  selected to classify the data : WeeksWorkedInYear,dividendsFromStocks, taxFiler, education, capitalGain,capitalLoss and sex.<br/>
![Alt text](./Plots/DT.png?raw=true)
<br/>
I go the confusion matrix:<br/>
![Alt text](./Plots/AccDT.png?raw=true)<br/>
The Accuracy : 0.9515001 
## Random Forest
I choosed to test Random Forest because it's robust to correlated covariates & outliers in general.I created a model with default parameters :</br>
randomForest(formula = income ~ ., data = training) 
               Type of random forest: classification
                     Number of trees: 500
No. of variables tried at each split: 4<br/>
I go the confusion matrix:<br/>
![Alt text](./Plots/RF.png?raw=true)<br/>
The Accuracy : 0.9516107 
## Logistic Regression
I go the confusion matrix:<br/>
![Alt text](./Plots/LR.png?raw=true)<br/>
This Accuracy : <b>0.9546226 </b>

# Predictive model evaluation
we conclude that the accuracy of the algorithms are roughly the same, but we can see a little improvement on the prediction of the ">50k" class.<br/>
After training all these models using the training data, I chose to keep the Logistic Regression as the most accurate.
Finally, I was evaluated the Logistic Regression Model on the test set. By  the previous methodology we got the following confusion matrix:<br/>
![Alt text](./Plots/test.png?raw=true)

# Conclusion
I divided the analysis into two parts, one serves the purpose of exploratory analysis and the other presents several classification models.The most challenging part for me was cleaning and exploring the data, it was the longest part and the most important to my opinion.Therefore, I had to use the knowledge I acquired on coursera courses(Data Science Specialization by the Johns Hopkins University for example) for this part.<br/>
Finally, I have to admit that this technical test was very interesting, I enjoyed working on it.






