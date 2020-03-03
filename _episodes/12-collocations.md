---
title: "Collocations"
teaching: 0
exercises: 0
questions:
- "How can I see what terms are often used together in a text or corpus?"
objectives:
- "We want to see words that collocate, occur together more often than by chance."
- "We will use the US Presidential Inaugural Addresses and which are provided with NLTK."
- "We will see what words co-occur within five words of each other."
- "We will then see which words appear more than ten times together."
- "We will then look at a measure to score the likelihood of these collocations being unusual." 

keypoints:
- "We used NLTK's ```BigramAssocMeasures()``` and ```BigramCollocationFinder``` to find the words commonly found together in this document set."
- "We then scored these collocations using ```bigram_measures.likelihood_ratio``` "
---

## Collocations

We may want to see what terms are often used together. We can do this by looking for collocations in a text, i.e. two word tokens occurring together in the text more often than would be expected by chance.

For this we need to import the ```nltk.collocations``` module and more specifically ```BigramAssocMeasures()``` and ```BigramCollocationFinder```. We allow a window of 5 words between collocated words.


```python
from nltk.collocations import BigramAssocMeasures
from nltk.collocations import BigramCollocationFinder

bigram_measures = BigramAssocMeasures()
finder = BigramCollocationFinder.from_words(inaugural_tokens, 5)
```

We then look for words that appear together 10 times or more.


```python
finder.apply_freq_filter(10)
```

A number of measures are available to score collocations or other associations including ```bigram_measures.likelihood_ratio```. We apply this measure below and show the top ten collocated tokens (occuring in a window of 5 tokens with a frequency of 10 or more).


```python
finder.nbest(bigram_measures.likelihood_ratio, 10)
```

    [('the', 'of'),
     ("'", 's'),
     ('.', 'The'),
     ('.', 'We'),
     ('United', 'States'),
     ('has', 'been'),
     ('.', '.'),
     ('have', 'been'),
     ('.', 'It'),
     (',', 'and')]


> ## Task 1: Change the code above to display collocations in the inaugural speeches after stopwords, punctuation and single digits have been removed. Refer back to Section 7 on frequency distribution for help.
>
> > ## Answer
> > ~~~python
> > nltk.download('stopwords')
> > from nltk.corpus import stopwords
> > remove_these = set(stopwords.words('english') + list(string.punctuation) + list(string.digits))
> > bigram_measures = BigramAssocMeasures()
> > filtered_text = [w for w in inaugural_tokens if not w in remove_these]
> > finder = BigramCollocationFinder.from_words(filtered_text, 5)
> > finder.apply_freq_filter(10)
> > finder.nbest(bigram_measures.likelihood_ratio, 7)
> > ~~~
> >
> {: .solution}
{: .challenge}