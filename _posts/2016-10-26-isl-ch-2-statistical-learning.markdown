---
published: true
title: ISL, Ch. 2: Statistical Learning
layout: post
---
Some notes on concepts from Chapter 2 of **An Introduction to Statistical Learning**.

**Reducible error**: The estimated function F will most likely not be a perfect estimate of F, but can potentially be improved by trying another statistical learning technique (reducing bias or variance)

**Irreducible error**: In most cases, we will attempting to estimate F in a case where Y = F(x) + e, where e is irreducible error. This error may be caused by unmeasured variables that are useful in predicting Y or other sources of unmeasurable variation.

**Inference**: When interested in understanding how Y is affected when the input X changes, we are interested in estimating F not so much to predict Y as to understand the relationship between X and Y. (Which predictors are associated with the outcome? What is the relationship between the outcome and each predictor? How can the relationship between the outcome and each predictor be best described?)

**Parametric methods for estimating F**: Start by making an assumption about the shape of f. Train the model using data - provides an estimation of the parameters of the f shape we’ve selected.This approach simplifies our estimation of F because it is often simpler to estimate a set of parameters than it is to estimate an entirely unique function F. 

**Non-parametric methods for estimating F**: In this case, we’re not making explicit assumptions about the shape of F. By avoiding an assumption of a particular shape for F, there are more options for a more accurate fit. However, since estimating an entirely new function F is more complex than simply estimating parameters, more data is required for estimating F using non-parametric methods than using parametric methods.

**Accuracy/Interpretability Tradeoff**: More inflexible methods for estimating F (such as linear regression) are more interpretable. More flexible methods for estimating F (such as splines or boosting methods) may result in a more accurate prediction of outcome, but can also make it more difficult to understand how individual predictors are associated with a particular outcome.

**Supervised/Unsupervised Learning**: Supervised learning problems involve fitting a model that relates an outcome to predictors, with the aim of improving prediction or better understanding the inference model. Unsupervised learning problems occur in situations where there are observations but no associated outcome variables (we “lack a response variable that can supervise our analysis”). Tools such as cluster analysis can be used in these cases to figure out if observations can be categorized into distinct groups.

**Regression/Classification Problems**: Problems with a quantitative outcome are usually regression problems, while those with a qualitative outcome (an option of product or color, for instance) are classification problems. Not a hard and fast distinction - logistic regression is typically used on problems with a qualitative (binary) outcome.

**Mean Squared Error**: Allows us to quantify the extent to which the predicted outcome for a given observation is close to the true outcome for that observation. Found by averaging the errors for each predicted outcome. 

The MSE curve for various functions fitted to data tends to have a U shape. Minimizing MSE involves taking into account the **Bias-Variance tradeoff** for fitted functions. Variance is the amount that a predicted function changes based on the set of training data used - more flexible functions tend to have more variance. Bias is the error introduced by simplifying a complex real-life problem using a model - generally, more flexible models have less bias. As we use more flexible methods, variance will increase and bias will decrease. As we use less flexible methods, variance will decrease and bias will increase.

**K-Nearest Neighbors**: Given a positive integer K and a test observation, the KNN classifier identifies the K points in training data closest to the test observation, and estimates the conditional probability for class j as the fraction of those K points whose response values equal j. KNN applies the Bayes rule and classifies the test observation to the class with largest probability.