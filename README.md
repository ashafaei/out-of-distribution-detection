# Out of Distribution Sample Detection
This repository is the ultimate self-contained reference for **out of distribution sample detection with deep neural networks**. We keep track of:

1. The latest publications.
2. The available (open-source) implementations.
3. A comparison of the compute cost, memory requirements, and the overall effectiveness of each method.

The hope is to provide the community with a current picture of the state-of-the-art on this problem. We welcome all contributions to this repository through [pull requests](pulls). You can also discuss your ideas and thoughts on ways to improve this repository in the [issues page](/issues).

*Last Update: Jan 16, 2019*.

**Note**. 
*In the following days, we will be gradually updating this repository with the latest developments. Meanwhile, stay tuned and feel free to contribute.*

- [Out of Distribution Sample Detection](#out-of-distribution-sample-detection)
- [Introduction](#introduction)
  - [Why Should We Care?](#why-should-we-care)
  - [Relevant Literatures](#relevant-literatures)
  - [Evaluation Techniques](#evaluation-techniques)
- [Methods](#methods)
  - [2018](#2018)
  - [2017](#2017)
  - [2016](#2016)
  - [2015](#2015)

# Introduction
## Why Should We Care?
In machine learning, a typical learning procedure would first split the available training data to train, validation, and test sets. We train the models on the train set, validate the hyperparameters on the validation set, and demonstrate the performance of the model on the test set. But, how would a well-performing model on the test set function in real-world applications? If model `A` performs better than model `B` on our test set, does that mean model `A` would also be more suitable for real-world applications?

Statistical learning theory provides a framework to answer these inquiries through some general assumptions. For instance, if our test set is large enough and IID, and if the real-world data is IID too, we can relate the test set error to the real-world error with a high probability. From a theoretical standpoint, if the real-world data comes from another distribution than the test set, then there would be no way for us to relate the errors in the absence of more information, i.e., *we do not have any idea how the model would perform on a new distribution*.

This problem is perhaps more critical than it seems, especially in the deep learning age. Let us say we have a cat vs. dog convolutional network that has a 99% accuracy on our huge test dataset. We deploy our model into a pipeline, and now we rely on the output to perform a task. Given an image, our model predicts a cat with 100% probability. How confident are we that the input to our model is, in fact, a cat? We know through the adversarial attacks that in the presence of an adversary, we cannot trust anything our model says. Even if we assume there are no adversaries, we still would not have certainty that the input image is a cat. However, if we further assume that the input image is from the same distribution as the test set on which we had 99% classification accuracy, we could have some degree of confidence that the input image is a real cat. To be more accurate, we would know that if we were given an independently sampled set from the same distribution as the test set, our model would not make mistakes on more than a certain number of samples with a high probability.

Determining whether an input is familiar (i.e., belongs to the population distribution of the training data), should be a *pre-condition to prediction with deep learning models*. If the sample is out-of-distribution, then the predictions are unreliable, and the error cannot be bounded.

## Relevant Literatures
## Evaluation Techniques

# Methods
## 2018
## 2017
## 2016
## 2015
