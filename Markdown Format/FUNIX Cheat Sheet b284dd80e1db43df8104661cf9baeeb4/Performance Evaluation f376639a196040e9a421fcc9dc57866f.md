# Performance Evaluation

Created: Feb 13, 2021 11:50 AM
Created By: Khanh Vương
Last Edited By: Khanh Vương
Last Edited Time: Feb 13, 2021 4:31 PM
Module: Regression
Status: Archived
Type: Regression Problem

# How can we denote the Loss Function ?

                                                           $L(y, f_w(w))$

- Usually, the **Loss Function** can use
    - **Absolute Error:** $L(y, f_w(w)) = |y - f_w(w)|$
    - **Squared Error:** $L(y, f_w(w)) = (y - f_w(w))^2$
- **Squared Error** approach will lead to extremely high cost if the difference is large relative to **Absolute Error**
- **Loss Function** used to measure the difference between the `predicted` value and the `actual` value
- With this, we can measure the performance of different models with different complexities

  

# What is the Training Error ?

- **`Training Error`** is the average loss defined over the **Training Data**

                                                    $\frac{\mathrm{1} }{\mathrm{N}} \sum_{i=1}^{N} L(y_i, f_w(X_i))$

- So as we see, if we defined **Squared Error** as our **Loss Function**, then we will have **`Mean Squared Error*( MSE )*`**

                                                        $\frac{\mathrm{1} }{\mathrm{N}} \sum_{i=1}^{N} (y_i, f_w(X_i)^2$

- We can then define **`Root Mean Squared Error*( RMSE )`**,* which is the square root of our average loss

                                                    $\sqrt{ \frac{\mathrm{1} }{\mathrm{N}} \sum_{i=1}^{N} L(y_i, f_w(X_i))}$ 

    - This will return us the unit value of the original $y$, instead of `squared` in the equation of **`MSE`**
- Generally, a low `**Training Error**` rate do not guarantee a stronger model due to the fact that the model is fitted into the training set which is a limited amount of data. However, a high `**Training Error**` is a good indication that the model is inadequate.

# What is Generalization Error ?

- The error rate per example found when used on full(true) data.
- This determine how well the model actually perform on real-world application and thus is the one we are aiming for.
- However, it is fundamentally impossible to retrieve the full data of every possible cases, and thus it is impossible to calculate this value directly.

# What is Test Error ?

- **Test Error** allows us to approximate **Generalization Error,** by approximate the `error` that not in the `training set`. So **Test Error** is a noise version of **Generalization Error**
- **Test Error** is the average loss defined over the **Test Data**

                                                           $\frac{\mathrm{1} }{\mathrm{N_{test}}} \sum_{i=1}^{N} L(y_i, f_w(X_i))$

# How can we define overfitting ?

- A fitted model with $w$ `parameter` can be called overfitted if there're a fitted model with $w'$ `parameter` that
    - $training\_error(w)<training\_error(w')$
    - $true\_error(w)>true\_error(w')$
- We say that the **Overfitted** model is the one that highly fit the `training set`, but doesn't `generalize` well
- An **Overfitted** model is a statistical model that contains more `parameters` than can be justified by the data

# What will be the consequence of over or under splitting training set and test set ?

- If we put too few points in `training set`, then we're not going to estimate the model well. As a result, we will have clearly bad predictor performance because of that.
- If we put to few points in `test set`, that's gonna be a bad approximation to `Generalization Error`. Because it's not gonna represent a wide enough range of things we might see out there in the world.
- We will want just enough points in your `test set` to approximate `generalization error` well

# What are the sources of error ?

## What is Noise ?

- **Noise** is the term indicate that there're a lot of other aspect that may effect out `data`, and that is the reason that we can't compute the perfect relationship between `dependence variable` and `independence variable`
- This is the property of the `data`, and we can't control it, we must deal with it. And that's why we can it `Irreducible Error`

## What is **Bias ?**

- **Bias** is an assessment of how well our model can fit the `true relationship` between `x` and `y`.
- What **Bias** is, is it's the difference between the average fit and the `true function`. And so intuitively what **Bias** is saying is whether our model flexible enough to on average be able to capture the true relationship between `dependence variable` and `independence variable`

                                                          $low\_complexity  \leftrightarrows high\_bias$

                                                $Bias(X) = f_{w(true)}(X) - f_{avg(w)(X)}$

## What is **Variance ?**

- Show how difference that our fit vary from one to another `dataset` when we looking to difference `dataset`
- If they could vary dramatically from one `dataset` to the other, then we would have very erratic predictions. Our prediction would just be sensitive to what `dataset` we got

                                                   $high\_complexity \leftrightarrows high\_variance$

# How can we summarize between Bias and Variance ?

- We can think of **Mean Square Error ( MSE )**

                                                          $MSE = bias^2 + variance$

- Our goal is to find the minima of **MSE**, that will be the best model complexity that we can have
- However, we cannot compute **Bias**, **Variance**. Which mean we cannot compute **MSE** because they are defined in term of **True Error**
    - **Bias** was defined very explicitly in terms of the relationship relative to the **true function**
    - To define **Bias** and **Variance**, we will have to average on **ALL** over the `dataset`, and that is impossible