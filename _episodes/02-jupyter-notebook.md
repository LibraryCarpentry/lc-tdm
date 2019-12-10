---
title: "Starting Jupyter Notebook"
teaching: 5
exercises: 0
questions:
- "What is Jupyter Notebook?"
- "How do I start it up?"
objectives:
- "Learn what Jupyter Notebook is"
- "Start Jupyter Notebook"
keypoints:
- "Jupyter Notebook is a tool to run small pieces of code and create visualisations easily. It is useful for running tutorials and lessons such as this one."
---

## Introduction to Jupyter Notebook

This course run is using [Jupyter Notebook](https://jupyter.org). It is an open-source web application that allows you to create and share documents that contain live code, equations, visualizations and narrative text.

### Starting Jupyter Notebook server
The start the lesson within a Jupyter Notebook you first need to start a Jupyter Notebook server.  To do that you need to open a terminal window and type:

~~~
jupyter notebook
~~~

This should open up a browser window containing the base directory of where you can store your notebook on your computer.

You can learn how to open a terminal window on your computer in the setup instructions for this lesson.

### Creating a new notebook

To create a new notebook you need to select a location for it on your computer via the browser window that opened up and click on "New" in the top right corner of the browser.  You also need to select Python 3 to do so.

![Starting a new notebook](../fig/start-notebook.png)

Once the new notebook opens you can give it a name by changing the word "Untitled" in the first line of the new notebook that opens up.

![A new notebook](../fig/new-notebook.png)

You can see the first cell in your new notebook.  You can enter python code into this cell and press "Run" as long as it is marked as "Code" in the menu at the top of your notebook.  This will run your code and you will see any output created by the code immediately below it.

To check that it works, tell the notebook to print the word "Works!" by typing the following code into the cell:

~~~
print("Works!")
~~~

and press run.  The output of your code appears below the cell.

{% include links.md %}
