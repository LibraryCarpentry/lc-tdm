---
title: "Counting Tokens in Text"
teaching: 0
exercises: 0
questions:
- "How can I count tokens in text?"
objectives:
- "Learn how to count tokens in text."
keypoints:
- "To count tokens, one can make use of NLTK's ```FreqDist``` class from the ```probability``` package. The ```N()``` method can then be used to count how many tokens a text or corpus contains."
- "Counts for a specific token can be obtained using ```fdist[\"token\"]```."
---


## Counting tokens in text

You can also do other useful things like count the number of tokens in a text, determine the number and percentage count of particular tokens and plot the count distributions as a graph. To do this we have to import the ```FreqDist``` class from the NLTK ```probability``` package.  When calling this class, a list of tokens from a text or corpus needs to be specified as a parameter in brackets.

```python
from nltk.probability import FreqDist
fdist = FreqDist(lower_india_tokens)
fdist
```
    FreqDist({'the': 5923, ',': 5332, '.': 5258, 'of': 4062, 'and': 2118, 'in': 2117, 'to': 1891, 'is': 1124, 'a': 1049, 'that': 816, ...})

The results show the top most frequent tokens and their frequency count.

We can count the total number of tokens in a corpus using the ```N()``` method:

```python
fdist.N()
```
    93571

And count the number of times a token appears in a corpus:

```python
fdist['she']
```
    26

We can also determine the relative frequency of a token in a corpus, so what % of the corpus a term is:

```python
fdist.freq('she')
```
    0.0002778638680787851

If you have a list of tokens created using regular expression matching as in the previous section and you'd like to count them then you can also simply count the length of the list:

```python
len(womaen_strings)
```
    43

Frequency counts of tokens are useful to compare different corpora in terms of occurrences of different words or expressions, for example in order to see if a word appears a lot rarer in one corpus versus another.  Counts of tokens, documents and a entire corpus can also be used to compute simple pairwise document similarity of two documents (e.g. see Jana Vembunarayanan's [blogpost](https://janav.wordpress.com/2013/10/27/tf-idf-and-cosine-similarity/) for a hands-on example of how to do that).

<!--
> ## Task: Count the frequency of a particular token.
>
> Change the word "she" to something else to see how the frequency changes.
>
> > ## Answer
> > ~~~python
> > fdist.freq('he')
> > ~~~
> {: .solution}
{: .challenge}-->

{% include links.md %}
