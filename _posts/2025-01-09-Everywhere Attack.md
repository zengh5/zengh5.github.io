---
layout: post
title: Everywhere Attack 
subtitle: Attacking Locally and Globally to Boost Targeted Transferability 
gh-repo: daattali/beautiful-jekyll
gh-badge: [star, fork, follow]
tags: [adversarial example, trustworthy AI]
comments: true
---

{: .box-success}
The proposed method can be illustrated with the following figure. To fool a DNN model to misclassify a 'Bajie' image as 'Wukong', we plant an army of 'Wukong's to the 'Bajie'. 
Specifically, we split the 'Bajie' image into non-overlap blocks and jointly mount a targeted attack on each block. 
Such a strategy avoids transfer failures caused by attention inconsistency between surrogate and victim models and thus results in strong transferability.

![fig1](https://github.com/zengh5/Everywhere_Attack/blob/main/fig/Fig1.png)

## Here is a secondary heading

[This is a link to a different site](https://deanattali.com/) and [this is a link to a section inside this page](#local-urls).

Here's a table:

| Number | Next number | Previous number |
| :------ |:--- | :--- |
| Five | Six | Four |
| Ten | Eleven | Nine |
| Seven | Eight | Six |
| Two | Three | One |

How about a yummy crepe?

![Crepe](https://beautifuljekyll.com/assets/img/crepe.jpg)

It can also be centered!

![Crepe](https://beautifuljekyll.com/assets/img/crepe.jpg){: .mx-auto.d-block :}

### Notification

{: .box-note}
**Note:** This is a notification box.

### Warning

{: .box-warning}
**Warning:** This is a warning box.

### Error

{: .box-error}
**Error:** This is an error box.

## Local URLs in project sites {#local-urls}

When hosting a *project site* on GitHub Pages (for example, `https://USERNAME.github.io/MyProject`), URLs that begin with `/` and refer to local files may not work correctly due to how the root URL (`/`) is interpreted by GitHub Pages. You can read more about it [in the FAQ](https://beautifuljekyll.com/faq/#links-in-project-page). To demonstrate the issue, the following local image will be broken **if your site is a project site:**

![Crepe](/assets/img/crepe.jpg)

If the above image is broken, then you'll need to follow the instructions [in the FAQ](https://beautifuljekyll.com/faq/#links-in-project-page). Here is proof that it can be fixed:

![Crepe]({{ '/assets/img/crepe.jpg' | relative_url }})
