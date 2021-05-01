---
title: "Python Fundamentals"
teaching: 0
exercises: 0
questions:
- "How can I create a new variable in Python?"
- "How do I print the value of a variable?"
- "How can I create a list and iterate through it?"

objectives:
- "Learn Python fundamentals"
- "Learn Python syntax"
- "Run simple python code"
keypoints:
- "Use ```name = value``` to assign a value to a variable with a specific name in order to record it in memory"
- "Use the ```print(variable)``` function to print the value of the variable"
- "Create the list by giving it different values (```list-name['value1','value2','value3']```) and use a for loop to iterate through each value of the list"
---

## Introduction to Python

Python is a programming language. We will use this as a way to interact with and analyse text documents. We can use Python either through the command line in your terminal window, by writing Python scripts or via Jupyter Notebook. In this lesson we will be using it via Jupyter Notebook.

This introduction to Python is important for understanding all the steps that follow in the text mining lesson.  If you are new to programming it may not be entirely clear why you need to learn Python first. Bear with us, you will soon understand why it is needed and is useful and it will help to speed things up later-on.

We will limit this introduction to the level of Python required for this lesson for a more in-depth introduction to Python, we'd recommend the following [Library Carpentries lesson]{https://librarycarpentry.org/lc-python-intro/}.

### Printing text

We first want to test that the Python works by asking it to print a string, so type ```print("Hello World")``` into the next Jupyter Notebook cell as shown below and run it as code.

```python
print("Hello World")
```
    Hello World

### Variables and how to assign them

In python, you can assign information to variables. A variable is a memory location used to hold data which has a name associated with it.  You can think of it like a box which can contain information and which also has a name, so you can refer to it in code.

For example, we can put the string "text mining" into the box named "text".

We do that by assigning the string to the variable named text. When assigning variables in python, the name of the variable is on the left followed by an equal sign and the value of the variable, as follows:


```python
text = "Text Mining"
```

