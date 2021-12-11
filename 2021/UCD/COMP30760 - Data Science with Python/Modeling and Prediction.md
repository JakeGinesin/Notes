###### tags: `COMP30760 - Data Science with Python`

# Modeling and Prediction

## Modeling and Prediction Tasks
- Predictive modelling uses statistics to predict outcomes, based on historic data. Also referred to as supervised machine learning
- Examples:
    - Spam filtering: predict if a new email is spam or non-span based on annotated examples of past spam/non-spam
    - Car insurance: assign risk of accidents to policy holdeers and potential customers
    - Healthcare: preict disease which a patient has, based on their symptoms
    - Algorithmic trading: predictive models can be built for different assets like stocks, futures, currencies, etc, based on histric data nad company information

## Supervised Learning
- Classification: Learn from a labeled training set to make a prediction to assign a new "unseen" example to one of a fixed number of classes
- Regression: Learn from an existing training set to decide the value of a continuous output variable (i.e. the output is a number)

## Scikit-Learn Package
- Scikit-learn is a comrehensive open source python package for machine learning and ata analysis
- Anaconda includes scikit-learn as a part of its free distribution

## Finding Patterns in Data
- When analysing anew dataset, as a first setep we might visualize the data to identify any obvious patterns
- Example: Dataset of 244 meals, with details of total meal bill and tip amount. What can we say about the data?

## Anscombe's Quartet
- 4 datasets with nearly identical statistical properties. Yet, each expresses quite different relationships between Y and X.
- important to look at the data visually before building a model

## Correlation
- Visualising data using scatter plots can provide us with a sense of the relationship between two variables
- Relationships can have different directions (positive and negative) and different strengths (weak or strong)
- How can we quantify this numerically?

## Correlation In Python
- Often useful to know the strenght of relationship between Y and X, but independent of the units of measurement
- The correlation between Y and X is a statistical measure of how strongly two cariables are related. It is dimensionless, i.e. a unit-free measure of the relationship between variables
- Takes a value in [-1, +1], where 1 is total postive correlation, 0 is no correlation, -1 is total negative correlation
- If our data is stored in a Pandas Data Frame, we can also use the ``df.corr()`` function

## Correlation vs Causation
- Causation: indicates that one event is the result of the occurance of the other event - i.e. there is a causal relationship between the two events
- But a correlation between variables does not automatically mean that the change in one variable is the cause of the change in values of the other variable

## Regession:
- Regression analysis: A common statistical process for estimating the relationships between variables. This can allow us to make numeric predictions based on past data

## Linear Regression
- Linear Regression: a simple approach to predictive modelling It assumes that the dependence of a response (dependent) variable Y on input (independent) variables X1, X2, .. is linear.

## Simple Linear Regression
- Simple Linear Regression: Method for predicting a numeric response using a single input variable
- Goal is to learn the model coefficients from existing data
- Once we have learned the model, we can make future predictions
- We learn the model by finding the best line (coefficients) which minimises the squared distance between our examples and the line

## Multiple Regression
- Multiple linear regression: Simple linear regression can easily be extended to include multiple features, where we try to learn a model: `y=Bo + B1X1 + B2X2 + ...`
- Each feature Xi hs its own coefficient Bi

