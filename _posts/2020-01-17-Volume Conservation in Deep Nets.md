---
layout: post
title: Volume Conservation in Deep Nets
comments: True
---

Many works suggested that volume conservation is important for deep nets to learn effectively. [1] argued that ResNet, LSTM, Highway nets are all based on this idea. 
Information theoretic view of a mapping:

$$Y = f(X)$$

$$H(Y) \le H(X) + \mathbb{E}\left[ \log\left(\left\vert\frac{\partial Y}{\partial X}\right\vert\right) \right]$$

If the determinant is smaller than 1, we loss some information. 
To conserve the volume/information, the determinant of the Jacobian must be 1.

Xavier initialization also tries to keep the variance of the outputs to be the same as that of the inputs. That's another form of coservation.

[1] Understanding Very Deep Networks via Volume Conservation. Thomas Unterthiner & Sepp Hochreiter


