# Terry Traffic Stop Arrest Analysis

## Objective
Using a dataset of 45,376 police reported stops under Terry v. Ohio, 392 U.S. a(1968), the objective is to find the demographic variables that most influence arresting a subject. I will then use this information to attempt to predict future arrests based on certain demographics.

## First things First
The first step in analyzing this large data set is to clean and organize the data.  Processes included removing extra spaces, removing data that would not be used, replacing dashes with "unknown", combining duplicate columns and creating dummies for all relevant variables.  In total, the revised dataset contained 41 demographic related columns.

## EDA
After plotting some graphs, there were some features that stood out including age of officer, gender of officer and certain precincts.  
![Optional Text](https://github.com/crissymae/TerryTrafficStops/blob/master/Precinct%20Bar%20Graph.png)

However, after some thought, these particular demographics could make up the same % of the total police force population.  Also, there is a huge imbalance of arrests vs no arrests, so that will need to be handled before moving forward with modeling.

## Dealing with Data Imbalance
Looking at the target variable, ArrestFlag_Y, there is an obvious data imbalance.
![Optional Text](https://github.com/crissymae/TerryTrafficStops/blob/master/Before%20and%20After%20Smote.png)

The first image is the original data count for the ArrestFlag_Y.  It is extremely important to find a technique to deal with imbalance as the model will not perform well when predicting, specifically for the minority class. So, I used the smote technique to even things out. Much better numbers to work with!

## Final Model: Bagged Tree
The model that produced the best results was Bagged Tree.

![Optional Text](https://github.com/crissymae/TerryTrafficStops/blob/master/Winning%20Model.png)

I did run a Grid Search on the bagged tree model but it resulted in a lower precision score than the original bagged tree model, so I kept the original parameters.
