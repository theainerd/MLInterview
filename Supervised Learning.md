# Supervised Learning

# Table of Contents
* [Supervised Learning](#supervisedlearning)
* [Linear Regression](#linearregression)
* [Logistic Regression](#lr)
* [Multiclass Vs MultiLabel Classification](#mcml)
* [K Nearest Neighbors](#knn)
* [Naive Bayes](#nb)
* [Support Vector Machines](#svm)
* [Bagging](#bagging)
   * [Decision Trees](#decision)
   * [Random Forest](#rf)
* [Boosting](#boosting)
* [Metrics](#metrics)
## What is supervised learning? <a name="supervisedlearning"> </br>
_Supervised learning_ is where you have input data (X) and their corresponding output variables.
![](https://github.com/theainerd/MLInterview/blob/master/images/Screenshot%20from%202018-07-03%2019-25-29.png)

## What is linear regression ? <a name="linearregression"> </br>
_Linear Regression_ is a parametric, discriminative supervised learning algorithm to predict continuous values of  a target variable by fitting the best linear relationship between the dependent & independent variable.
![](https://github.com/theainerd/MLInterview/blob/master/images/maxresdefault.jpg)

## What is gradient descent ? <a name="gd"></br>
_Gradient Descent_ is a first order optimization algorithm which is used for finding the local minima of an
objective function. It starts with intial set of parameter values and iteratively moves towards a set of values that minimize the function. This iterative minimization is done by taking steps towards the negative direction of the function gradient.

![](https://github.com/theainerd/MLInterview/blob/master/images/1_7VyTVnlVj2Ooqa3MRSRFEQ.gif)

## What is logistic regression ? <a name="lr"></br>
_Logistic regression_ is a parametric, discriminative supervised learning algorithm for classification, i.e used where the response variable is categorical by applying a sigmoid function to a linear prediction.
The idea of logistic regression is to find  a relationship between features and probability of particular outcome.

![](https://github.com/theainerd/MLInterview/blob/master/images/20170513_gradient_descent_logistic_animation.gif)

## Multiclass Vs Multilabel Classification <a name = "mcml"></br>

Multiclass classification means a classification task with more than two classes; e.g., classify a set of images of fruits which may be oranges, apples, or pears. Multiclass classification makes the assumption that each sample is assigned to one and only one label: a fruit can be either an apple or a pear but not both at the same time.

Multilabel classification assigns to each sample a set of target labels. This can be thought as predicting properties of a data-point that are not mutually exclusive, such as topics that are relevant for a document. A text might be about any of religion, politics, finance or education at the same time or none of these.

## What is maximum likelihood estimation ? <a name="mle"></br>
The principle of maximum likelihood states that we should choose
parameters so as to make the data as high probability as possible. i.e we should choose parameters to maximize likelihood function.

Note : **Probability** in this mathematical context describes the plausibility of a random outcome, given a model parameter value, without reference to any observed data. **Likelihood** describes the plausibility of a model parameter value, given specific observed data.

## What is K- Nearest Neighbors ?<a name="knn"></br>
It's a non-parametric supervised learning algorithm in which we assign a label to new data based on the labels of training examples
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

## What is Naive Bayes ? <a name="nb"></br>
It is a supervised learning algorithm based on bayes theorem. It classifies
different instances into predefined classes, assuming there is no interdependency of features.

**Pros**:
- Easy and fast to predict class of test data set. Also, performs well
in multi-class prediction.

**Cons**:
- Bad estimator: Probability outputs from predict_proba are not to
be taken too seriously.

- Assumption of independent predictors: In real life, it is almost impossible that we get a set of predictors which are completely independent.

![](https://github.com/theainerd/MLInterview/blob/master/images/seashell.png)

## What is Support Vector Machines ? <a name="svm"></br>
_Support Vector Machines_ is an non-parametric, discriminative supervised learning algorithm
which identifies optimal separating hyperplane which maximizes the margin between different classes of the training data.

![](https://github.com/theainerd/MLInterview/blob/master/images/Screenshot%20from%202018-08-21%2020-53-48.png)

### Kernel Functions

Kernel methods owe their name to the use of kernel functions, which enable them to operate in a high-dimensional feature space without ever computing the coordinates of the data in that space, but rather by simply computing the inner products between the images of all pairs of data in the feature space.

**Note** : Any linear model can be turned into a non-linear model by applying the kernel trick to the model: replacing its features (predictors) by a kernel function

![](https://github.com/theainerd/MLInterview/blob/master/images/Screenshot%20from%202018-08-21%2020-56-24.png)

### Examples of SVM Kernels

* Polynomial kernel
* Gaussian radial basis function (RBF)
* Sigmoid kernel

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

## What is bagging ? <a name="bagging"> </br>
_Bagging_ is an ensemble  technique mainly used to reduce the variance of our predictions
by combining the results of multiple classifiers modelled on different sub-samples of the same dataset. In Bagging, individual learner are trained in parallel.

## What is decision trees ? <a name="decision"> </br>
Decision trees are non-parametric supervised learning algorithm.
Given the training data, a decision tree algorithm divides the feature space into regions. For inference, we first see which region does the test data point fall in and take the mean label value (regression) or the majority label value ( classification )

There are couple of algorithms there to build a decision tree , we only talk about a few which are:

CART (Classification and Regression Trees) → uses Gini Index(Classification) as metric.
ID3 (Iterative Dichotomiser 3) → uses Entropy function and Information gain as metrics.

#### Finding the variable/feature for best split.

**Gini Index**: Measure of variance across all classes of the data. Measures the impurity of the data.</br>
Ex. Given a binary classi cation problem, the number of positive
cases equals the negative ones. 
GI = 1/2*(1–1/2)+1/2*(1–1/2) = 1/2 </br>

This is maximum GI possible. As we split data, and move towards subtree, GI decreases to zero with increase in depth of tree.

**Entropy**: Measure of randomness. More the random data, higher the entropy.
E = -p*log(p) ; p - probability

**Information Gain**: Decrease in entropy. The difference between the entropy before the split and the average entropy after split is obtained to decide when to split.

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

- **Minimum Samples Split**: Minimum number of sample required to
split a node. This parameter helps in reducing over tting.
High value: Underfitting, Low value: overfitting.

- **Maximum Depth of a Tree**: Most in uential parameter. Gives limit
on vertical depth decide upto which level pruning is required.
Higher value: overfitting, Lower value: Underfitting

- **Maximum Features**: At each node, while splitting either we can
chose best feature from pool of all the features or limited number of
random features. This parameter adds a little randomness - good
generalised model.
![](https://github.com/theainerd/MLInterview/blob/master/images/image5.png)
## What is random forest ? </br> <a name="rf">
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
![](https://github.com/theainerd/MLInterview/blob/master/images/decision-forests-and-discriminant-analysis-77-638.jpg)

## What is boosting ? </br> <a name="boosting">
Boosting builds on weak learners, and in an iterative fashion. In each iteration, a new learner is added, while all existing learners are kept unchanged. All learners are weighted based on their performance (e.g., accuracy), and after a weak learner is added, the data are re-weighted: examples that are misclassified gain more weights, while examples that are correctly classified lose weights. Thus, future weak learners focus more on examples that previous weak learners misclassified.

### Types of Boosting Algorithms

* **AdaBoost (Adaptive Boosting)**
* **Gradient Tree Boosting**
* **XGBoost**

![](https://github.com/theainerd/MLInterview/blob/master/images/Screenshot%20from%202018-07-10%2016-29-57.png)

**Pros**:

- Automatically do feature engineering.
- Very little data preparation needed for algorithm.

**Cons**:

- Time and computation expensive.
- Complexity of the classiffication increases.
- Hard to implement in real time platform.


## Metrics <a name="metrics">
   
   - **Confusion Matrix**
   
     An NxN matrix where N is the no. of classes, that summarizes how successful a classification model's predictions are.
   
   - **Accuracy**</br>
     Accuracy is the fraction of predictions our model got right.</br>
     Suppose you build a model that classified 100 tumors as malignant (the positive class) or benign (the negative class):
     ![](https://github.com/theainerd/MLInterview/blob/master/images/Screenshot%20from%202018-07-09%2009-40-16.png)
     
  - **Recall or Sensitivity or True Positive Rate**</br>
    ![](https://github.com/theainerd/MLInterview/blob/master/images/Precisionrecall.svg.png)
    
    Number of items correctly identified as positive out of total true positives. High recall means you’re not missing many positives.
    ![](https://github.com/theainerd/MLInterview/blob/master/images/Screenshot%20from%202018-07-09%2009-47-10.png)
    Our model has a recall of 0.11—in other words, it correctly identifies 11% of all malignant tumors.

  - **Precision** </br>
    Number of items correctly identified as positive out of total items identified as positive. High precision means low “false alarm rate” (if you test positive, you’re probably positive)
    ![](https://github.com/theainerd/MLInterview/blob/master/images/Screenshot%20from%202018-07-09%2009-46-53.png)
    Our model has a precision of 0.5—in other words, when it predicts a tumor is malignant, it is correct 50% of the time.
  - **True Negative Rate or Specificity**</br>
    Number of items correctly identified as negative out of total true negatives.

  - **Type 1 Error or False Positive Rate or false alarm rate** </br>
    Number of items wrongly identified as positive out of total true negatives.

  - **Type 2 Error or False Negative Rate or miss rate** </br>
    Number of items wrongly identified as negative out of total
    true positives.
    
   - **RMSE (Root Mean Square Error)**</br>
    It represents the sample standard deviation of the differences between predicted values and observed values (called residuals).
    
   - **MAE**</br>
   MAE is the average of the absolute difference between the predicted values and observed value. 
    
   - **R Squared (R²) and Adjusted R Squared**
    
   - R Squared & Adjusted R Squared (_goodness of fit measure_) are often used for explanatory purposes and explains how well your selected independent      variable(s) explain the variability in your dependent variable(s).</br>
   **Note** : Higher the MSE, smaller the R_squared and poorer is the model.</br>
   Just like R², adjusted R² also shows how well terms fit a curve or line but adjusts for the number of terms in a model.
   **Note** : The more predictors you add the higher R^2 become hence use adjusted R^2 which adjusts for the degrees of freedom.</br> 
   ![](https://github.com/theainerd/MLInterview/blob/master/images/Adjusted_R2.png_large)

## Explain how a ROC curve works?<br>

The **ROC curve** is a graphical representation of the contrast between true positive rates and the false positive rate at various thresholds.</br>
It’s often used as a proxy for the trade-off between the sensitivity of the model (true positives) vs the fall-out or the probability it will trigger a false alarm (false positives).

AUC ROC = area under the ROC curve.

![](https://github.com/theainerd/MLInterview/blob/master/images/Screenshot%20from%202018-07-09%2009-27-32.png)
