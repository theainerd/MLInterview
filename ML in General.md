## Parametric vs Nonparametric ?</br>
A learning model that summarizes data with a set of parameters of fixed size (independent of the number of training examples) is called a **parametric model**.</br>
A learning model where the number of parameters is not determined prior to training. On the contrary, nonparametric models (can) become more and more complex with an increasing amount of data.

## Discriminative vs Generative Learning Algorithm ?</br>
**Discriminative algorithms model p(y|x; w)**, that is, given the dataset and learned parameter, what is the probability of y belonging to a specific class. A discriminative algorithm doesn't care about how the data was generated, it simply categorizes a given example</br>

**Generative algorithms model p(x|y)**, that is, the distribution of features given that it belongs to a certain class. A generative algorithm models how the data was generated.</br>

Given a training set, an algorithm like logistic regression or the perceptron algorithm (basically) tries to find a straight line—that is, a decision boundary—that separates the elephants and dogs. Then, to classify a new animal as either an elephant or a dog, it checks on which side of the decision boundary it falls, and makes its prediction accordingly.</br>

First, looking at elephants, we can build a model of what elephants look like. Then, looking at dogs, we can build a separate model of what dogs look like. Finally, to classify a new animal, we can match the new animal against the elephant model, and match it against the dog model, to see whether the new animal looks more like the elephants or more like the dogs we had seen in the training set.

## What is cross validation ?</br>

Cross Validation is a technique to evaluate predictive models by partitioning the original sample into a training set to train the model, and a validation set to evaluate it. For ex: K fold CV divides the data into k folds, train on each k-1 folds and evaluate it on remaining 1 fold. The result of k models can be averaged to get a overall model performance.

## What is overfitting?

Overfitting or High Variance is a modeling error which is caused by a hypothesis function that fits the training data
but does not generalise well to predict new data.

## What is regularization?

Regulariztion is a technique to prevent overfitting by penalizing the coefficients of the cost function.

  ### Ridge Regression
  It performs ‘L2 regularization’, i.e. adds penalty equivalent to square of the magnitude of coefficients. Thus, it optimises the following:

    Objective = RSS + α * (sum of square of coefficients)

  ### Lasso Regression
  LASSO stands for Least Absolute Shrinkage and Selection Operator.Lasso regression performs L1 regularization, i.e. it adds a factor of sum of absolute value of coefficients in the optimisation objective.

      Objective = RSS + α * (sum of square of coefficients)

  ### Elastic nets
  A technique known as Elastic Nets, which is a combination of Lasso
  and Ridge regression is used to tackle the limitations of both Ridge and
  Lasso Regression.

## How do you handle missing or corrupted data in a dataset?
Before jumping to the methods of data imputation, we have to understand the reason why data goes missing.

  - **Missing at Random (MAR)**: Missing at random means that the propensity for a data point to be missing is not related to the missing data, but it is related to some of the observed data.
  - **Missing Completely at Random (MCAR)**: The fact that a certain value is missing has nothing to do with its hypothetical         value and with the values of other variables.
  - **Missing not at Random (MNAR)**: Two possible reasons are that the missing value depends on the hypothetical value (e.g.         People with high salaries generally do not want to reveal their incomes in surveys) or missing value is dependent on some other variable’s value (e.g. Let’s assume that females generally don’t want to reveal their ages! Here the missing value in age variable is impacted by gender variable).
  


## How would you handle an imbalanced dataset?
* Using a better metrics like AUROC, Precision, Recall etc.
* Cost-sensitive Learning
* Over sampling of the minority class or Under sampling of the minority class.
* SMOTE
* Anomaly Detection

## how do you detect outliers?
