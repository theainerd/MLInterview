# Machine Learning Interview Questions

## What is supervised learning? </br>
_Supervised learning_ is where you have input data (X) and their corresponding output variables.
![](https://github.com/theainerd/MLInterview/blob/master/images/Screenshot%20from%202018-07-03%2019-25-29.png)

## What is linear regression ?</br>
_Linear Regression_ is a parametric, discriminative supervised learning algorithm to predict continuous values of  a target variable by fitting the best linear relationship between the dependent & independent variable.
![](https://github.com/theainerd/MLInterview/blob/master/images/maxresdefault.jpg)

## What is gradient descent ?</br>
_Gradient Descent_ is an optimization algorithm that starts with intial set of parameter values and iteratively moves towards a set of values that minimize the function. This iterative minimization is done by taking steps towards the negative direction of the function gradient.

## What is logistic regression ?</br>
_Logistic regression_ is a parametric, discriminative supervised learning algorithm for classification, i.e used where the response variable is categorical.
The idea of logistic regression is to find  a relationship between features and probability of particular outcome.

## What is maximum likelihood estimation ?</br>
The principle of maximum likelihood states that we should choose
parameters so as to make the data as high probability as possible. i.e we should choose parameters to maximize likelihood function.

## What is K- Nearest Neighbors ?</br>
It's a classification algorithm in which we assign a label to new data based on the labels of training examples
which are most near to it. It's a lazy learning technique because it goes through complete training data everytime it needs to predict a test sample.

  - Distance Metric
        - Euclidean distance
        - Manhattan distance
        
 

## How is KNN different from k-means clustering ?</br>
K-Nearest Neighbors is a supervised classication algorithm, while k-means clustering is an unsupervised clustering algorithm. In order for K-Nearest Neighbors to work, you need labeled data you
want to classify an unlabeled point into (thus the nearest neighbor part).
K-means clustering requires only a set of unlabeled points and a
threshold: the algorithm will take unlabeled points and gradually learn how to cluster them into groups by computing the mean of the
distance between different points.

The critical difference here is that KNN needs labeled points and is thus supervised learning, while k-means doesn’t — and is thus
unsupervised learning.

## What is Naive Bayes ? </br>
It is a supervised learning algorithm based on bayes theorem. It classifies
different instances into predefined classes, assuming there is no interdependency of features.

**Pros**:
- Easy and fast to predict class of test data set. Also, performs well
in multi-class prediction.

**Cons**:
- Bad estimator: Probability outputs from predict_proba are not to
be taken too seriously.

- Assumption of independent predictors: In real life, it is almost
impossible that we get a set of predictors which are completely
independent.

## What is Support Vector Machines ? </br>
_Support Vector Machines_ is an non-parametric, discriminative supervised learning algorithm
which identifies optimal separating hyperplane which maximizes the margin between different classes of the training data.

**Pros**:

- It is really effective in higher dimension. If you have more features
than training examples, most of the algorithms perform very bad,
but SVM is the only algorithm which can saves you in this
situation.
- Best algorithm if you data are separable. That two classes are not
mixed.
- Only support vectors affect the optimally spaced hyperplane. So, it
is less affected by outliers.

**Cons**:

- On large dataset it takes too much time. Mainly because of kernel
function calculations and finding optimal hyperplane in higher
dimensions.
- Can not perform well in case of overlapping classes.
- Can only give you 0–1 classification. Probably estimates
computation are really expensive.

## What is bagging ? </br>
_Bagging_ is an ensemble technique mainly used to reduce the variance of our predictions
by combining the results of multiple classifiers modelled on different sub-samples of the same dataset. In Bagging, individual learner are trained in parallel.

## What is decision trees ? </br>
Decision trees are non-parametric supervised learning algorithm.
Given the training data, a decision tree algorithm divides the feature space into regions. For inference, we first see which region does the test data point fall in and take the mean label value (regression) or the majority label value ( classification )

#### Finding the variable/feature for best split.

**Gini Index**: Measure of variance across all classes of the data. Measures the impurity of the data.</br>
Ex. Given a binary classi cation problem, the number of positive
cases equals the negative ones. GI = 1/2*(1–1/2)+1/2*(1–1/2)
= 1/2 </br>

This is maximum GI possible. As we split data, and move towards
subtree, GI decreases to zero with increase in depth of tree.

**Entropy**: Measure of randomness. More the random data, higher the entropy.
E = -p*log(p) ; p - probability

**Information Gain**: Decrease in entropy. The di erence between the
entropy before the split and the average entropy after split is obtained
to decide when to split.

The variable which provides maximum entropy gain is chosen!

**Pros**:
- Easy to understand and visualise.
- Can be used for feature engineering.
- Very little data preparation needed for algorithm.

**Cons**:
- If not tuned well, may lead to overfitting.
- Unstable. Small variation in data leads to completely different tree
formation.
- In case of imbalanced dataset, decision trees are biased.However,
by using proper splitting criteria, this issue can be resolved.

**Important Parameters**:

- *Minimum Samples Split*: Minimum number of sample required to
split a node. This parameter helps in reducing over tting.
High value: Underfitting, Low value: overfitting.

- *Maximum Depth of a Tree*: Most in uential parameter. Gives limit
on vertical depth decide upto which level pruning is required.
Higher value: overfitting, Lower value: Underfitting

- *Maximum Features*: At each node, while splitting either we can
chose best feature from pool of all the features or limited number of
random features. This parameter adds a little randomness - good
generalised model.

## What is random forest ? </br>
Random forest improves bagging further by adding some randomness. In random forest, only a subset of features are selected at random to construct a tree (while often not subsample instances). The benefit is that random forest decorrelates the trees.

For example, suppose we have a dataset. There is one very predicative feature, and a couple of moderately predicative features. In bagging trees, most of the trees will use this very predicative feature in the top split, and therefore making most of the trees look similar, and highly correlated. Averaging many highly correlated results won't lead to a large reduction in variance compared with uncorrelated results. In random forest for each split we only consider a subset of the features and therefore reduce the variance even further by introducing more uncorrelated trees.

**Pros**:
- As it predicts by aggregating the predictions from smaller
predictors the variance decreases. Less overfitting.
- Useful when missing data is huge.

**Cons**:
- Better with classification than regression.
- Black box approach: Many factors are random.
- Slight increase in Bias

**Parameters**:
- **n_estimators**: Number of trees in the model. The larger the better,
but the longer it will take to compute.

- **max_features**: Size of the random subsets of features to consider
when splitting a node. Lower the #features, greater the reduction
in variance, but greater the increase in bias.

- **feature_importances_**: The relative importances of each feature
to the model. Features used in the tree at the top nodes are
relatively more important as more data points are dependent on
that feature.


## What is boosting ? </br>
Boosting builds on weak learners, and in an iterative fashion. In each iteration, a new learner is added, while all existing learners are kept unchanged. All learners are weighted based on their performance (e.g., accuracy), and after a weak learner is added, the data are re-weighted: examples that are misclassified gain more weights, while examples that are correctly classified lose weights. Thus, future weak learners focus more on examples that previous weak learners misclassified.

**Pros**:

- Automatically do feature engineering.
- Very little data preparation needed for algorithm.

**Cons**:

- Time and computation expensive.
- Complexity of the classi cation increases.
- Hard to implement in real time platform.


## Metrics

  - **Recall or Sensitivity or True Positive Rate**</br>
    Number of items correctly identified as positive out of total true positives.

  - **Precision** </br>
    Number of items correctly identified as positive out of total items identified as positive.

  - **Specificity**</br>
    Number of items correctly identified as negative out of total true negatives.

  - **Type 1 Error or False Positive Rate** </br>
    Number of items wrongly identified as positive out of total true negatives.

  - **Type 2 Error or False Negative Rate** </br>
    Number of items wrongly identified as negative out of total
    true positives.

## Explain how a ROC curve works?<br>
The **ROC curve** is a graphical representation of the contrast between true positive rates and the false positive rate at various thresholds.</br>
It’s often used as a proxy for the trade-off between the sensitivity of the model (true positives) vs the fall-out or the probability it will trigger a false alarm (false positives).

![](https://github.com/theainerd/MLInterview/blob/master/images/roc.gif)
