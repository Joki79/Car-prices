# Car-prices

This project uses the car dataset published by https://archive.ics.uci.edu/ml/datasets/automobile

The goal in this project is to analyze and impute missign data in the cars datset and then to build and evaluate a linear regression model for predicting car prices.

I will be using Python, and following libraries Pandas, matpolotlib, seaborn and scikit-learn. 

This project will be completed through following steps:

1. loading the dataset and txt file to extract columns

2.removing irrelevant columns and imputing the missing ('?') data

3.changing the datatype where needed and checking for possible collinearity between numerical columns

4.performing encoding of categorical variables and scaling numerical features

5.training and testing linear model 

6.evaluation

7.further considerations



# Unused columns 
I found following columns to be irrelevant or less relevant for the car price: Irrelevant columns: engine location,wheel base,length, width,height,
curb weight,bore(the inner diameter of the cylinder),stroke(the distance within the cylinder the piston travels), compression-ratio(the ratio between the volume of the cylinder and combustion chamber in an internal combustion engine at their maximum and minimum )

By comparing some of the properties I found out that the normalized-loss depends to some extent on symboling, body style, num of doors and make. I utilized those columns to find missing values for the normalized loss.
In case that there were no cars with the same properties I imputed values with the average value for cars that have same symboling value and some common properties

# Collinearity between numerical features
![Screen Shot 2022-02-16 at 5 37 57 PM](https://user-images.githubusercontent.com/57463075/154381611-2e89f21b-e857-4f86-8908-11e1badcf5a8.png)

The engine-size is highly colrelated with the horsepower of the car which is logical, so I keptonly one of these two features- the "horsepower".
Also city mpg and highway mpg are highly correlated. I chose "highway mpg" as a feature because I think that it affects the price of the car more than "city mpg" (at least in the US as you can get to the most destinations using highways. The situation might have been different in Europe...)

# Encoding, scaling and linear regression
I used OneHotEncoder for categorical variables and Feature Scaler for numerical variables

# Evaluation 
The train and test result gave a high value of r- squared which means that 94% and 89% of variations in the price of the car can be explained trough variations in independent features, respectively.

The average percentage error on the test set is 13% of the car price. 

# Further considerations
It is maybe important to mention that 4 missing values from our dataset were actually the dependant variables .When performing the missing value imputation I did imupte those values too taking the average of the prices.
With or without those values the coefficient of determination of my model is almost the same.
However, it is important to aknowledge this. If there were more missing values we would have thougth of the correct approach. Imputing many missing values could lead to the data leakage on one hand and on the other hand imputed values do not cary any valuable information. Something worth of discussion.


# Thank you for reading!
