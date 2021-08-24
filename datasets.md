---
layout: article
aside:
  toc: true
title: Datasets for Machine Learning
key: page-teaching
redirect_from: 
  - /horses-or-humans-dataset/
  - /rock-paper-scissors-dataset/


---

When learning Computer Vision, particularly the training of DNNs and CNNs to recognize and classify images, there is a shortage of suitable datasets. You tend to see the same old datasets again and again.

*I wanted to fix that problem*

I wanted a unique and distinct dataset for teaching binary classifiers.  

I wanted to see if I could use Photoreal CGI to train a neural network that could then recognize and classify real images with the same subject matter.

## Horses or Humans Dataset
The result is Horses-v-Humans. You can download the raw data for the training set [here](https://storage.googleapis.com/laurencemoroney-blog.appspot.com/horse-or-human.zip) and a validation set [here](https://storage.googleapis.com/laurencemoroney-blog.appspot.com/validation-horse-or-human.zip).

The set contains 500 rendered images of various species of horse in multiple poses in multiple locations. It also includes 527 rendered images of humans in different poses and backgrounds. I emphasized the diversity of humans, so there are both men and women and Asian, Black, South Asian, and Caucasians present in the training set. The validation set adds six different figures to ensure breadth of data.

Here are some examples:  

![An image of a horse](/assets/horse03-3.png)
![An image of a horse](/assets/horse08-5.png)
![An image of a human](/assets/human01-16.png)
![An image of a human](/assets/human05-09.png)

**All Images are 300×300 pixels in 24-bit color.**

They’re arranged into sub folders within the zip that makes it easy to auto label them using a Keras ImageGenerator

#### License
The dataset is licensed as a CC By 2.0, free for you to share and adapt for all uses, commercial or non-commercial. Please just attribute and give appropriate credit to Laurence Moroney (lmoroney@gmail.com / laurencemoroney.com), and place no additional restrictions on your users as outlined here.

## Rock Paper Scissors Dataset
Rock Paper Scissors contains images from various hands, from different races, ages, and genders, posed into Rock / Paper or Scissors and labeled as such. You can download the [training set here](https://storage.googleapis.com/laurencemoroney-blog.appspot.com/rps.zip) and the [test set here](https://storage.googleapis.com/laurencemoroney-blog.appspot.com/rps-test-set.zip). I created these images using CGI techniques as an experiment in determining if a model trained on a CGI-based dataset could classify real images. I also generated a few pictures that you can use for predictions. You can [find them here](https://storage.googleapis.com/laurencemoroney-blog.appspot.com/rps-validation.zip).

Note that all of these pictures use a plain white background.
Each image is 300×300 pixels in 24-bit color.
Examples
Here are a few examples showing some of the poses and the diversity of hands used.
![An image of a rock](/assets/rock06ck02-085.png)
![An image of a paper](/assets/scissors04-080.png)
![An image of a scissors](/assets/testpaper01-00.png)

#### License
The dataset is licensed as a CC By 2.0, free for you to share and adapt for all uses, commercial or non-commercial. Please attribute and give appropriate credit to Laurence Moroney (lmoroney@gmail.com / laurencemoroney.com), and place no additional restrictions on your users as outlined here.

## Yoga Poses Dataset
This dataset contains images of 5 different Yoga Poses, rendered with a variety of models, using different skin and hair tones. It's 300x300 full color, and already split into training and test sets for you. You can learn more about the dataset and download it from [here](https://laurencemoroney.com/2021/08/23/yogapose-dataset.html)

To make it a little more challenging, I've rendered the images against a variety of backgrounds, including shadows!

Some examples:

![A girl in chair pose](/assets/girl1_chair138.jpg)
![A guy in warrior pose](/assets/guy2_warrior111.jpg)
![A girl in tree pose](/assets/girl3_tree090.jpg) 
![A girl in downward dog pose](/assets/girl2_dog033.jpg)
