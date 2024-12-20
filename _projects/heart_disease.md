---
title: "Heart Disease Prediction"
excerpt: "Is it possible to predict whether someone will develop heart disease in the future?"
header:
  image: /assets/images/heart_disease_splash.jpg
  caption: "Image courtesy of [FREEPIK](https://www.freepik.com/)"
  teaser: /assets/images/heart_disease_teaser.jpg
  teaser_caption: "Image courtesy of [FREEPIK](https://www.freepik.com/)"
---

Heart disease refers to a variety of conditions that affect the heart, including coronary artery disease, arrhythmias, and heart failure. It is the leading cause of death in many countries, but many types can be prevented or managed through healthy lifestyle choices.

Knowing whether you are at high risk of heart disease could be life-saving, by motivating people to not only seek preemptive care but also make the lifestyle changes required. Nowadays, we have access to many health markers, either through regular health check-ups or through wearable devices, that can be used to predict the chances of heart disease.

This project aimed to perform exactly that. Given health markers such as a patient's blood pressure, their cholesterol, their max heart rate, their resting ECG, etc. we try to predict whether the patient is suffering from heart disease. This can be formulated as a binary classification task - perfect for a machine learning solution.

The data was taken from Kaggle and was created user *fedesoriano*. The dataset, along with details about the data, can be found [here](https://www.kaggle.com/datasets/fedesoriano/heart-failure-prediction).

The project was done in two parts. The first part was focused on data exploration, visualization, and finally data cleaning and processing. The second part of the project focused on creating predictive models, training them, and evaluating them.

We trained three basic machine learning models to tackle this binary classification task: a Support Vector Machine classifier, a Decision Tree classifier, and a Nearest Neighbor classifier.

Because of its medical nature, the evaluation of the models was one of the most important aspects of this project. Using just the classification accuracy is not enough to judge such a "mission-critical" model. That is because false negatives can have detrimental effects in the medical domain - a false negative diagnosis could mislead a patient and make them think that they are healthy while they are not. For that reason, we reported the overall accuracy, the precision, the recall, and the f1-score (which is a general indicator that takes both precision and recall into account). Since false negatives are the most important for our project, we prioritized recall that takes them into account in its computation.

Our final results show our SVM classifier performing best, with overall accuracy of 85% and recall of 85% on test data. These are both impressive results for such a simple and easy to train model, and could further be improved with more data and more complex models.

The notebooks used for this project which includes details about the data and the methods used can be found in [this GitHub repository](https://github.com/pkyriakou/Heart-Disease-Prediction).
