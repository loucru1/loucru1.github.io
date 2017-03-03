---
layout: post
title:  "What is Data Science, Machine Learning?"
date:   2016-07-24 01:01:01 -0400
excerpt_separator: <!--more-->
category: data-science
tags: [ml, data-science]
comments: true
---

Over recent years there has been an increasing demand for data scientists. As smartphones become more ubiquitous and the rising trend of IoTs continues, ‘big data’ analysis has never been more essential.

However, many are still confused about what data science exactly is. The tech industry emphasizes buzzwords like ‘machine learning’ and ‘big data’ (leading many to believe that is solely what data science is all about.) Although dealing with big data and doing machine learning are important, they are only components of the larger process that make up data science.
<!--more-->

In general, data science is the process of understanding and extracting knowledge from data. This includes, but is not limited to, collecting data, performing exploratory analysis, and creating machine learning or statistical models to solve business problems. A typical data scientist might spend most of their time cleaning and manipulating data. Only after will they do machine learning, which, for the most part, depends heavily on the quality of the data munging. However, machine learning is still an integral component to producing usable results, which is ultimately the goal of a data scientist.

## So, What is Machine Learning?

Machine learning has a broad definition and can mean many different things to many people. However, in its most basic form, it is using past data to solve future problems. Typically, these problems are framed as a prediction:

- Predicting if an email is spam or not
- Predicting if a call received by a call center is attempting to extract a client’s information
- Predicting if an image represents a face
- Predicting who will be the next president

Data scientists are able to make these predictions by using data to create machine learning models. A model, in data science, is a mathematical specification of the relationships between different variables. For example, an investment model will probably take inputs like company revenue, net income, and sale numbers to produce expected stock price as output. Additionally, a machine learning model is a special kind of model that is learned from from data.

What makes machine learning such a popular field is that machine learning models can develop nuanced relationships between variables -- beyond what a normal person could find. And unlike with human skill, pattern detection becomes more pronounced and precise as the data quantity grows.

## How to Start Doing Machine Learning
If you are reading this post there is a good chance that you are interested in doing machine learning. While most guides will provide you with a coding walkthrough of the machine learning process, they almost never explain the reason behind each step. This guide will provide an overview of each major step in machine learning and explain why they are important.

# Data Preparation
There is a saying in the data science that summarizes the importance of good data preparation: ’Garbage in, Garbage Out’. In essence, machine learning models can only be as good as the data that is used to train them. Therefore, it is critical to spend extra effort in cleaning and formatting data. The meaning of ‘clean’ data is dependent on the project, but normally means that the data is consolidated in a consistent format.

Data can come in many types: images, words, numbers, and even binary. Overtime, a data scientist will develop expertise that will help them find the best way to represent their dataset.

# Feature Extraction
Once the data is formatted and processed, the next step is to extract the features to feed into a model. A feature is an individual, measurable property of a phenomenon being observed. Put more simply, features are meaningful attributes of the dataset. Understanding which attributes of a dataset are important is extremely difficult and time consuming, but gets easier with experience and domain knowledge. Some examples of features include:

- In a computer vision dataset, edges and objects from the images
- In a spam dataset, the types of words used in the document, or IP addresses

The main reason for using some features of the dataset and not the entire dataset is to only select the data that improves a machine learning model. Large data sets have many data points that may not be useful for the specific task at hand. Focusing only on a subset of the data can improve result accuracy.

# Picking and Training a Model
Picking a model that fits a project’s needs depends mainly on the the input data and desired output. Some models require the data to be labeled with its expected output (i.e. supervised models), where other models don’t require such overhead (unsupervised model). Some models produce binary or categorical outputs, while others produce the probabilities for every possible outcome. Usually, multiple models can be applied to a data set, so it is encouraged to experiment with different models to find out which method works best with a project. Figure 1 is a chart made by [scikit-learn](http://scikit-learn.org/stable/), a popular machine learning library in
python, which can be used to help determine what machine learning model might be best for a particular situation.

<br><br>

{% include image.html
            img="assets/ml_map.png"
            title="scikit-learn algorithm flowchart"
            caption="Figure 1: A flowchart designed to help select a suitable
            model based on type of data and problem."
%}

<br><br>
Once a model is chosen, it’s time to train the model. Training is where the heavy lifting, math intensive, ’learning’ is done; each model defines its own method of training. The purpose of training is to use input data to develop mathematical relationships between variables. Figure 2 is an example of a logistical regression model trained on survival (1 = survived, 0 = died) on the titanic by sex. Notice that depending on the training data, male vs female, the model produces a different logistical curve.

{% include image.html
            img="assets/titanic_survival.png"
            title="logistical regression titanic"
            caption="Figure 2: Two logistical models (lines) trained on historical
            surival tally of titanic passengers (dots). The models are separated
            by sex and predict the survival rate of a passenger given age and sex. "
 %}


# Prediction
Now that a machine learning model has been picked and trained, the fun begins. Trained models are able to predict future outcomes with incoming data. For example, take the titanic model above. Using this model, you could predict that for a 30 year old male (incoming data) the expected survival rate to be around 20% (prediction). Similarly, in a computer vision model, you could feed in a new picture of an animal and the model could classify it as an image of a dog. Keep in mind that the scope of what a model can predict depends entirely on the data it is trained on.

## Wrap up
And that’s it! You now have a predicting machine learning model! The process outlined here can work with many machine learning models. Using machine learning is not as hard or mysterious as it’s worked out to be, and understanding the basics will go far in creating a decent model.

This post was a simple overview of the concepts of machine learning. If you are someone who is looking to get experience with data science first hand, I would recommend this [O’reilly book](http://shop.oreilly.com/product/0636920033400.do). The book goes through a breadth of machine learning applications and models, from regression to neural nets. It is written for python but no experience is required. Happy data-ing!
