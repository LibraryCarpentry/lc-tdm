---
title: "Pre-processing Data Collections"
teaching: 0
exercises: 0
questions:
- "How can I load a file and tokenise it?"
- "How can I load a text collection made up of multiple text files and tokenise them?"
objectives:
- "Learn how to tokenise a text file and a collection of text files"
keypoints:
- "To open and read a file on your computer, the ```open()``` and ```read()``` functions can be used. "
- "To read an entire collection of text files you can use the ```PlaintextCorpusReader``` class provided by NLTK and its ```words()``` function to extract all the words from the text in the collection."
---

## Data Preparation

Text data comes in different forms.  You might want to analyse a document in one file or an entire collection of documents (a corpus) stored in multiple files.  In this part of the lesson we will show you how to load a single document and how to load the text of an entire corpus into Python for further analysis.

Firstly, please download a data set (and make a note of where it is saved).  We will use the Medical History of British India collection provided by the [National Libarry of Scotland](https://www.nls.uk) as an example:

https://data.nls.uk/data/digitised-collections/a-medical-history-of-british-india

### Loading and tokenising a single document

You can use the ```open()``` function to open one file in the Medical History of British India corpus. You need to specify the path to a file in the downloaded dataset and the mode of opening it ('r' for read). The path will be different to the one below depending on where you saved the data on your computer.

The ```read()``` function is used to read the file. The file's content (the text) is then stored as a string variable called ```india_raw```.

You can then tokenise the text and convert it to lowercase. You can check it has worked by printing out a slice of the list ```lower_india_tokens```.

```python
file = open('/Users/balex/Downloads/nls-text-indiaPapers/74457530.txt','r')
india_raw = file.read()
india_tokens = word_tokenize(india_raw)
lower_india_tokens = [word.lower() for word in india_tokens]
lower_india_tokens[0:10]
```
    ['no', '.', '1111', '(', 'sanitary', ')', ',', 'dated', 'ootacamund', ',']

### Loading and tokenising a corpus

We can do the same for an entire collection of documents (a corpus).  Here we choose a collection of raw text documents in a given directory.  We will use the entire Medical History of British India collection as our data set.

To read the text files in this collection we can use the ```PlaintextCorpusReader``` class provided in the ```corpus``` package of NLTK.  You need to specify the collection directory name and a wildcard for which files to read in the directory (e.g. ```.*``` for all files) and the text encoding of the files (in this case ```latin1```).  Using the ```words()``` method provided by NLTK, the text is automatically tokenised and stored in a list of words. As before, we can then lowercase the words in the list.

```python
from nltk.corpus import PlaintextCorpusReader
corpus_root = '/Users/balex/Downloads/nls-text-indiaPapers/'
wordlists = PlaintextCorpusReader(corpus_root, '.*', encoding='latin1')
corpus_tokens = wordlists.words()
print(corpus_tokens[:10])
```
    ['No', '.', '1111', '(', 'Sanitary', '),', 'dated', 'Ootacamund', ',', 'the']
<!--
~~~
$ cd
$ cd Desktop/shell-lesson
$ pwd
~~~
{: .bash}
~~~
/Users/riley/Desktop/shell-lesson
~~~
{: .output}


> ## Exercise title
>
> Add explanation
>
> > ## Answer
> > ~~~
> > code
> > ~~~
> > {: .bash}
> {: .solution}
{: .challenge}
-->

{% include links.md %}
