# Out of Distribution Sample Detection
This repository is the ultimate self-contained reference for **out of distribution sample detection with deep neural networks**. We keep track of:

1. The latest publications.
2. The available (open-source) implementations.
3. A comparison of the compute cost, memory requirements, and the overall effectiveness of each method.

The hope is to provide the community with a current picture of the state-of-the-art on this problem. We welcome all contributions to this repository through [pull requests](pulls). You can also discuss your ideas and thoughts on ways to improve this repository in the [issues page](/issues).

*Last Update: Jan 22, 2019*.

**Note**. 
*In the following days, we will be gradually updating this repository with the latest developments. Meanwhile, stay tuned and feel free to contribute.*

- [Out of Distribution Sample Detection](#out-of-distribution-sample-detection)
- [Introduction](#introduction)
  - [Why Should We Care?](#why-should-we-care)
  - [Relevant Literatures](#relevant-literatures)
    - [Epistemic Uncertainty](#epistemic-uncertainty)
    - [Prediction with Abstention](#prediction-with-abstention)
    - [Anomaly Detection](#anomaly-detection)
    - [Novelty Detection](#novelty-detection)
  - [Evaluation Techniques](#evaluation-techniques)
    - [Two-distribution](#two-distribution)
    - [OD-test](#od-test)
- [Methods](#methods)
  - [2019](#2019)
    - [Outlier exposure with confidence control for out-of-distribution detection](#outlier-exposure-with-confidence-control-for-out-of-distribution-detection)
  - [2018](#2018)
    - [Deep anomaly detection with outlier exposure](#deep-anomaly-detection-with-outlier-exposure)
    - [Metric Learning for Novelty and Anomaly Detection](#metric-learning-for-novelty-and-anomaly-detection)
    - [Reducing Network Agnostophobia](#reducing-network-agnostophobia)
    - [Out-of-distribution detection using an ensemble of self supervised leave-out classifiers](#out-of-distribution-detection-using-an-ensemble-of-self-supervised-leave-out-classifiers)
    - [Enhancing the Robustness of Prior Network in Out-of-Distribution Detection](#enhancing-the-robustness-of-prior-network-in-out-of-distribution-detection)
    - [Out-of-distribution detection using multiple semantic label representations](#out-of-distribution-detection-using-multiple-semantic-label-representations)
    - [Generative ensembles for robust anomaly detection](#generative-ensembles-for-robust-anomaly-detection)
    - [Detecting Out-Of-Distribution Samples Using Low-Order Deep Features Statistics](#detecting-out-of-distribution-samples-using-low-order-deep-features-statistics)
    - [A simple unified framework for detecting out-of-distribution samples and adversarial attacks](#a-simple-unified-framework-for-detecting-out-of-distribution-samples-and-adversarial-attacks)
    - [Anomaly Detection with Generative Adversarial Networks](#anomaly-detection-with-generative-adversarial-networks)
    - [Novelty Detection with GAN](#novelty-detection-with-gan)
  - [2017](#2017)
    - [Enhancing The Reliability of Out-of-distribution Image Detection in Neural Networks](#enhancing-the-reliability-of-out-of-distribution-image-detection-in-neural-networks)
    - [Training Confidence-calibrated Classifiers for Detecting Out-of-Distribution Samples](#training-confidence-calibrated-classifiers-for-detecting-out-of-distribution-samples)
  - [2016](#2016)
    - [A Baseline for Detecting Misclassified and Out-of-Distribution Examples in Neural Networks](#a-baseline-for-detecting-misclassified-and-out-of-distribution-examples-in-neural-networks)
    - [Towards Open Set Deep Networks](#towards-open-set-deep-networks)
  - [2015](#2015)

# Introduction
## Why Should We Care?
In machine learning, a typical learning procedure would first split the available training data to train, validation, and test sets. We train the models on the train set, validate the hyperparameters on the validation set, and demonstrate the performance of the model on the test set. But, how would a well-performing model on the test set function in real-world applications? If model `A` performs better than model `B` on our test set, does that mean model `A` would also be more suitable for real-world applications?

Statistical learning theory provides a framework to answer these inquiries through some general assumptions. For instance, if our test set is large enough and IID, and if the real-world data is IID too, we can relate the test set error to the real-world error with a high probability. From a theoretical standpoint, if the real-world data comes from another distribution than the test set, then there would be no way for us to relate the errors in the absence of more information, i.e., *we do not have any idea how the model would perform on a new distribution*.

This problem is perhaps more critical than it seems, especially in the deep learning age. Let us say we have a cat vs. dog convolutional network that has a 99% accuracy on our huge test dataset. We deploy our model into a pipeline, and now we rely on the output to perform a task. Given an image, our model predicts a cat with 100% probability. How confident are we that the input to our model is, in fact, a cat? We know through the adversarial attacks that in the presence of an adversary, we cannot trust anything our model says. Even if we assume there are no adversaries, we still would not have certainty that the input image is a cat. However, if we further assume that the input image is from the same distribution as the test set on which we had 99% classification accuracy, we could have some degree of confidence that the input image is a real cat. To be more accurate, we would know that if we were given an independently sampled set from the same distribution as the test set, our model would not make mistakes on more than a certain number of samples with a high probability.

Determining whether an input is familiar (i.e., belongs to the population distribution of the training data), should be a *pre-condition to prediction with deep learning models*. If the sample is out-of-distribution, then the predictions are unreliable, and the error cannot be bounded.

## Relevant Literatures

### Epistemic Uncertainty

### Prediction with Abstention

### Anomaly Detection

### Novelty Detection

## Evaluation Techniques

### Two-distribution
- False-positive rate at 95% true-positive rate.
- optimal detection error.
- area under the ROC curve
- area under the PR curve.

### OD-test
Shafaei, Alireza, Mark Schmidt, and James J. Little. "Does Your Model Know the Digit 6 Is Not a Cat? A Less Biased Evaluation of" Outlier" Detectors." arXiv preprint arXiv:1809.04729 (2018).

# Methods
## 2019

### Outlier exposure with confidence control for out-of-distribution detection 
A.-A. Papadopoulos, M. R. Rajati, N. Shaikh, and J. Wang, “Outlier Exposure with Confidence Control for Out-of-Distribution Detection,” arXiv Prepr. arXiv1906.03509, 2019.

## 2018

### Deep anomaly detection with outlier exposure
D. Hendrycks, M. Mazeika, and T. G. Dietterich, “Deep anomaly detection with outlier exposure,” arXiv Prepr. arXiv1812.04606, 2018.

### Metric Learning for Novelty and Anomaly Detection
M. Masana, I. Ruiz, J. Serrat, J. van de Weijer, and A. M. Lopez, “Metric Learning for Novelty and Anomaly Detection,” arXiv Prepr. arXiv1808.05492, 2018.

### Reducing Network Agnostophobia
A. R. Dhamija, M. Günther, and T. Boult, “Reducing Network Agnostophobia,” in Advances in Neural Information Processing Systems 31, S. Bengio, H. Wallach, H. Larochelle, K. Grauman, N. Cesa-Bianchi, and R. Garnett, Eds. Curran Associates, Inc., 2018, pp. 9175–9186.

### Out-of-distribution detection using an ensemble of self supervised leave-out classifiers
A. Vyas, N. Jammalamadaka, X. Zhu, D. Das, B. Kaul, and T. L. Willke, “Out-of-distribution detection using an ensemble of self supervised leave-out classifiers,” in European Conference on Computer Vision, 2018, pp. 560–574.

### Enhancing the Robustness of Prior Network in Out-of-Distribution Detection
W. Chen, Y. Shen, X. Wang, and W. Wang, “Enhancing the Robustness of Prior Network in Out-of-Distribution Detection,” arXiv Prepr. arXiv1811.07308, 2018.

### Out-of-distribution detection using multiple semantic label representations
G. Shalev, Y. Adi, and J. Keshet, “Out-of-distribution detection using multiple semantic label representations,” in Advances in Neural Information Processing Systems, 2018, pp. 7386–7396.

### Generative ensembles for robust anomaly detection
H. Choi and E. Jang, “Generative ensembles for robust anomaly detection,” arXiv Prepr. arXiv1810.01392, 2018.

### Detecting Out-Of-Distribution Samples Using Low-Order Deep Features Statistics
I. M. Quintanilha, R. de M. E. Filho, J. Lezama, M. Delbracio, and L. O. Nunes, “Detecting Out-Of-Distribution Samples Using Low-Order Deep Features Statistics.” 2018.

### A simple unified framework for detecting out-of-distribution samples and adversarial attacks
K. Lee, K. Lee, H. Lee, and J. Shin, “A simple unified framework for detecting out-of-distribution samples and adversarial attacks,” in Advances in Neural Information Processing Systems, 2018, pp. 7167–7177.

### Anomaly Detection with Generative Adversarial Networks
L. Deecke, R. Vandermeulen, L. Ruff, S. Mandt, and M. Kloft, “Anomaly Detection with Generative Adversarial Networks.” 2018.

### Novelty Detection with GAN
M. Kliger and S. Fleishman, “Novelty Detection with GAN,” arXiv:1802.10560, 2018.

## 2017
### Enhancing The Reliability of Out-of-distribution Image Detection in Neural Networks
S. Liang, Y. Li, and R. Srikant, “Enhancing The Reliability of Out-of-distribution Image Detection in Neural Networks,” ICLR, 2018.

### Training Confidence-calibrated Classifiers for Detecting Out-of-Distribution Samples
K. Lee, H. Lee, K. Lee, and J. Shin, “Training Confidence-calibrated Classifiers for Detecting Out-of-Distribution Samples,” in ICLR, 2018.

## 2016

### A Baseline for Detecting Misclassified and Out-of-Distribution Examples in Neural Networks
D. Hendrycks and K. Gimpel, “A Baseline for Detecting Misclassified and Out-of-Distribution Examples in Neural Networks,” ICLR, 2017.

### Towards Open Set Deep Networks
A. Bendale and T. E. Boult, “Towards Open Set Deep Networks,” in CVPR, 2016.

## 2015
