---
title: 3 inequalities for good models 👌
slug: 3-inequalities-for-good-models
date: 2023-04-12
excerpt: Guidelines for good models, that often hold true.
---

## Cross-Validation > Single Validation Set

Yes, you should have a **test set**, which you never touch, only when evaluating your final model. In a sense, we could call this the "measuring set", as its only purpose should be to give you a performance number of unseen data. 

However, for the model building, hyperparameter tuning and feature engineering that leads up to it, use a form of **cross-validation** to evaluate your model's performance. 

This makes it more difficult to tailor your model to the validation data (bad idea), but it also protects you from getting a "lucky" draw on your validation set, which might make your model look better than it is.

## Starting simple > Starting complex

Do a **kitchen-sink-style linear regression first**. Otherwise, you will have no idea whether your 10 layer neural-network is any good. 

This inequality is even more important, if your problem is likely not too far from being linear: Predicting house prices based on houses' living area and number of pools is probably *"less" non-linear*, than identifying a cat in a foto. Here, a linear regression is mandatory, as **imposing **the linear structure, **rather than learning** it, could be a giant win for your prediction performance. At least it does not hurt to try.

After all, OLS takes like 10 seconds.

## Domain Knowledge > Data Mining

Parameters, hyperparameters, your optimization's settings, trying out various interactions between variables, or performing a **shotgun-style** basis expansion: All valid options. 

But, simply poking around in the data until something works bears many risks: Your model might be overly complex, you overlook essential structures in the data, or waste resources. **Think** about what is going on **first**, then mine the data and poke your model to squeeze out the last few performance points. 

Do you really need 3-way interactions to predict house prices? Maybe some select interactions, such as whether a house has a sauna AND a pool (think: luxurious house), gets you pretty far? 

Often it is about finding one, or two, of the **gold nuggets** in your data, rather than having a pile of gravel with a few of the gold nuggets buried in it.
