###### tags: `COMP30760 - Data Science with Python`

# Classification
- Binary Classificaiton: Assign input examples into one of two different classes
- Multivlass classification: Assign input examples into one of three or more different classes

## Binary Classificiton
- BInary classification tasks typiclly invovle one class nthat represents the state ofinterest (the posiitve class) and one clas swhich represents the "normal" state


## Multiclass Classification
- In other cases, we want to train an algorithm to learn to automatically classify a new input into one of 3+ different classes

## Training Data
- Classificaiton Algorithms rely on a set of examples fo reach of the relevant classes - i.e. a training set 

## Classification Algorithms
- Many different leanring algorithms exist for classifiction (k-nearst neighbour, decision tree, neural network, support vector machine)
- Problem dimensions will often determine which clssificiton algorithm will be practically applicable, due to processing, memory, and astorage requirements
    - Numbers of examples N
    - Numbers of features (dimensions) D representing each example
    - Number of target classes M
    - Certain types of models perofmr will empirically for certain domains

## Similarity/Distance-based Algorithms

**Fundamental Strategy*: "Best way to make predictionsis to look at past examples and repeat the same process again"*

*Feature Space*: A D-dimensional coordinate space used to represent the input example for a given proble, wiht one coordinate per descriptive feature

*Similarity measure*: Some function to measure how similar (or distant) two input examples are from one another are in the D_dimensional coordinate space. 

- For numerica data, te most common distane function used is the *Euclidean distance*
- Calculated as the square root of the sum of square ddifferneces for each feature *f* represneting a pair of examples

$$
ED(p, q) = \sqrt{\sum_{i=1}^{n}(q_i-p_i)^2}
$$

## KNN Classifier
k-Nearest Neighbour Classifier: imple but effective "lazy" classifier. Find most similar previous examples fo rwhich a decision has already been made (i.e. their nearest neighbours from the training set).

*Mjaority Voting*: The predicted label for a new input example Z is decided based on the "votes" of its *k* nearest neighbours, where the neighbours are selected to minimie the distance (d(q, x_i))

## KNN Classifier in Python
- Scikit-learn includes a range of classification algorithms. In all cases, we call `fit()` to bui;ld a model on training data, then we call `predict()` to predict class labels for new inputs
- Step 1: fit a KNN classifier with K=3 neighbours on the full dataset
    - this is our training data, using the `fit()` function
```python=
from sklearn.neighbors import KNeighborsClassifier
model = KNeighborsClassifier(N_neighbors=3)
model.fit(data, target)
```
- Step 2: Make a prediction for a new input using the trainined KNN mode, using the predict function

## Decision Tree Classifier 
- Create a classification model to predict class labels by learning decision rules learned from trianing data
- **Basic Idea**: Build a tree model that splits the trainng set into subsets in which all examples have the same class
- Splitting is done using rules inferred from the training set.
- Each rule is based on a feature, and the split corresponds to the values it can take:
    - e.g. insured = {true, false}
    - e.g. wind = {weak, strong}
    - e.g. income = {low, average, high}
    - e.g. height < 6ft, height > 6ft

## Evaluating Classifiers
- A key aspect of applying classificaiton invovles quantitatively assessing how well an algorithm is performing at the task at hand
- Stanard evaluation approach for classification tasks is to split the complete original set of annotated examples into two distinct sets
    - Training set: Set of examples provided to the classifer to build a model of the data. Each has been assigned a class label.
    - Test set: Separate set of examples which are used to evaluate the formance of the classifier

**Hold-out Strategy**: A common approach for generating training and test sets is to take the complet edataset and randomly "hold back" some examples (e.g. 20%) in the test set for evaluation

- We can use the `train_teset_split()` function to randomly split a dataset (and its associated class labels) into two distinct training and test sets for evaluation purposes

## Overfitting
- Q. Why not just use all the original data to build our model?
- For real-world taasks, we are interested in the generalisation accuracy of a classification system
- Overfitting: Model is fitted too cloesly to the traiing data (including its noise). The model cannot generalise to situations not presented during trainnig, so it is not useful when applied to unseen data

## Evaluation Measures
- When making predictions, we need some kind of measure to cature how oftne the model amkes coret or incorrect predictions, and how severe the mistakes are
- Accuracy: Simplist measure, fraction of correct predictions made by the classifier
