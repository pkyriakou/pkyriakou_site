---
title: "Cactus Identification Challenge"
excerpt: "Determine whether an image contains a columnar cactus."
header:
  image: /assets/images/aerial_cactus_splash.jpg
  caption: "Image courtesy of [Kaggle](https://www.kaggle.com/)"
  teaser: /assets/images/aerial_cactus_teaser.jpg
  teaser_caption: "Image courtesy of [FREEPIK](https://www.freepik.com/)"
---

This was one of the projects done in my first year in the Honors Academy of the Eindhoven University of Technology. In that first year, my team and I participated in multiple Kaggle competitions centered around the theme of computer vision and pictures of nature. Specifically, this project's goal was to classify whether a aerial landscape image has a columnar cactus or not.

The below excerpt was taken from the competition's webpage and describes the motivation for the competition:
> To assess the impact of climate change on Earth's flora and fauna, it is vital to quantify how human activities such as logging, mining, and agriculture are impacting our protected natural areas. Researchers in Mexico have created the VIGIA project, which aims to build a system for autonomous surveillance of protected areas. A first step in such an effort is the ability to recognize the vegetation inside the protected areas. In this competition, you are tasked with creation of an algorithm that can identify a specific type of cactus in aerial imagery.

Our solution to the competition was a deep convolutional neural network, which was implemented using Tensorflow. Data augmentation was also performed (horizontal flips and rotations) to increase the training data size.

The final accuracy on the held out test set was 99.8% with the data augmentation and 96.9% without.

The notebook submitted for the competition which shows the data preprocessing and the model training can be found in [this GitHub repository](https://github.com/pkyriakou/Cactus-Identification-Challenge-ML).
