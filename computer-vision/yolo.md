---
layout: page
title:  "YOLO Algorithm"
mathjax: true
---

{% include head/custom.html %}

YOLO (“You Only Look Once”) is an effective real-time object recognition algorithm, first described in the seminal 2015 paper by Joseph Redmon et al. One of the algorithm’s open source implementations can be found [here](https://pjreddie.com/darknet/yolo).

"You Only Look Once" (YOLO) is a popular algorithm because it achieves high accuracy while also being able to run in real-time. This algorithm "only looks once" at the image in the sense that it requires only one forward propagation pass through the network to make predictions. After non-max suppression, it then outputs recognized objects together with the bounding boxes.

In this video, one of the authors of the YOLO paper explains it
<iframe width="560" height="315" src="https://www.youtube.com/embed/NM6lrxy0bxs" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

# References

- [You Only Look Once: Unified, Real-Time Object Detection by Joseph Redmon et al](https://arxiv.org/abs/1506.02640)
- [https://appsilon.com/object-detection-yolo-algorithm/](https://appsilon.com/object-detection-yolo-algorithm/)
