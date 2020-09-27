---
layout: page
title:  "Object Detection"
mathjax: true
---

{% include head/custom.html %}

Object detection is one of the areas of computer vision that’s exploding and it’s working so much better than just a couple years ago.

To explore the concept of object detection it is useful to begin with image classification. It goes through levels of incremental complexity. 

**Image classification** aims at assigning an image to one of a number of different categories (e.g. car, dog, cat, human, etc.), essentially answering the question “What is in this picture?”. One image has only one category assigned to it. 

**Object localization** then allows us to locate our object in the image, so our question changes to “What is it and where it is?”. 

In a real real-life scenario, we need to go beyond locating just one object but rather multiple objects in one image. For example, a self-driving car has to find the location of other cars, traffic lights, signs, humans and to take appropriate action based on this information.

**Object detection** provides the tools for doing just that –  finding all the objects in an image and drawing the so-called bounding boxes around them. 

There are also some situations where we want to find exact boundaries of our objects in the process called **instance segmentation**.

![](./object-detection.png) 

# Algorithms

There are a few different algorithms for object detection and they can be split into two groups:

- **Algorithms based on classification**. They are implemented in two stages. 
    - First, they select regions of interest in an image. 
    - Second, they classify these regions using convolutional neural networks. 
    
    This solution can be slow because we have to run predictions for every selected region. A widely known example of this type of algorithm is the _Region-based convolutional neural network_ (RCNN) and its cousins Fast-RCNN, Faster-RCNN and the latest addition to the family: Mask-RCNN. Another example is RetinaNet.
- **Algorithms based on regression** – instead of selecting interesting parts of an image, they predict classes and bounding boxes for the whole image in one run of the algorithm. The two best known examples from this group are the YOLO ([_You Only Look Once_](./yolo)) family algorithms and SSD (_Single Shot Multibox Detector_). They are commonly used for  real-time object detection as, in general, they trade a bit of accuracy for large improvements in speed.