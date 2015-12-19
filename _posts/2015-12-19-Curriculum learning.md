---
layout: post
title: Curriculum learning
---

### Introduction

Curriculum learning is a technique for training machine learning systems  proposed by Yoshua Bengio et al. in the paper named Curriculum Learning.

The method of curriculum learning is quite intuitive. It is analogous to how we learn in schools, we first start with a easy introductory course and gradually learn more advanced courses of the same subject. Yoshua Bengio et al. suggest that if we train our system on data sets of increasing order of 'difficulty' then the model can achieve better generalization and reduce training time.

### Curriculum learning as a continuation method

Continuation methods (Allgower & Georg, 1980) first 'optimize a smoothed version of the objective function and gradually consider less smoothing with the intuition that the smoothed version of the problem reveal the global picture'.

![_config.yml]({{ site.baseurl }}/images/first-smoothed.png)

![_config.yml]({{ site.baseurl }}/images/original-loss.png)

![_config.yml]({{ site.baseurl }}/images/config.png)

Figure 1: Sequence of functions from most smoothed to least smoothed.

Consider the example in figure 1, if we minimize the original objective using gradient descent starting at \\(x=1.5\\) we might get stuck at the local minimum at \\(x \approx 0.4\\). However, if we minimize the top objective, we can go pass the local minimum and arrive at an approximate solution at \\(x \approx -2.35\\). After that, we optimize the non-smoothed objective but with a starting point at \\(x \approx -2.35\\). This time we arrive at the global minimum.

In Curriculum Learning, Bengio et al. did not try to smooth the objective function but to give the system easier training examples first to guide the training toward better regions in parameter space. More difficult training examples are gradually introduced latter to fine turn the model.

The remaining problem is how to define 'easy' and 'hard' examples. Bengio et al. suggest to use entropy of the data set: easier data set should have lower entropy, i.e less variability while harder ones should have higher entropy. Bengio et al. sampled the original data set to create an easy data set with low entropy and a harder one with the original entropy.
Result

Although the technique is simple, it is quite effective in practice. Systems trained with curriculum learning are not only generalize better but also converge faster. Detailed result can be found in the original paper.

### References
Bengio, Yoshua, et al. "Curriculum learning." Proceedings of the 26th annual international conference on machine learning. ACM, 2009.

Allgower, E. L., & Georg, K. (1980). Numerical continuation methods. An introduction. Springer-Verlag