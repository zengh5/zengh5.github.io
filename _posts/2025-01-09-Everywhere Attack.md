---
layout: post
title: Everywhere Attack 
subtitle: Attacking Locally and Globally to Boost Targeted Transferability 
gh-repo: daattali/beautiful-jekyll
gh-badge: [star, fork, follow]
tags: [adversarial example, trustworthy AI, 2025AAAI]
comments: true
---

{: .box-success}
The proposed method can be illustrated with the following figure. To fool a DNN model to misclassify a 'Bajie' image as 'Wukong', we plant an army of 'Wukong's to the 'Bajie'. 
Specifically, we split the 'Bajie' image into non-overlap blocks and jointly mount a targeted attack on each block. 
Such a strategy avoids transfer failures caused by attention inconsistency between surrogate and victim models and thus results in strong transferability.

<div align=center>
  <img src="../../figs/2025AAAI_Fig1.png" width="750">
</div>

## Experiments

Results on CNNs w.o./w. the proposed *everywhere* scheme (surrogate: res50):

| Attack |  IncV3  | Dense121 | Vgg16 |
| :------| :-------- |:------- | :-------- |
| CE   | 3.9/14.1 | 44.9/62.3 | 30.5/55.2 |
| [Logit](https://github.com/ZhengyuZhao/Targeted-Tansfer)| 9.1/22.3 | 70.0/78.5 | 61.9/69.3 |
| [Margin](https://github.com/WJJLL/Target-Attack)| 10.9/21.7 | 70.8/80.8 | 61.2/69.4 |
| [SH](https://github.com/zengh5/Transferable_targeted_attack)   | 9.9/17.8 | 74.2/82.7 | 62.5/78.2 |
| [SU](https://github.com/zhipeng-wei/Self-Universality)   | 11.1/21.9 | 72.5/79.2 | 63.9/67.4 |
| [CFM](https://github.com/dreamflake/CFM)   | 41.4/55.3 | 83.3/87.7 | 77.2/81.9 |

Results on Vits (surrogate: res50):

| Attack |  vit_b  | pit_b | visformer |
| :------| :-------- |:------- | :-------- |
| CE   | 0.6/3.7 | 2.0/3.5 | 4.8/15.3 |
| Logit| 2.7/9.2 | 6.0/13.4 | 16.0/32.2 |
| Margin| 4.8/6.4 | 7.6/9.3 | 19.5/28.4 |
| SH   | 3.7/6.6 | 7.3/18.8 | 20.1/36.1 |
| SU   | 5.0/5.3 | 4.8/12.9 | 20.0/29.6 |

### Notification

{: .box-note}
**Note:** For vits, the original images are first resampled to 224 x 224 pixels and then attacked.





