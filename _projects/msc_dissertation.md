---
title: "Reinforcement Learning Rewards"
excerpt: "Reinforcement Learning with Function Approximation in Continuing Tasks: Discounted Return or Average Reward?"
header:
  image: /assets/images/edinburgh_splash.jpg
  caption: "The old college of the University of Edinburgh"
  teaser: /assets/images/University_of_Edinburgh_logo.png
---

If you read the *About Me* page of this website, you'd already know that I did my Master's degree on artificial intelligence in 2020 at the University of Edinburgh in Scotland. The final part of the degree was the Master's thesis which I worked on between May and August of 2021.

The thesis project was done in the [Autonomous Agents Research Group](https://agents.inf.ed.ac.uk/), with Dr. Stefano Albrecht as the supervisor.

The research group specializes on machine learning and AI for autonomous systems control and decision making and thus naturally my thesis topic revolved around reinforcement learning which is widely used in these contexts. More specifically, we wanted to empirically test the difference in performance between return formulations of reinforcement learning agents.

The final title of the project was: *Reinforcement Learning with Function Approximation in Continuing Tasks: Discounted Return or Average Reward?*

Below you can read the paper's abstract which goes into the project's topic and methods a bit more deeply.

> Reinforcement learning is a machine learning sub-field, involving an agent performing sequential decision making and learning through trial and error inside a predefined environment. An important design decision for a reinforcement learning algorithm is the return formulation, which formulates the future expected returns that the agent receives after following any action in a specific environment state. In continuing tasks with value function approximation (VFA), average rewards and discounted returns can be used as the return formulation but it is unclear how the two formulations compare empirically. This dissertation aims at empirically comparing the two return formulations. We experiment with three continuing tasks of varying complexity, three learning algorithms and four different VFA methods. We conduct three experiments investigating the average performance over multiple hyperparameters, the performance with near-optimal hyperparameters and the hyperparameter sensitivity of each return formulation. Our results show that there is an apparent performance advantage in favour of the average rewards formulation because it is less sensitive to hyperparameters. Once hyperparameters are optimized, the two formulations seem to perform similarly

All the code used as well as the final paper can be found in [this GitHub repository](https://github.com/pkyriakou/RL-reward-experiments).
