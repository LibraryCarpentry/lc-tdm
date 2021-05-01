---
title: "Tokenising Text"
teaching: 0
exercises: 0
questions:
- "What is tokenisation?"
- "How can a string of raw text be tokenised?"
objectives:
- "Learn how to tokenise text"
keypoints:
- "Tokenisation means to split a string into separate words and punctuation, for example to be able to count them."
- "Text can be tokenised using the a tokeniser, e.g., the punkt tokeniser in NLTK."
---
## Tokenising text

### But first ... importing packages

Python has a selection of pre-written code that can be used. These come as in-built functions and a library of packages of modules. We have already used the in-built function ```print()```. In-built functions are available as soon as you start python. There is also a (software) library of modules that contain other functions, but these modules need to be imported.

For this course we need to import a few libraries into Python. To do this, we need to use the ```import``` command.

NLTK is the tool which we'll be using to do much of the text processing in this workshop so we need to run ```import nltk```. We will also use ```numpy``` to represent information in arrays and matrices, ```string``` to process some strings and ```matplotlib``` to visualise the output.

If there is a problem importing any of these modules you may need to revisit the appropriate install in the prerequisites list.

```python
import nltk
import numpy
import string
import matplotlib.pyplot as plt
```

### Tokenising a string
In order to process tex,t we need to break it down into tokens. As we explained at the start, a token is a letter, word, number, or punctuation which is contained in a string.

To tokenise we first need to import the ```word_tokenize``` method from the ```tokenize``` package from NLTK which allows us to do this without writing the code ourselves.

```python
from nltk.tokenize import word_tokenize
```

We will also download a specific tokeniser that NLTK uses as default.  There are different ways of tokenising text and today we will use NLTK's in-built ```punkt``` tokeniser by calling:

```python
nltk.download('punkt')
```

Now we can assign text as a string variable and tokenise it.  We will save the tokenised output in a list using the ```humpty_tokens``` variable. We can inspect this list by inspecting the ```humpty_tokens``` variable.

```python
humpty_string = "Humpty Dumpty sat on a wall, Humpty Dumpty had a great fall; All the king's horses and all the king's men couldn't put Humpty together again."
humpty_tokens = word_tokenize(humpty_string)
# Show first 10 entries of the tokens list
humpty_tokens[0:10]
```
    ['Humpty', 'Dumpty', 'sat', 'on', 'a', 'wall', ',', 'Humpty', 'Dumpty', 'had']

As you can see, some of the words are uppercase and some are lowercase. To further analyse the data, for example counting the occurrences of a word, we need to normalise the data and make it all lowercase.

You can lowercase the strings in the list by going through it and calling the ```.lower()``` method on each entry. You can do this by using a for loop to loop through each word in the list.

```python
lower_humpty_tokens = [word.lower() for word in humpty_tokens]
# Show first 10 entries of the lowercased tokens list
lower_humpty_tokens[0:6]
```
    ['humpty', 'dumpty', 'sat', 'on', 'a', 'wall']

> ## Task: Printing token in list
>
> Print the 13th token of the nursery rhyme (remember that a list index starts with 0).
>
> > ## Answer
> > ~~~python
> > print(lower_humpty_tokens[12])
> > ~~~
> >     fall
> {: .solution}
{: .challenge}

{% include links.md %}
