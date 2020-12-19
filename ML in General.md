# Table of Contents
* [Types of Artificial Intelligence Learning Models](#aimodels)
  * [Knowledge-Based Classification](#kbc)
  * [Feedback-Based Classification](#fbc)
* [Data Mining Vs Machine Learning](#mlvsdm)
* [Workflow of Machine Learning Project](#workflow)
* [Parametric vs Nonparametric](#tric)
* [Discriminative vs Generative Learning Algorithm](#dam)
* [Cross Validation](#cv)
* [Overfitting](#of)
* [Regularization](#reg)
* [Loss Functions for Regression and Classification](#lossfun)
* [Handle missing or Corrupted data](#missing)
* [Imbalanced Datasets](#imb)
* [Outliers](#out)

## Types of Artificial Intelligence Learning Models  <a name="aimodels"> </br>

### AI Learning Models: Knowledge-Based Classification  <a name="kbc"> </br>
- **Inductive Learning**: This type of AI learning model is based on inferring a general rule from datasets of input-output pairs.
- **Deductive Learning**:  This type of AI learning technique starts with a series of rules and infers new rules that are more efficient in the context of a specific AI algorithm.

### AI Learning Models: Feedback-Based Classification <a name="fbc"> </br>

Based on the feedback characteristics, AI learning models can be classified as supervised, unsupervised, semi-supervised or reinforced.

—  **Unsupervised Learning**: Unsupervised models focus on learning a pattern in the input data without any external feedback. Clustering is a classic example of unsupervised learning models.

—  **Supervised Learning**: Supervised learning models use external feedback to learning functions that map inputs to output observations. In those models the external environment acts as a “teacher” of the AI algorithms.

—  **Semi-supervised Learning**: Semi-supervised learning is a class of supervised learning tasks and techniques that also make use of unlabeled data for training – typically a small amount of labeled data with a large amount of unlabeled data.
The goal of a semi-supervised model is to classify some of the unlabeled data using the labeled information set.

—  **Reinforcement Learning**: Reinforcement learning models use opposite dynamics such as rewards and punishment to “reinforce” different types of knowledge. This type of learning technique is becoming really popular in modern AI solutions.

## Data Mining Vs Machine Learning <a name="mlvsdm"></br>

**Machine learning** focuses on prediction, based on known properties learned from the training data.</br>
**Data mining** focuses on the discovery of (previously) unknown properties in the data. This is the analysis step of Knowledge Discovery in Databases.

**Note** : If you have a better explanation a pull request would be helpful.

## Workflow of Data Science Project <a name="workflow"></br>

Given a data science / machine learning project, what steps should we follow? Here's how we should tackle it:

* **Specify business objective.** Are we trying to win more customers, achieve higher satisfaction, or gain more revenues?
* **Define problem.** What is the specific gap in your ideal world and the real one that requires machine learning to fill? Ask questions that can be addressed using your data and predictive modeling (ML algorithms).
* **Create a common sense baseline.** But before you resort to ML, set up a baseline to solve the problem as if you know zero data science. You may be amazed at how effective this baseline is. It can be as simple as recommending the top N popular items or other rule-based logic. This baseline can also server as a good benchmark for ML algorithms.
* **Review ML literatures.** To avoid reinventing the wheel and get inspired on what techniques / algorithms are good at addressing the questions using our data.
* **Set up a single-number metric.** What it means to be successful - high accuracy, lower error, or bigger AUC - and how do you measure it? The metric has to align with high-level goals, most often the success of your business. Set up a single-number against which all models are measured.
* **Do exploratory data analysis (EDA).** Play with the data to get a general idea of data type, distribution, variable correlation, facets etc. This step would involve a lot of plotting.
* **Partition data.** Validation set should be large enough to detect differences between the models you are training; test set should be large enough to indicate the overall performance of the final model; training set, needless to say, the larger the merrier.
* **Preprocess.** This would include data integration, cleaning, transformation, reduction, discretization and more.
* **Engineer features.** Coming up with features is difficult, time-consuming, requires expert knowledge. Applied machine learning is basically feature engineering. This step usually involves feature selection and creation, using domain knowledge. Can be minimal for deep learning projects.
* **Develop models.** Choose which algorithm to use, what hyperparameters to tune, which architecture to use etc.
* **Ensemble.** Ensemble can usually boost performance, depending on the correlations of the models/features. So it’s always a good idea to try out. But be open-minded about making tradeoff - some ensemble are too complex/slow to put into production.
* **Deploy model.** Deploy models into production for inference.
* **Monitor model.** Monitor model performance, and collect feedbacks.
* **Iterate.** Iterate the previous steps. Data science tends to be an iterative process, with new and improved models being developed over time.

![](https://github.com/theainerd/MLInterview/blob/master/images/workflow.png)

## Parametric vs Nonparametric ?</br> <a name="tric"></br>
A learning model that summarizes data with a set of parameters of fixed size (independent of the number of training examples) is called a **parametric model**.</br>
A learning model where the number of parameters is not determined prior to training. On the contrary, nonparametric models (can) become more and more complex with an increasing amount of data.

## Discriminative vs Generative Learning Algorithm ?</br> <a name="dam"></br>
**Discriminative algorithms model p(y|x; w)**, that is, given the dataset and learned parameter, what is the probability of y belonging to a specific class. A discriminative algorithm doesn't care about how the data was generated, it simply categorizes a given example</br>
Ex: Linear Regression, Logistic Regression, Support Vector Machines etc.

**Generative algorithms model p(x|y)**, that is, the distribution of features given that it belongs to a certain class. A generative algorithm models how the data was generated.</br>
Ex: Naive Bayes, Hidden Markov Models etc.</br>

![](https://github.com/theainerd/MLInterview/blob/master/images/Screenshot%20from%202018-08-21%2020-22-44.png)

Given a training set, an algorithm like logistic regression or the perceptron algorithm (basically) tries to find a straight line—that is, a decision boundary—that separates the elephants and dogs. Then, to classify a new animal as either an elephant or a dog, it checks on which side of the decision boundary it falls, and makes its prediction accordingly.</br>

First, looking at elephants, we can build a model of what elephants look like. Then, looking at dogs, we can build a separate model of what dogs look like. Finally, to classify a new animal, we can match the new animal against the elephant model, and match it against the dog model, to see whether the new animal looks more like the elephants or more like the dogs we had seen in the training set.

## What is cross validation ?</br> <a name="cv"></br>

Cross Validation is a technique to evaluate predictive models by partitioning the original sample into a training set to train the model, and a validation set to evaluate it. For ex: K fold CV divides the data into k folds, train on each k-1 folds and evaluate it on remaining 1 fold. The result of k models can be averaged to get a overall model performance.

![](https://github.com/theainerd/MLInterview/blob/master/images/10_fold_cv.png)

**Time - Series Cross Validation** :  Experimenters cannot cut out a piece in the middle, and train on data before and after this portion. Instead, they need to train on a set of data that is older than the test data.</br>
![](https://github.com/theainerd/MLInterview/blob/master/images/image6-e1536165830511.png)

With this in mind, there are two major approaches, outlined in Figure, above: the **sliding window** approach and the **expanding window** approach. In the sliding window approach, one uses a fixed size window, shown here in black, for training. Subsequently, the method is tested against the data shown in orange.

## What is overfitting? <a name="of"></br>

Overfitting or High Variance is a modeling error which is caused by a hypothesis function that fits the training data too close but does not generalise well to predict new data.
![](https://github.com/theainerd/MLInterview/blob/master/images/partitions-underfitting-vs-overfitting-regression-via-polynomial-degree.png)

## What is regularization? <a name="reg"></br>

Regulariztion is a technique to prevent overfitting by penalizing the coefficients of the cost function.

  ### Ridge Regression
  It performs ‘L2 regularization’, i.e. adds penalty equivalent to square of the magnitude of coefficients.
  `L 2 regularizer` is also called a gaussian prior or weight decay .
  Thus, it optimises the following:

    Objective = RSS + α * (sum of square of coefficients)

  ### Lasso Regression
  LASSO stands for Least Absolute Shrinkage and Selection Operator.Lasso regression performs L1 regularization, i.e. it adds a factor of sum of absolute value of coefficients in the optimisation objective.

      Objective = RSS + α * (sum of absolute value of coefficients)

  ### Elastic nets
  A technique known as Elastic Nets, which is a combination of Lasso
  and Ridge regression is used to tackle the limitations of both Ridge and
  Lasso Regression.
  
  
## Loss Functions for Regression and Classification? <a name="lossfun"></br>

* **Regression Loss Function**
    * Square or l2 loss (not robust)
    * Absolute or Laplace loss (not differentiable)
    * Huber Loss (robust and differentiable)
* **Classification Loss Function**
    * SVM/Hinge loss
    * log loss
    
    ![](https://github.com/theainerd/MLInterview/blob/master/images/Screenshot%20from%202018-08-21%2020-24-08.png)

## How do you handle missing or corrupted data in a dataset? <a name="missing"></br>
Before jumping to the methods of data imputation, we have to understand the reason why data goes missing.

  - **Missing Completely at Random (MCAR)**: The fact that a certain value is missing has nothing to do with its hypothetical         value and with the values of other variables.
  
  - **Missing at Random (MAR) - a weaker assumption than MCAR**: Missing at random means that the propensity for a data point to be missing is not related to the missing data, but it is related to some of the observed data.</br>
  
 - **Missing not at Random (MNAR)**: Two possible reasons are that the missing value depends on the hypothetical value (e.g.         People with high salaries generally do not want to reveal their incomes in surveys) or missing value is dependent on some other variable’s value (e.g. Let’s assume that females generally don’t want to reveal their ages! Here the missing value in age variable is impacted by gender variable).
 
  Methods :
  
  * **Listwise Deletion** : In the listwise deletion method, all rows that have one or more column values missing are deleted.
  
  * **Mean, Median and Mode Imputation**: In the mean/median/mode imputation method, all missing values in a particular column are substituted with the mean/median/mode, which is calculated using all the values available in that column.
  
  * Multiple Imputation
  * Last Observation Carried Forward (LOCF)**
  * KNN (K Nearest Neighbors)

## How would you handle an imbalanced dataset? <a name="imb"></br>
* Using a better metrics like AUROC, Precision, Recall etc.
* Cost-sensitive Learning
* Over sampling of the minority class or Under sampling of the majority class.
* SMOTE (Synthetic Minority Over-sampling Technique.)
* Anomaly Detection

![](https://github.com/theainerd/MLInterview/blob/master/images/Screenshot%20from%202018-09-21%2009-20-55.png)

## how do you detect outliers? <a name="out"></br>

Outliers are extreme values that deviate from other observations on data , they may indicate a variability in a measurement, experimental errors or a novelty.

### How to find outliers 
* Visualize the Data</br>
 * **Histogram**: A histogram is the best way to check univariate data — data containing a single variable — for outliers
 * **Scatter Plot**: A scatter plot is useful to find outliers in bivariate data (data with two variables). You can easily spot the outliers because they will be far away from the majority of points on the scatter plot.
 * **Box Plots**
 * incomplete

