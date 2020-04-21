We use pandas for data interpretation with python

```python

import pandas as pd

```

Most important part of pandas is DataFrame. It holds the table like data.We look at house prices in melbourne data.in here, the data is at the file path '../input/melb_data.csv'
<br>
We load the data with following commands

```python

#save filepath to variable for easier access
melbourne_file_path = '../input/melb_data.csv'

#read the data and store data in DataFrame titled melbourne_data
melbourne_data = pd.read_csv(melbourne_file_path)

#print a summary of data in Melbourne Data
melbourne_data.describe()

```
### Selecting Data for Modeling
We start by picking a few variables from a large set of data. To choose variables/columns, we use columns property of DataFrame

```python

melbourne_file_path = '../input/melb_data.csv'
melbourne_data = pd.read_csv(melbourne_file_path)
melbourne_data.columns

Output - 

Index(['Suburb', 'Address', 'Rooms', 'Type', 'Price', 'Method', 'SellerG',
       'Date', 'Distance', 'Postcode', 'Bedroom2', 'Bathroom', 'Car',
       'Landsize', 'BuildingArea', 'YearBuilt', 'CouncilArea', 'Lattitude',
       'Longtitude', 'Regionname', 'Propertycount'],
      dtype='object')

```
This prints the variables(column headings) in our data
<br>
<br>

missing values are values in data that weren't recorded for some reasons. Melbourne data has some missing values

```python

#For now we would just drop the houses from data
#dropna drops missing values ( think of na as 'not available )

melbourne_data.dropna(axis = 0)

```

There are many ways to select a subset of your data but we will focus on two approaches for now.

<br>
* Dot notation, which we use to select the "prediction target"<br>
* Selecting with a column list, which we use to select the "features"
<br>

### Selecting the Prediction Target

we can pull out a variable with dot notation. This single columnis stored in **Series**, which is broadly like a dataFrame with only a single column of data.

<br>
We use dot notation to select the column we want to predict, which is called the **prediction target**. By convention, the prediction target is called **y**. So the code is

```python

y = melbourne_data.Price
```
### Choosing "Features"

Columns added or inputted in our model  (and later used tomake predictions) are called "features". In our case, those would be the columns used to determine home price.Sometimes, you will use all columns except the target as features.
<br>

We select multiple features by providing a list of column names inside brackets. Each item in that list should be a string
(with quotes)
<br>

Example

```python

melbourne_features = ['Rooms', 'Bathroom', 'Landsize', 'Lattitude', 'Longitude']
```

By convention. this data is called **X**

```python

X = melbourne_data[melbourne_features]

```

Let's review the data using **describe** method and **head** method which shows the top few rows

```python

X.describe()

Output - 

        Rooms	        Bathroom	Landsize	Lattitude	Longtitude
count	6196.000000	6196.000000	6196.000000	6196.000000	6196.000000
mean	2.931407	1.576340	471.006940	-37.807904	144.990201
std	0.971079	0.711362	897.449881	0.075850	0.099165
min	1.000000	1.000000	0.000000	-38.164920	144.542370
25%	2.000000	1.000000	152.000000	-37.855438	144.926198
50%	3.000000	1.000000	373.000000	-37.802250	144.995800
75%	4.000000	2.000000	628.000000	-37.758200	145.052700
max	8.000000	8.000000	37000.000000	-37.457090	145.526350

```

head

```python

X.head()

Output - 

	Rooms	Bathroom	Landsize	Lattitude	Longtitude
1	2	1.0	         156.0	-37.8079	144.9934
2	3	2.0	         134.0	-37.8093	144.9944
4	4	1.0	         120.0	-37.8072	144.9941
6	3	2.0	         245.0	-37.8024	144.9993
7	2	1.0	         256.0	-37.8060	144.9954

```

### Buliding the model

We will use scikit - learn library to create your models. written as **sklearn**. Scikit is popular for modeling types of data typically stored in DataFrames.

<br>
<br>
Steps to build a model - <br>

* Define - What type of model? Decision tree? Some other model?
* Fit - Capture patterns from provided data. this is the heart of modeling.
* Predict - Just what it sounds like
* Evaluate - Determine how accurate the model's predictions are

<br>

Here we have an example of defining a decision tree model with scikit learn and fitting it with features and target variables.

```python

from sklearn.tree import DecisionTreeRegressor

# Define model. Specify a number for random_state to ensure same results each run
melbourne_model = DecisionTreeRegressor(random_state = 1)

#Fit model
melbourne_model.fit(X,y)
 
```

many ML models allow for some randomness. Specifying a number for **random_state** ensures you get the same results in each run. This is a good practice. We can use any number and model quality won't depend on what value we choose

<br>
<br>
We mow have a fitted model that we can use to make predictions.
<br>
Originally, we want to predict the prices of houses coming on the market rather than of the houses we already have but we'll make predictions for the first few rows of training data to see how the prediction function works.

```python

print("making predictions for the following five houses:")
print (X.head())
print("The predictions are")
print(melbourne_model.predict(X.head()))

Output - 

Making predictions for the following 5 houses:
   Rooms  Bathroom  Landsize  Lattitude  Longtitude
1      2       1.0     156.0   -37.8079    144.9934
2      3       2.0     134.0   -37.8093    144.9944
4      4       1.0     120.0   -37.8072    144.9941
6      3       2.0     245.0   -37.8024    144.9993
7      2       1.0     256.0   -37.8060    144.9954
The predictions are
[1035000. 1465000. 1600000. 1876000. 1636000.]

```













































