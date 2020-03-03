---
title: "Plotting Frequency Over Time"
teaching: 0
exercises: 0
questions:
- "How can I extract and plot the frequency of specific terms over time?"
objectives:
- "We will use a NLTK’s ConditionalFreqDist class to extract the frequency of defined words."
- "We will use the US Presidential Inaugural Addresses and which are provided with NLTK."
keypoints:
- "Here we extracted the terms and the years from the files using NLTK's ```ConditionalFreqDist``` class from the ```nltk.probability``` package"
- "We then plotted these on a graph to visualise how the use changes over time"
---

## Plotting frequency over time

Similarly to lexical dispersion, you can also plot frequency of terms over time.  This is similarly to the [Google n-gram visualisation](https://books.google.com/ngrams) for the Google Books corpus but we will show you how to do something similar for your own corpus.

You first need to import NLTK's ```ConditionalFreqDist``` class from the ```nltk.probability``` package. To generate the graph, you have to specify the list of words to be plotted (see targets) and the x-axis labels (in this case the year the inaugural was held which appears at the start of each file: ```fileid[:4]```).

The plot is created by:
* looping through each file (speech)
* then looping through each word in each speech
* then looping though the list of specified target words and
* checking if each target word matches the start of each word in the speeches (after being lower-cased).

The ```ConditionalFreqDist object``` (```cfd```) stores the number of times each of the target words appear in the each of the speaches and the ```plot()``` method is used to visualise the graph.


```python
from nltk.probability import ConditionalFreqDist

# type this to set the figure size
plt.rcParams["figure.figsize"] = (12, 9)

targets=['great','good','tax','work','change', 'wom[ae]n']

cfd = nltk.ConditionalFreqDist((target, fileid[:4])
    for fileid in inaugural.fileids()
    for word in inaugural.words(fileid)
    for target in targets
    if word.lower().startswith(target))
cfd.plot()
```

<img src="../fig/output_12_0.png" width="700">

   
> ## Task 1: See how the plot changes when choosing different target words.
> > ## Answer
> >
> > ~~~python
> > plt.rcParams["figure.figsize"] = (12, 9)
> > targets=['god','work']
> > cfd = nltk.ConditionalFreqDist((target, fileid[:4])
> > 	for fileid in inaugural.fileids()
> > 	for word in inaugural.words(fileid)
> >    	for target in targets
> >     if word.lower().startswith(target))
> > cfd.plot()
> > ~~~
> >
> {: .solution}
{: .challenge}
    
> ## Task 2: Use regular expression searching to search for target words exactly instead of matching on words that start with the target words.
> > ## Answer
> > ~~~python
> > plt.rcParams["figure.figsize"] = (12, 9)
> > targets=['m[ea]n']
> > cfd = nltk.ConditionalFreqDist((target, fileid[:4])
> >     for fileid in inaugural.fileids()
> >     for word in inaugural.words(fileid)
> >     for target in targets
> >     if word.lower().startswith(target))
> > cfd.plot()
> > ~~~
> >
> {: .solution}
{: .challenge}