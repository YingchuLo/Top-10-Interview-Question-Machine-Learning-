# Top-10-Interview-Question-Machine-Learning-
## 1). What is overfitting?  / Please briefly describe what is bias vs. variance.

Overfitting: The model has tried to capture the sampling error. The model has learned the data’s signal and the noise.


### Bias vs. Variance
- Small Bias: accurate                                            

- Small variance: precise



![](https://github.com/YingchuLo/Top-10-Interview-Question-Machine-Learning-/blob/master/Screen%20Shot%202019-01-11%20at%2010.52.22%20AM.png)



### Bias and variance tradeoff



![](https://github.com/YingchuLo/Top-10-Interview-Question-Machine-Learning-/blob/master/Screen%20Shot%202019-01-11%20at%2010.54.26%20AM.png)






## 2). How do you overcome overfitting? Please list 3-5 practical experience. / What is 'Dimension Curse'? How to prevent?

- Get more data: not always possible/practical

- Subset Selection: keep only a subset of your predictors (i.e, dimensions)

- Regularization: restrict your model’s parameter space

- Dimensionality Reduction: project the data into a lower dimensional space

Dimension Curse: When the dimensionality increases, the volume of the space increases so fast that the available data become sparse.
How to prevent? Principal Component








## 3). Please briefly describe the Random Forest classifier. How did it work? Any pros and cons in practical implementation?
Random Forest Classifier could be seen as a cpmbination of several individual trees. At each tree split, a random sample of m features is drawn. For the output, if more than half of the trees predict 1 class (label 0/1), random forest predicts 1 class.

![](https://github.com/YingchuLo/Top-10-Interview-Question-Machine-Learning-/blob/master/image/Screen%20Shot%202019-01-13%20at%2012.11.01%20AM.png)

### - Pros
- One of the top performing algorithms without much tuning (easier to tune than boosting).
- Runs efficiently on large data sets: intrinsically easy to parallel.
- No feature transformation needed for nonlinear or non-monotonic features. (Logistic regression needs feature transformation).
- Automatically addresses variable interactions. (Need to construct interaction terms for logistic regression).
- Able to handle thousands of input variables without variable deletion: handles correlation and collinearity
among features well. (Logistic regression needs regularization to repress feature collinearity).
- Gives estimates of what variables are important in the classification: feature importance.
- Able to generate an internal unbiased estimate of the generalization error as the forest building progresses: OOB error.
- It has an effective method for estimating missing data and maintains accuracy when a large proportion of the data are missing.
- It has methods for balancing error in class population unbalanced data sets.
- It computes proximities between pairs of cases that can be used in clustering, locating outliers, or (by
scaling) give interesting views of the data.
### - Cons
- A good RF model needs
- Deep trees are required to lower bias
- Many trees are required to lower variance
- Relative long time to train
- Complex models (large files) to save for later use
- May still have remnant overfitting effect left
- Performance often is often beaten by Boosting
- Hard to interpret the results as compared with individual trees
## 4). Please describe the difference between GBM tree model and Random Forest.

## 5). What is SVM? what parameters you will need to tune during model training? How is different kernel changing the classification result?


## 6). Briefly rephrase PCA in your own way. How does it work? And tell some goods and bads about it.

## 7). Why doesn't logistic regression use R^2?
## 8). When will you use L1 regularization compared to L2?
## 9). List out at least 4 metrics you will use to evaluate model performance and tell the advantage for each of them. (F1 score, ROC curve, recall, etc…)
## 10). What would you do if you have > 30% missing value in an important field before building the model?

Reference:
BitTiger DS 501 Data Scientist Express Bootcamp