You can see the content of the variable (what's in the box) by printing the value of it using the ```print()``` function and the variable name as shown:

```python
print(text)
```
    Text Mining

In addition to strings, we can assign other data types such as numbers and floats to variables.

```python
text = "Text Mining"  # An example of a string
number = 42  # An example of an integer
pi_value = 3.1415  # An example of a float
```

In this lesson we will be concentrating mainly on strings.

> ## Note
> Whenever something is followed by the ```#``` sign in Python code then it is a comment and not part of the code.  Comments are used to explain the code but are not needed to run it.
{: .callout}

### A list

Data can be grouped together in an ordered way using a list. Lists are very common data structures used in Python, for example to represent text.

In the following example the list named "sentence" stores all the words and punctuation of the sentence "This is an example sentence."

Lists are created by typing comma separated values inside square brackets.  You can print out all elements in the list.


```python
sentence = ['Just', 'think', 'happy', 'thoughts', 'and', 'you', '’ll', 'smile', '.']
print(sentence) # print all elements

```
    ['Just', 'think', 'happy', 'thoughts', 'and', 'you', '’ll', 'smile', '.']

The list holds an ordered sequence of elements (in this case words or punctuation) and each element can be accessed using its index or position in the list.  To do that you need to specify the index.

> ## Note
> Python indexes start with 0 instead of 1.  So, the first element in the list is called using a 0 in square brackets after the name of the list
{: .callout}

```python
print(sentence[0]) # print the first element
```
    Just

You can also print a slice of the list (e.g., the first two elements of the list):

```python
sentence[0:2]
```
    ['Just', 'think']


You can delete an item in the list by using the ```pop()``` function specifying the index of the element (unless you want to remove the last one).


```python
sentence.pop(7)
print(sentence) # prints the entire list at once
```

    ['Just', 'think', 'happy', 'thoughts', 'and', 'you', '’ll', '.']


Items can be added to a list either by inserting them at a specific position (index) or by appending them to the end of the list.


```python
sentence.insert(7,'fly')
print(sentence)
sentence.append('[J.B. Barrie]')
print(sentence)
```
    ['Just', 'think', 'happy', 'thoughts', 'and', 'you', '’ll', 'fly', '.']
    ['Just', 'think', 'happy', 'thoughts', 'and', 'you', '’ll', 'fly', '.', '[J.B. Barrie]']

### A for loop

A for loop can be used to access the elements in a list one at a time.

The syntax for a for loop starts with ```for x in y:``` where y is the thing you want to loop through (in our case a list) and x is a new variable which each element of y is assigned to while looping. So, when looping, x keeps getting overwritten by the next element of y until the end of y is reached.

The code after the initial line then specifies what is to be done with each element of y. This needs to be indented using a tab so that Python knows the instructions that follow need to be executed for each element.

For example, you can loop through the sentence list by assigning each element to the word variable and then print each element by calling the ```print()``` function:


```python
for word in sentence:
    print(word) # prints each element of the list one after the other
```
    Just
    think
    happy
    thoughts
    and
    you
    ’ll
    fly
    .
    [J.B. Barrie]

### if/elif/else statements

An if/elif/else statement can be used to condition some code on something being true or false.  This is useful when wanting to only run some code if a specific condition is met or for running different bits of code depending on what condition is met.

If the test that follows the statement is true, then its body (i.e., the lines indented underneath it) are executed.  If the test is false then the indented code is not executed and the programme continues.

In the following example, the code specifies that if the sentence list contains 5 elements, then print text to confirm that, else if the list contains more than 5 elements then print text to say it does.  If neither of those two conditions are true (else) which means the sentence list contains less than 5 elements, then print something saying that is the case.  Finally print the entire list to show which elements it contains.  The last line of code is not indented as it is supposed to run independent of the if/elif/else statements.

We use the ```len()``` function to count the length of the list which returns an integer and we also use operators as part of the tests (```==``` for is equal to and ```>``` for is greater than).

```python
if len(sentence) == 5:
    print("The sentence list contains 5 tokens.")
elif len(sentence) > 5:
    print("The sentence list contains more than 5 tokens.")
else:
    print("The sentence list contains less than 5 tokens.")

print(sentence)
```
    The sentence list contains more than 5 tokens.
    ['Just', 'think', 'happy', 'thoughts', 'and', 'you', '’ll', 'fly', '.', '[J.B. Barrie]']


### A tuple

A tuple is similar to a list as it is an ordered sequence of elements. The difference is that tuples can't be changed once created and they are created by placing comma-separated values inside parentheses.

```python
colour_tuple = ('blue', 'green', 'red')
print(colour_tuple[1]) # prints the 2nd entry in the tuple
```
    green

### Dictionary

A dictionary works a lot like a list but it contains 'key/value' pairs. A key acts as a name for a single or a set of values in the dictionary.

In the example below the values are integers (e.g., counts). So, a dictionary could be used to store the number of times (the value) a word (the key) occurs in a text.

```python
pets = {'cats':45, 'dogs':24, 'mice':33}
print(pets['cats']) # prints the value of the key 'cats'
```
    45

We can use a for loop to print the keys and values of a dictionary:

```python
for key, value in pets.items():
    print(key, value)
```
    cats 45
    dogs 24
    mice 33


> ## Task 1: Printing text
>
> Print a bit of text of your choice using print()
>
> > ## Answer
> > ```python
> > print("Humpty Dumpty sat on the wall")
> > ```
> >     Humpty Dumpty sat on the wall
> {: .solution}
{: .challenge}

> ## Task 2: Create a list
>
> Create a list containing different first names, iterate through them
>
> > ## Answer
> > ```python
> > names = ['Mary', 'John', 'Bob']
> > for name in names:
> >   print(name)
> > ```
> >     Mary
> >     John
> >     Bob
> {: .solution}
{: .challenge}

{% include links.md %}
