---
layout: post
title: Two heads are better than one
subtitle:  Averaging along Fine-Tuning to Improve Targeted Transferability
gh-repo: daattali/beautiful-jekyll
gh-badge: [star, fork, follow]
tags: [adversarial example, trustworthy AI]
comments: true
---

{: .box-success}
Our key assumption is that an AE located at the center of high-confidence (w.r.t. y<sub>t</sub>) region may transfer better across unknown models than that located near the boundary of the high-confidence region. As shown in below, without cherry-picking, the proposed AaF steers AE towards a more central region than FFT, let alone the baseline attack (I'). The AEs are crafted with a Resnet50 (source model), while the planes are calculated on an ensemble of target models.

<div align=center>
  <img src="../../figs/2025ICASSP_919_08.png" width="500">
</div>

Well, how to accomplish this goal? Inspired by Izmailov et al's work [SWA], we propose averaging over the fine-tuning trajectory to pull the crafted AE towards a more centered region

[SWA] P. Izmailov, D. Podoprikhin, T. Garipov, et al., “Averaging weights leads to wider optima and better generalization,” Uncertainty in Artificial Intelligence, 2018.

Here are the targeted transfer success rates when Resnet 50 is the surrogate, no fine-tuning/fine-tuning with FFT / AaF:

| Attack |  IncV3  | Dense121 | Vgg16 |
| :------| :-------- |:------- | :-------- |
| CE   | 3.9/9.0/13.6 | 44.9/60.4/66.3 | 30.5/49.3/60.2 |
| Logit| 9.1/15.8/18.7 | 70.0/74.5/78.3 | 61.9/64.1/69.3 |
