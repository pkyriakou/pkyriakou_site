---
title: "Car price prediction"
excerpt: "Learn how much your car might be worth without ever speaking to a dealer."
header:
  image: /assets/images/image_cars_large.jpg
  caption: "Image courtesy of [FREEPIK](https://www.freepik.com/)"
  teaser: /assets/images/image_cars_small.jpg
  teaser_caption: "Image courtesy of [FREEPIK](https://www.freepik.com/)"
---

Asset valuation can be a very time consuming and stressful process. It basically dictates how much money you will earn or spend on a product, and thus it carries a lot of weight for everyone involved.

When it comes to cars, car evaluation is usually performed by car dealerships or by individuals if you opt for a direct transaction. In both cases, the two parties, namely the seller and the buyer, may try to trick each other by asking for a lower or higher price than what the car is worth.

Therefore, an automatic car valuation system would be very useful for the "average Joe". They know nothing about cars, and they're about to buy or sell a car and want to know the car's approximate value. This is exactly what was built in this project which was part of [Kaggle's Playground Series competition](https://www.kaggle.com/competitions/playground-series-s4e9/overview).  

The code for this project can be found [here](https://www.kaggle.com/code/pkyriakou/predicting-used-car-prices-a-basic-approach) (on Kaggle).

Below, I will go over some main takeaways from this project. To see all the data analysis and model experimentation, look at the notebook from the link above.

## The Data

To create our predictive model, we had a dataset of around 190k valuated cars, and to assess our model for the competition we had to predict the value of 120k cars.

The data features in this project included all typical values relevant to cars. Namely:

- the brand,
- the model,
- the year in which the model came out,
- the milage,
- the engine information,
- the transmission information,
- the fuel type,
- the exterior and interior colors.

These features are all we need to know to make an estimate on how much a car is worth, but we quickly run into problems with the data.

### Challenges phased

The main challenge that plagued our dataset was that most of the categorical features had very high cardinality, meaning that they had many unique values instead of a handful of values that each car could take.
For example, the car model feature had nearly 2k unique values and the the color features had around 200 unique values. Having so many unique value makes it very difficult to create a model since it would explode the dimensionality when we would apply the categorical feature encoding.
We handled those features by doing data aggregation and keeping the five to ten most popular values as they are with the rest of the values being labeled as "Other". This made the problem much more manageable in terms of dimensionality. Of course, with features like the car's model, which had most values be quite equally infrequent, we decided to drop the feature completely.

Another challenge was that the engine information, which is information that could be quite critical to the value of a car, was unstructured. Instead of having numerical features like horse power or displacement, we had all engine information in a string.
We extracted the horse power, the cylinder count, and the displacement using regular expressions and created three numerical features from the one categorical feature.

## The predictive model

The final predictive model at the end of the project was an Gradient Boosted Tree regressor with a max depth of 7 and 200 estimators.

This was the first project in which I went really deep into Sklearn's pipelines and column transformers. The final "model" was a pipeline with:

1. a column transformer for imputation,
2. another column transformer for normalization, discretization, and encoding
3. the regressor

This made it possible to basically to perform all those pipeline actions with one call during training and during inference - minimizing code duplication and most importantly, the chance of data leakage during the preprocessing stages.

## Final performance

The final performance of the model was an RMSE of ~64,000.

That means that the model was off by around 60k in each of its predictions. That is quite a lot, especially given that most cars in the world probably cost less than 60k.

The RMSE value though, since it's an average, is heavily influenced by extreme values. That means perhaps most of the model's predictions were much closer to the real value but some were quite off leading the RMSE value to be high. Indeed, in the data some blatant price "outliers" can be found (like a 3M$ 2023 Ford Bronco Raptor).

For the sake of comparison, the top Kaggle submission, which used extra data (from another competition) for its model training, had an RMSE of ~63,000. Our model did not do too badly I'd say.
