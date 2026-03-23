**Q0.** Please answer the following questions in your own words.

1. What makes a model "linear"? "Linear" in what?

**A model is considered linear in its parameters the prediction is a weighted sum of the inputs, where each coefficient enters as a simple multiplier.**

2. How do you interpret the coefficient for a dummy/one-hot-encoded variable? (This is a trick question, and the trick involves how you handle the intercept of the model.) There's further explanation at the end of this document, if needed.

**You can interpret the coefficient as the difference in predicted outcome compared to the omitted category, which becomes the baseline absorbed into the intercept. You drop one dummy to avoid perfect collinearity with the intercept. This is also described below as dummy variable trap. So in simple terms the coefficient on a dummy variable represents the expected difference in the outcome between that category and the omitted reference category, holding all other variables constant.**

3. Can linear regression be used for classification? Explain why, or why not.

**Yes, linear regression can be used for classification by predicting a value and applying a cutoff (like 0.5). However, it’s not ideal because predictions can fall outside 0 and 1, and it doesn’t model probabilities well. That’s why models like logistic regression are usually preferred for classification.**

4. If you have a high accuracy on training but low on testing, what might be the problem? It also might be you see a pattern in the residuals.

**The model is learning the training data too well, so it doesn’t generalize to new data, which is why test accuracy is low. This is also called overfitting. And if we see a pattern in the residuals then that suggests that the model isn't capturing the true relationship.**

5. Review this page: [Non-Linear with Linear](https://inria.github.io/scikit-learn-mooc/python_scripts/linear_regression_non_linear_link.html) What are two ways to incorporate nonlinear relationships between your target/response/dependent/outcome variable $y$ and your features/control/response/independent variables $x$?

**2 ways to incorporate nonlinear relationships between your target/response/dependent/outcome variable $y$ and your features/control/response/independent variables $x$ are creating new features derived from original features using expert knowledge. For example using polynomials of the features. Another way is by using "Kernel" where weights are assigned to samples and not every sample is used, some redundant data points of the training set are assigned a weight of 0 so that they do no influence the model’s prediction function. This is the intuition to the "Support vector Machines".**

6. What is the interpretation of the intercept? A slope coefficient for a variable? The coefficient for a dummy/one-hot-encoded variable?

**Interpretation of the intercept: When all variables are 0, the model predicts the outcome to be Beta0.**

**Interpretation of the Slope coefficient for a variable: If this variable increases by one unit, the predicted outcome changes by Beta1, holding all other variables constant.**

**Interpretation of the coefficient for dummy/one-hot-encoding variable: Being in this category changes the predicted outcome by Beta, holding all other variables constant.**