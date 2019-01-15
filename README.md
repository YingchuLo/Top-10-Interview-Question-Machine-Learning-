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
How to prevent? Principal Component Analysis (PCA)








## 3). Please briefly describe the Random Forest classifier. How did it work? Any pros and cons in practical implementation?
(Reference: BitTiger DS 501 Data Scientist Express Bootcamp)

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
Maximum Margin
![](https://github.com/YingchuLo/Top-10-Interview-Question-Machine-Learning-/blob/master/image/Screen%20Shot%202019-01-13%20at%2010.15.47%20AM.png)


How to select Kernel?
(Reference: https://stats.stackexchange.com/questions/18030/how-to-select-kernel-for-svm?rq=1)

The choice of the kernel and kernel/regularisation parameters can be automated by optimising a cross-valdiation based model selection (or use the radius-margin or span bounds). The simplest thing to do is to minimise a continuous model selection criterion using the Nelder-Mead simplex method, which doesn't require gradient calculation and works well for sensible numbers of hyper-parameters. If you have more than a few hyper-parameters to tune, automated model selection is likely to result in severe over-fitting, due to the variance of the model selection criterion. It is possible to use gradient based optimization, but the performance gain is not usually worth the effort of coding it up).

Automated choice of kernels and kernel/regularization parameters is a tricky issue, as it is very easy to overfit the model selection criterion (typically cross-validation based), and you can end up with a worse model than you started with. Automated model selection also can bias performance evaluation, so make sure your performance evaluation evaluates the whole process of fitting the model (training and model selection)

## 6). Briefly rephrase PCA in your own way. How does it work? And tell some goods and bads about it.
PCA is a technique that seeks a m - dimensional basis that best captures the variance in the data.
![](https://github.com/YingchuLo/Top-10-Interview-Question-Machine-Learning-/blob/master/image/Screen%20Shot%202019-01-13%20at%204.27.52%20PM.png)

##### Reduce number of features for data understanding and modeling
- Not always a good practice, since each principal conponent contains all original variables, and interpretability of model is significantly reduced.
- Feature (in original space)selection is preferable for better interpretability purpose.

## 7). Why doesn't logistic regression use R^2?

R-squared is the result of the ANOVA decomposition,   SSTot = SSE + SSR  

where SSE is the error sum of squares, SSR is the regression sum of squares.   

Divide that equation by SSTot and the last term in the right hand side is the R-squared.

It measures the proportion of variation of the response Y explained by the regression model.


For a 0-1 variable that decomposition does not apply.  As a result, R-square do not, as well.

Logistic regression is a model where the response is a 0-1 (categorical) variable.
## 8). When will you use Lasso(L1) regularization compared to Ridge(L2)?
(Reference: Speech and Language Processing, Book by Daniel Jurafsky and James H. Martin)

### L2 > L1, get easier derivative
### L1 > L2, get fewer feature

L2 is easier to optimize because of its simple derivative (the derivative of w^2 is just 2w), while L1 is more complex (the derivative of |w| is non-continuous at zero.) But where L2 prefers weight vectors with many small weights, L1 prefers sparse solutions with some larger weights but many more weights set to zero. Thus, L1 leads to much sparser weight vectors, that is, far fewer features. 

## 9). List out at least 4 metrics you will use to evaluate model performance and tell the advantage for each of them. (F1 score, ROC curve, recall, etc…)
### Confusion Matrix

### F1-score 
### ROC(Receiver Operating Characteristic) curve

#### What's ROC?
ROC evaluate model performance based on the area under curve (AUC). Higher the PRC-AUC, better the model is at predicting 0s as 0s and 1s as 1s.

#### Advantage of ROC
No matter the original data is class balance or class imbalance, it will not change how it look like in ROC Curve.

![](https://github.com/YingchuLo/Top-10-Interview-Question-Machine-Learning-/blob/master/image/Screen%20Shot%202019-01-13%20at%205.35.44%20PM.png)

(a) is the ROC curve with class balance as shown in (b)
(c) is the ROC curve with class imbalance as shown in (d)

### PRC (Precision-Recall Curve)

#### What's PRC?
PRC is similar to ROC. Both evaluate model performance based on the area under curve (AUC). Higher the PRC-AUC, better the model is at predicting 0s as 0s and 1s as 1s. The curve of ideal model is closest to the right corner(precision=1， recall=1).
![](https://github.com/YingchuLo/Top-10-Interview-Question-Machine-Learning-/blob/master/image/Screen%20Shot%202019-01-13%20at%2011.16.46%20PM.png)

#### Advantage of PRC

## 10). What would you do if you have > 30% missing value in an important field before building the model?
(Reference: https://towardsdatascience.com/how-to-handle-missing-data-8646b18db0d4)
![](https://github.com/YingchuLo/Top-10-Interview-Question-Machine-Learning-/blob/master/image/Screen%20Shot%202019-01-15%20at%209.45.09%20AM.png)

