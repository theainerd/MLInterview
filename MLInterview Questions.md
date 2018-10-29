# Machine Learning Interview Questions

## Cross Entropy or Log Loss

Cross-entropy is commonly used to quantify the difference between two probability distributions.</br>
Cross-entropy loss measures how close is the predicted distribution to the true distribution.

![](https://github.com/theainerd/MLInterview/blob/master/images/Screenshot%20from%202018-08-12%2009-28-06.png)

Why the Negative Sign? </br>
Log Loss uses negative log to provide an easy metric for comparison. It takes this approach because the positive log of numbers < 1 returns negative values, which is confusing to work with when comparing the performance of two models.

## Explain Bias Variance Trade of in Machine Learning

https://machinelearningmastery.com/gentle-introduction-to-the-bias-variance-trade-off-in-machine-learning/

Quick Summary:-

Bias is the simplifying assumptions made by the model to make the target function easier to approximate.

Variance is the amount that the estimate of the target function will change given different training data.

Trade-off is tension between the error introduced by the bias and the variance.
