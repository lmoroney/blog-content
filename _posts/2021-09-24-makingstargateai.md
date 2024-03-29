---
title: Making Stargate AI - Part One - The Approach
layout: article
tags: ai coding
---

Recently, I've been working on a very exciting project -- instigated by an idea from Brad Wright, creator of the 'Stargate' TV shows. Given how many attempts there have been for Machine Learning models to consume scripts and to attempt to come up with stories of their own, why couldn't we do something similar for Stargate -- where there are over 300 episodes of TV, several TV movies, and a lot more in the corpus of work.

The goal: Create an AI that writes a script for Stargate, and then get a number of the actors from the original show(s) together to do a table read.

If you've watched any AI-generated media, you'll immediately see that they rapidly deteriorate into gibberish. The famous 'Sunspring' movie is a great example. Check it out here: 

<div>{%- include extensions/youtube.html id='LY7x2Ihqjmc' -%}</div>

Sunspring was generated by a model called Jetson, and, as you'll see in the video, it was created using a technique called LSTM -- which stands for 'Long Short Term Memory,' and it's a way that a machine learning model can understand context in a sequence, and predict what should come next in that sequence.

This is good for writing text -- given a series of words -- it can predict the next likely word in the corpus. So, for example, if an LSTM was trained on Star Wars, and given the sequence "May the force," it would quite likely predict the next word to be "be". They're a lot of fun, but as you think about it, the reason why they become gibberish quickly is that they really only predict one word at a time.

So, if you were to start a sequence with 

"May the force", it would likely predict "be". I say 'likely,' because it will look at every possible word used in 'Star Wars,' and then calculate the probability of each one being the next word. Say 'be' has an 80% probability. Now you have "May the force be," and you want to get the *next* word. It will do the same -- and calculate the probability of every word used in Star Wars, and the most likely one is 'with,' with, say a 70% probability. Then the next word, of course will be 'you.'

But then what? 'be with you,' would be generated, but what would come next? This is a phrase that happens a lot in that corpus -- so "May the force be with you," is relatively easy to generate. The next word will be calculated based on the probabilities of every word in the corpus...so it's unlikely it will have a high probability like 'be,' 'with,' and 'you' had. And the next one would be even lower and so on. Thus, very quickly, low probability words would be spat out. And very quickly, the script would become gibberish.

For more detail -- check out my tutorial series [here](https://www.youtube.com/playlist?list=PLQY2H8rRoyvzDbLUZkbudP-MFQZwNmU4S), where I teach Natural Language Processing (NLP), and show how to create lyrics for traditional Irish songs with an LSTM.

### But Stargate neeeded something better
Realizing that this LSTM-based approach would get us into gibberish territory really quickly *and* knowing that we would be working with a limited set of characters who weren't all in all 300+ episodes together, I wanted to approach this a little differently.

So the first step was to understand the anatomy of a script.

Typically a script will look something like this:

![Example script page with annotations for Scene Heading, Action and Dialog](/assets/scriptsnippet.png)

Note the architecture of a script. There's a scene heading that sets the scene -- in this case we can see a hospital in LA in 1941. There's an *action description* that tells you what's going on, and then there's dialog -- what each character says.

So, what, I thought -- if I build models for *each* of these elements. Given a scene heading (for example INT. ATLANTIS GATEROOM,) what type of *action* description would follow? It might come up with something like "The Stargate is active.". Then I can choose to continue with the action, and it may come up with "An alarm goes off, incoming wormhole," and the story begins to take shape.

In the script, actors usually have some kind of response to the action, so, at that point, what if I trained a model for each character, and how they respond to action? Perhaps the character, in response to the above text might say "Unscheduled offworld activation,".

And then...what if I also created a model for each character that predicts how they might respond to dialog, as well as action. 

...and the idea of a cluster of models was born.

So, for the Stargate AI project, that's what we have.

- A model to predict action from a scene heading
- A model to predict more action from existing action
- A model to prediction action in response to dialog

And then, for each character:
- A model to predict dialog from action
- A model to predict dialog from dialog
- A model to continue dialog

Given that Stargate AI has three confirmed characters (McKay, Jackson, Carter,) this involved the creation and training of 12 models, each with between 1 and 2 million parameters.

...and there's more on the way! 

And to continue to push the state of the art with this, instead of using LSTM, I opted instead to use a *Transformer* architecture. I'll cover more of that in future articles, but the idea of that architecture is to predict sequences as opposed to individual words.

So, with a transformer, you would feed it a sequence like "May the force be with you," and it might come back with "and also with you," which is more realistic for a script-writing AI like we're trying to build for Stargate.

### The Data
I'll go into more detail on the Transformers in a future article, but, if you're into ML and AI, you know the hardest part is getting the data. So, in the video below I allude a little to how we did it.

I created a new XML-variant that I call SML (Script Markup Language) that allows me to pull dialog out of a scene (i.e. if I'm predicting dialog from action, it should be action in the same scene, not the previous one!) and from there train a model quickly an easily.

Here's a sample of SML:

```` 
<dialog character='CARTER'>
   <spoken s='4' i='4'>Mining what?</spoken>
</dialog>
<dialog character='MCKAY'>
   <spoken s='4' i='5'>Havent a clue. Whatever it was, they cleaned out the deposits and left.</spoken>
</dialog>
<dialog character='CARTER'>
   <spoken s='4' i='6'>So…?</spoken>
</dialog>
<dialog character='SHEPPARD'>
   <spoken s='4' i='7'>So, they think were like the Genii, and they want their cut.</spoken>
</dialog>
<dialog character='CARTER'>
   <spoken s='4' i='8'>Ah.</spoken>
</dialog>
<dialog character='KELLER'>
   <spoken s='4' i='9'>Theyre willing to move, but they have a list of demands a mile and a half long.</spoken>
</dialog>
<dialog character='SHEPPARD'>
   <spoken s='4' i='10'>And negotiating with alien settlements is not exactly why I joined the Air Force.</spoken>
</dialog>
<action s='4'>[Carter half-quirks a wry smile.]</action>

````

You can learn more in this video, where Brad, David Hewlett and I announce and discuss the project:

<div>{%- include extensions/youtube.html id='2yIEUfDUiHg' -%}</div>

In the next article, we'll talk Transformers, and I'll show some examples of how models came up with dialog for the characters!




