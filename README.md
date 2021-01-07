# 503-project
Math Student Scores Prediction & Analysis 
Group 30: Avery Roper, Abhishek Vikram Mogal, Arinjay Shenoy
Problem :-
Inspired by the Gates Foundation’s “Balance the Equation: A Grand Challenge for Algebra 1”, our group sought to  look into what one can do to improve a student’s math scores. 
To this end we took a dataset from UCI Machine Learning Repository website showing math score data against other survey values and attempted to find important predictors that 
can influence math scores and predict math scores based on these indicators. The hope is that this info can be used to see what variables will lead to higher math scores.

Data Normalization :-
Before any data visualization can be done, the data has to be cleaned. And, by cleaning it means that the data must be sorted so that it can be easily read.
For this purpose the entire dataset is normalized, i.e divided into distinct tables which are connected to each other. 
We went about creating around 14 tables in which 9 tables contained distinct categorical values which were School, Sex, Family size, Address, Mother’s job, 
Father’s job, Guardian, Reason and Parents Status. The other 5 tables referenced the above factors as foreign keys along with all the other factors and were 
named as Data, Family, Location, Education and Student info. With a clear picture of the data, we could proceed to data visualization.

Data Visualization :-
Data visualization was very important because when we explored the data we got a grasp of what is the story behind the data.
Our aim for data visualization was to understand what the data is telling us through visualizations (plotly, matplotlib, seaborn). 
Almost, all the data was normally distributed. All the independent variables showed a linear relationship with the dependent variable Math Grade G3. 
So, it gave us a notion that linear regression may perform well in our case. That is the reason we first started with a linear regression model.
Data cleaning and transformation was done to understand the categorical variables. Corrplot showed us the important variables and then those variables were further analysed.
Scatter plots, histogram, pie charts, bar graphs & confusion matrix were used for data visualization & analysis.

Method :-
In order to find important predictors and predict scores we needed to perform best subset selection and perform a linear regression. 
Before this could be done we had to clean and preprocess the data. First, the full set of predictors was extracted from the sql database, 
excluding student id, G1 and G2 scores, as we don’t wish to predict based on these. Then one hot encoding was used to turn our results into binary 
suitable for reading by the regression function. Next, these variables were cut down by a variance threshold. If the column was used by less than 4% of
the students it was excluded. Cross validation was performed alongside best subset selection on the basis of a chi squared test across a range of allowed predictors. 
The error is lowest at 12 variables so the 12 variables used in each version of cross validation were compared and selected based on the ones that were used most frequently
between them. These new variables were then used for more cross validated regression. The cross validated mean squared error is 17.5. 

Results :-
The first result of our project is the average MSE of 17.5, indicating that a score predicted based off of our model could be expected to be off by about 4 points. 
On a scale of 1 to 20 this is pretty significant. The second result is the subset of predictors used in the model. These show us some of the important factors in 
determining the test score. These variables were age, mother’s education, father’s education, mother’s job, father’s job, reason for attending their school, 
previous failures in the course, whether they received supplementary lessons, if they want to go to college,  whether they’re in a relationship, how much free time they have, 
how much they go out, daily alcohol intake, their health, and how many absences they have.


Bibliography:
P. Cortez and A. Silva. Using Data Mining to Predict Secondary School Student Performance. In A. Brito and J. Teixeira Eds., Proceedings of 5th FUture BUsiness TEChnology Conference (FUBUTEC 2008) pp. 5-12, Porto, Portugal, April, 2008, EUROSIS, ISBN 978-9077381-39-7.
[Web Link]
