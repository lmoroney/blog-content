---
title: New Dataset for Yoga Pose Classification
layout: article
tags: ai coding
---

![Image of Yoga Pose](/assets/girl1_tree133.jpg)

I'm a huge fan of using synthetic means to create data to drive Machine Learning understanding forward. For computer vision, one often has spend a lot of money to create a dataset of images, by, for example, hiring photographers, models, equipment and the rest. 

But with Computer Generated Imagery (CGI), it's becoming easier to create photorealistic images on your desktop. I started this experiment with the Rock Paper Scissors and Horse or Human datasets, which you can find on this site [here](https://laurencemoroney.com/datasets.html)

My newest creation is a Yoga Poses dataset, which you can download in its entirety from [here](http://download.tensorflow.org/data/pose_classification/yoga_poses.zip)

It contains several hundred 300x300 full color images in 5 different Yoga Poses: Downward Dog, The Warrior, The Tree, The Chair, and The Cobra. There are many different backgrounds and both male and female models with a variety of skin and hair tones, as well as different camera angles and lighting. It's a challenging one to build a classifier with, and hopefully will be a useful alternative to the usual run-of-the-mill datasets!

It also includes many frames of the model going into and out of the pose, instead of just dealing with the finished pose, so you can build a classifier to potentially classify different stages should you want to!

Here's an example of a male model on his way into the Warrior pose:

![Male model in warrior pose](/assets/guy2_warrior054.jpg)

Or, the same model a little later into the pose! 

![Male model in warrior pose, later](/assets/guy2_warrior111.jpg)

Here also is a girl entering the chair pose:

![Female model in chair pose, early](/assets/girl1_chair081.jpg)

...and the same girl deeper into the pose, from a different angle:

![Female model in chair pose, later](/assets/girl1_chair138.jpg)


There's a really cool notebook using it with Movenet -- teaching you how to integrate movenet classifications with poses on the TensorFlow site [here](https://www.tensorflow.org/lite/tutorials/pose_classification)

...and of course, you could try this dataset with a Convolutional Neural Network, like the ones I teach about on [Coursera](https://www.coursera.org/learn/convolutional-neural-networks-tensorflow)

I'd love to hear if you find this dataset useful, and please reach out to me on [Twitter](https://twitter.com/lmoroney) if so! 

All of these images were created using [Daz3D](http://daz3d.com) should you want to try for yourself!