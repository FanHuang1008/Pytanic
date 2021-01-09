# Pytanic
 Titanic - Machine Learning from Disaster | Kaggle

First, we need to import the libraries and the data. There are 891 rows, 11 features, and the target (Survived) in the training-set. Let’s take a closer look at the missing data. The Embarked feature has only 2 missing values, which can easily be filled. The Age feature has 177 missing values. We might want to drop the Cabin feature from the dataset since 77% of the values are missing.
 
 
From the plot we can see clearly that Pclass and Sex are contributing to a person’s chance of survival. Female has a higher probability of survival, regardless of their class. A person’s chance of survival increases as class increases.The survival chances are highest between 15 and 40 for women. As for men, the highest probability of survival occurs between 25 and 40. It is worth noting that infants have a higher probability of survival. Those who embarked from port Cherbourg have a higher chance of survival.
 
 
It would make more sense to create a new feature that shows the total number of relatives a person has on the boat (Relatives = SibSp + Parch + 1). A high probability of survival occurs between 2 and 4.


The first letter of “Cabin” refers to the deck. Therefore, we are going to create a new feature that contains the deck information. Afterwards we will convert the feature into a numeric variable. Missing values or rare values will be converted to 8, then we can drop “Cabin”. Next, we will extract the “Title” from “Name” and divided them into five groups. An array of random numbers will be created to fill in the missing age values. The random numbers are computed based on the mean and standard deviation of different title group. Since the Embarked feature has only two missing values, we will just fill them with the most common one.


We will convert “Sex”, “Fare”, and “Embarked” into numeric features. Since “Fare” has only one missing value in the testing set, we will fill it with median.


Before building a machine learning model, I want to add 3 new feature that are computed out of other features: “Connected_Survival”, “Age_class”, and “Fare_grp”.  People holding the same ticket could either be friends or family. If the SibSp and Parch features both equals to zero, then they’re friends. The default value of “Connected_Survival” will be set to 0.5. If any other group member survived, “Connected_Survival” will be changed to 1. Else if any other group member died, “Connected_Survival” will be changed to 0. The “Ticket” and “PassengerId” features will be dropped since we won’t need them anymore.
 
 
After splitting the training set and testing set, each feature will be scaled to 0 and 1. We will build and train our multilayer perceptron neural network. There are two hidden layers with 40 and 30 neurons respectively. Weights are initialized to small uniformly random values between 0 and 0.05. Finally, we will use the trained model to make predictions on the testing set. The best score is 0.81100, which is ranked 627 among 19641 teams.
