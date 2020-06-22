---
layout: post
title: Volume Conservation in Deep Nets
comments: True
---
## Volume Conservation through Jacobian's determinant
Many works suggested that volume conservation is important for deep nets to learn effectively. 
[Unterthiner & Hochreiter](https://openreview.net/forum?id=ROVmN8wyOSvnM0J1IpNm "Understanding Very Deep Networks via Volume Conservation. Thomas Unterthiner & Sepp Hochreiter") argued that ResNet, LSTM, Highway nets are all based on this idea. 
Information theoretic view of a mapping:

$$Y = f(X)$$

$$H(Y) \le H(X) + \mathbb{E}\left[ \log\left(\left\vert\frac{\partial Y}{\partial X}\right\vert\right) \right]$$

If the determinant is smaller than 1, we loss some information. 
To conserve the volume/information, the determinant of the Jacobian must be 1.


## Volume Conservation through Initialization

[Xavier initialization](http://proceedings.mlr.press/v9/glorot10a.html "Understanding the difficulty of training deep feedforward neural networks") also tries to keep the variance of the outputs to be the same as that of the inputs. That's another form of coservation.

Recently, [Sitzmann et al.](https://vsitzmann.github.io/siren/ "Implicit Neural Representations with Periodic Activation Functions") introduced SINusoidal REpresentation Networks (SIREN) for "representing  complex natural signals and their derivatives".
The authors also proposed an initialization scheme which allows SIREN to be trained efficiently.
"The key idea in our initialization scheme is to preserve the distribution of activations
through the network so that the final output at initialization does not depend on the number of layers."

## Some thoughts
From these paper, we see that volume/information preservation is the key to representation learning.
We could use this as a guideline for developing new Deep Generative Models.


