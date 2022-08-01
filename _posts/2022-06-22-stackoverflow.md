---
title: ML and the Stack Overflow 2022 Dev Survey 
layout: article
tags: ai coding
---


Here's the [survey](https://survey.stackoverflow.co/2022/) if you want to explore it for yourself.

First off, explore the sample size used. It’s over 73K developers. Then, understanding that there  are about 27M developers world wide, when running a statistical size calculator, like [this one](https://www.calculator.net/sample-size-calculator.html?type=1&cl=99&ci=1&pp=50&ps=27000000&x=91&y=34), you’ll see that for a survey to be 99% accurate, with a margin of error of only 1%, you need a sample size of around 17,000 

So when browsing the responses, particularly the ‘Professional Developers’ tabs, you’ll see that in general there are 3x to 4x the number of people answering than would be required for 99% accuracy with a 1% error margin!

## Insights:

### Programming Languages - no surprises

In the most popular technologies section, 67.9% of developers say they used JavaScript. The programming language in second place was Python with 43.51% (in between was HTML/CSS and SQL, but I’m going to focus on more traditional coding languages here)

![Chart of top coding langauges](/assets/sochart1.png)

That extrapolates to about *18 million* JavaScript developers, and *12 million* Python developers globally. Thus, as we build TensorFlow, these are the two main languages we support in developer documentation, education, etc. A surface of tens of millions of devs.

### ML Frameworks - the widening gap between TensorFlow and PyTorch

Looking into the ‘Other Frameworks and Libraries,’ one sees that 11.49% of Professional developers (i.e. about 3.1 Million) developers use TensorFlow, 7.61% (about 2M) use PyTorch and 6.47% (about 1.7M) use Keras.

![Chart of top frameworks](/assets/sochart2.png)

So, when it comes to *developers* using ML Frameworks, TensorFlow is clearly the *most popular* one, with about 50% more developers using it than PyTorch, and that’s not counting the Keras devs. 

It’s not clear from the survey how many of them are TF users, but even in the *worst case scenario*, where it would be zero of them — TensorFlow would still have *50% more developers than PyTorch* does. 

In the *best case*, where it would be all of them, then the population difference would be *more than double*: 4.8M versus 2M.

So, those folks that talk about PyTorch “eating TensorFlow’s lunch” simply aren’t supported by the numbers.

And amongst the next generation of developers? 17.6% of ‘learners’ are using TensorFlow, 10.71% using Keras, and 10.68% using PyTorch. 

The gap is *widening*.

![Chart of top coding langauges being learned](/assets/sochart3.png)

This isn’t a diss to PyTorch. I openly share that I’m excited that there is optionality in the ML space. If there was only 1 player, I would be very wary. But there isn’t. Competition is good. But it’s pretty clear that the conversation around ‘dominant’ frameworks is misplaced at best, and heavily biased at worst.

Oh, and a big Kudos to the folks over at Hugging Face. With 1.92% of the respondents saying they use it, or bit more than half a million developers. That’s impressive for a brand new offering that’s specifically targeted to a particular scenario, as opposed to broad APIs like TensorFlow or PyTorch.


### Loved and Dreaded Frameworks: Popularity doesn't translate to beloved

Indeed, when one looks at the Loved/Dreaded section — Hugging Face Transformers was the most beloved with a split of 72.2% loved versus 27.76% dreaded. PyTorch had a split of 68.29:31.71, and TensorFlow did a bit worse with 60.06:39.94. We have some work to do to make it more beloved. 

One thing to note here though is the number of respondents and their statistical relevance. So, for example, the PyTorch split is based on only 3952 answers, so it’s not going to be quite the 99% with a 1% margin of error.

![Chart of loved frameworks](/assets/sochart4.png)


### Future potential from people who 'want' - the widening accelerates

Perhaps the most insightful part, particularly when surveying the overall landscape is to look at what developers *want*

Looking at this section, we see that 15.53% of developers want TensorFlow (from a survey of 53.442, so still well in the 99% with a 1% error margin), equating to a population of 4.19M developers.

That’s a huge area of growth. The question was for those not already using it. So, if all of them to adopt, the TensorFlow developer community would grow from 3M to 7.19M.

![Chart of wanted frameworks](/assets/sochart5.png)

Similarly, the PyTorch community would grow from 2M to 4.39M, and the HuggingFace Transformers one could almost double to 1M.

So, it’s pretty clear — to me at least — the the ML framework community is vibrant, and that there are several players, the largest of which (by far!) is TensorFlow. 

And don’t just take my word for it — the World Economic Forum’s [report on the jobs of tomorrow](https://www3.weforum.org/docs/WEF_Jobs_of_Tomorrow_2020.pdf) only names 1 framework: TensorFlow, and only names 1 way of learning it: the [TensorFlow: In Practice specialization](https://www.coursera.org/professional-certificates/tensorflow-in-practice) on Coursera!

(Shameless self plug: I teach that course!)