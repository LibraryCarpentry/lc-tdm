---
title: "Searching Text using Regular Expressions"
teaching: 0
exercises: 0
questions:
- "How can I search for tokens in text more flexibly? For example, to find all mentions of ```woman``` and ```women```."
objectives:
- "Learn how to search for tokens in a data set using regular expressions"
keypoints:
- "To search for tokens in text using regular expressions you need the ```re``` module and its ```search``` function."
- "You will need to learn how to construct regular expressions.  E.g. you can use a wildcard ```*``` or you can use a range of letters, e.g. ```[ae]``` (for a or e), ```[a-z]``` (for a to z), or numbers, e.g. ```[0-9]``` (for all single digits) etc.  Regular expressions can be very powerful if used correctly.  To find all mentions of the words ```woman``` or ```women``` you need to use the following regular expression ```wom[ae]n```."
---

## Searching text using regular expressions

This episode provides a taster to the use of regular expression searching.  For a more detailed overview and use of regular expressions, we refer to the Programming Historian lesson [Understanding Regular Expressions](https://programminghistorian.org/en/lessons/understanding-regular-expressions).

You may want to look for the word "women" as well a "woman" in a corpus simultaneously, to find out how many times they occur. You would do this using regular expressions. Regular expressions define a search term that can have some variety in it.  Do use regular expression search in python, you first need to import the ```re``` module.

```python
import re
```

The next line is a bit more complex combining a for loop and and an if statement so let's explain this in a bit more detail.

The code first goes through each element in the ```lower_india_tokens``` list using a for loop and assigning each element in that list to the variable```w```. The if statement then specifies to only return true if the strings assigned to ```w``` matches "woman" or "women".  If that is the case then the word is added to the ```womaen_strings``` list.

The regular expression search string ```^wom[ae]n$``` contains square brackets to indicate that the letter to match could be "a" or "e" (so either woman or women).  ```^``` means start of string and ```$``` means end of string, so the search is for the exact tokens "women" or "woman" but not for words containing them.

You can see all the strings found in the corpus assigned to the ```womaen_strings``` list by printing it.

```python
womaen_strings=[w for w in lower_india_tokens if re.search('^wom[ae]n$', w)]
print(womaen_strings)
```
    ['women', 'women', 'women', 'woman', 'woman', 'woman', 'woman', 'woman', 'woman', 'woman', 'woman', 'woman', 'women', 'woman', 'women', 'women', 'woman', 'women', 'woman', 'women', 'woman', 'woman', 'woman', 'woman', 'women', 'women', 'women', 'women', 'women', 'woman', 'woman', 'women', 'women', 'women', 'women', 'women', 'women', 'woman', 'woman', 'women', 'women', 'women']

You can see how the search results change if you remove the ```^``` and ```$``` characters from the regular expression.

Now that the results are stored in a list you can count them. We will see how to do that in the next section of the course.

```python
womaen_strings=[w for w in lower_india_tokens if re.search('wom[ae]n', w)]
print(womaen_strings)
```
    ['women', 'women', 'women', 'woman', 'woman', 'woman', 'woman', 'woman', 'woman', 'woman', 'woman', 'woman', 'women', 'woman', 'women', 'women', 'woman', 'women', 'woman', 'women', 'washerwoman', 'woman', 'woman', 'woman', 'woman', 'women', 'women', 'women', 'women', 'women', 'woman', 'woman', 'women', 'women', 'women', 'women', 'women', 'women', 'woman', 'woman', 'women', 'women', 'women']

Regural expressions can be very specific and we will not cover them in detail here but they are very powerful to carry out complex searches, e.g. find all tokens starting with ```a``` and are 12 characters long (```.``` means a character). Or find all tokens which are 13 characters long but that do not start with a lower case letter (```[^a-z]``` means not the letters a-z).

```python
[w for w in lower_india_tokens if re.search('^a............$', w)]
```
    ['antiscorbutic',
     'approximately',
     'approximately',
     'agriculturist',
     'ages.-chiefly',
     'approximately',
     'accommodation']

```python
[w for w in lower_india_tokens if re.search('^[^a-z]............$', w)]
```
    ['24-pergunnahs',
     '19.-commenced',
     '24-pergunuahs',
     '24-pergunnahs',
     '24-pergunnahs',
     '1875.-patches']

> ## Task: Search for specific tokens using regular expressions
>
> Search for all tokens starting with the string "man" or "men"
>
> > ## Answer
> > ~~~python
> > maen_strings=[w for w in lower_india_tokens if re.search('m[ae]n', w)]
> > print(maen_strings)
> > ~~~
> >
> {: .solution}
{: .challenge}

{% include links.md %}
