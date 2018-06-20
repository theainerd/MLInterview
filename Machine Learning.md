# Machine Learning Interview Questions

## Parametric vs Nonparametric ?</br>
A learning model that summarizes data with a set of parameters of fixed size (independent of the number of training examples) is called a parametric model.</br>
A learning model where the number of parameters is not determined prior to training. On the contrary, nonparametric models (can) become more and more complex with an increasing amount of data.

## Discriminative vs Generative Learning Algorithm ?</br>
Discriminative algorithms model p(y|x; w), that is, given the dataset and learned parameter, what is the probability of y belonging to a specific class. A discriminative algorithm doesn't care about how the data was generated, it simply categorizes a given example</br>

Generative algorithms model p(x|y), that is, the distribution of features given that it belongs to a certain class. A generative algorithm models how the data was generated.</br>

Given a training set, an algorithm like logistic regression or the perceptron algorithm (basically) tries to find a straight line—that is, a decision boundary—that separates the elephants and dogs. Then, to classify a new animal as either an elephant or a dog, it checks on which side of the decision boundary it falls, and makes its prediction accordingly.</br>

First, looking at elephants, we can build a model of what elephants look like. Then, looking at dogs, we can build a separate model of what dogs look like. Finally, to classify a new animal, we can match the new animal against the elephant model, and match it against the dog model, to see whether the new animal looks more like the elephants or more like the dogs we had seen in the training set.

## What is cross validation ?</br>

Cross Validation is a technique to evaluate predictive models by partitioning the original sample into a training set to train the model, and a validation set to evaluate it. For ex: K fold CV divides the data into k folds, train on each k-1 folds and evaluate it on remaining 1 fold. The result of k models can be averaged to get a overall model performance.

## What is linear regression ?</br>
_Linear Regression_ is a parametric, discriminative supervised learning algorithm to predict continuous value of  a target variable by fitting the best linear relationship between the dependent & independent variable.

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

## What is Naive Bayes ? </br>
It is a supervised learning algorithm based on bayes theorem. It classifies
different instances into predefined classes, assuming there is no interdependency of features.

## What is Support Vector Machines ? </br>
_Support Vector Machines_ is an non-parametric, discriminative supervised learning algorithm
which identifies optimal separating hyperplane which maximizes the margin between different classes of the training data.

## What is bagging ? </br>
Bagging is an ensemble technique mainly used to reduce the variance of our predictions
by combining the results of multiple classifiers modelled on different sub-samples of the same dataset. In Bagging, individual learner can be are trained in parallel.

## What is decision trees ? </br>
Decision trees are non-parametric supervised learning algorithm.
Given the training data, a decision tree algorithm divides the feature space into regions. For inference, we first see which region does the test data point fall in and take the mean label value (regression) or the majority label value ( classification )

## What is random forest ? </br>
Random forest improves bagging further by adding some randomness. In random forest, only a subset of features are selected at random to construct a tree (while often not subsample instances). The benefit is that random forest decorrelates the trees.

For example, suppose we have a dataset. There is one very predicative feature, and a couple of moderately predicative features. In bagging trees, most of the trees will use this very predicative feature in the top split, and therefore making most of the trees look similar, and highly correlated. Averaging many highly correlated results won't lead to a large reduction in variance compared with uncorrelated results. In random forest for each split we only consider a subset of the features and therefore reduce the variance even further by introducing more uncorrelated trees.

## What is boosting ? </br>
Boosting builds on weak learners, and in an iterative fashion. In each iteration, a new learner is added, while all existing learners are kept unchanged. All learners are weighted based on their performance (e.g., accuracy), and after a weak learner is added, the data are re-weighted: examples that are misclassified gain more weights, while examples that are correctly classified lose weights. Thus, future weak learners focus more on examples that previous weak learners misclassified.


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


# Unsupervised Learning
