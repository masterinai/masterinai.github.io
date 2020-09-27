---
layout: page
title:  "Landmark Detection"
mathjax: true
---

{% include head/custom.html %}

In [Object Localization](./object-localization) we saw how we can get a neural network to output 4 numbers: $$ b_x, b_y ,b_h, b_w $$ to specify the bounding box of an object we want to localize. In more general cases we can have a neural network which outputs just $$ x $$ and $$ y $$ coordinates of important points in the image, sometimes called **landmarks**. 

Let’s see a few examples. Let’s say we’re building a face recognition application, and for some reason we want the algorithm to tell us where is the corner of someone’s eye.

# References
- http://datahacker.rs/deep-learning-landmark-detection/