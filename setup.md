---
title: Setup
---

# Computer Setup and Software Installs
This course run is entirely using [Jupyter Notebook](https://jupyter.org).  It is an open-source web application that allows you to create and share documents that contain live code, equations, visualizations and narrative text.  We will therefore only be using the terminal window on your computer for the initial setup and software installation.

### Terminal Setup
__Linux:__ Look for Terminal in your applications and click on it to open it.  
__macOS:__ Bash is the default shell in all versions of macOS, you do not need to install anything. Open the Terminal application from ``/Applications/Utilities`` or using Spotlight search.  
__Windows:__ Open the Start Menu, type ```command``` or ```cmd``` in the search field, and then press Enter or click on the Command Prompt shortcut.

### Software Installs for Day 1

For this course, we ask you to install Miniconda and as well as the a series of software packages with it (jupyter notebook, nltk, numpy, matplotlib, wordcloud, pandas and networkx).  We also ask you to install the Stanford NER tagger (which is needed for day 2 of the course).  See instructions below.  Please take time to install these different things prior to the course.

__1. Install Miniconda__

Got to https://docs.conda.io/en/latest/miniconda.html and download the correct version.  We will be working with Python version 3.7, so you need to select the appropriate version of Miniconda for your operating system with Python 3.7.

For all of the software packages to be installed next (using conda) you will need to proceed through the terminal installation by pressing "y" when prompted on Linux/Mac or install them via the Anaconda prompt on Windows.

__2. Install Jupyter Notebook__

Windows: install jupyter notebook via the Anaconda prompt  
macOS/Linux: go to a terminal window and run the following command:


~~~
conda install -c anaconda jupyter
~~~
{: .bash}

__3. Install NLTK__

Windows: install NLTK via the Anaconda prompt  
macOS/Linux: run the following command in your terminal:


~~~
conda install -c anaconda nltk
~~~
{: .bash}

__4. Install numpy__

Windows: install numpy via the Anaconda prompt  
macOS/Linux: run the following command in your terminal:


~~~
conda install numpy
~~~
{: .bash}

__5. Install matplotlib__

Windows: install matplotlib via the Anaconda prompt  
macOS/Linux: run the following command in your terminal


~~~
conda install -c conda-forge matplotlib
~~~
{: .bash}

__6. Install wordcloud__

Windows: install wordcloud via the Anaconda prompt  
macOS/Linux: run the following command in your terminal:


~~~
conda install -c conda-forge wordcloud
~~~
{: .bash}

### Software Installs for Day 2

__7. Install Stanford NER tagger__

Go to the following URL and if your computer doesn't automatically download it, then download it yourself.

https://nlp.stanford.edu/software/stanford-ner-2018-10-16.zip

You can put the tagger anywhere you like.  For this workshop we recommend you put it into your Download folder.  The directory path to the Stanford tagger is needed to be able to run some of the exercises on day 2.

__8. Install pandas__

Windows: install pandas via the Anaconda prompt  
macOS/Linux: run the following command in your terminal:


~~~
conda install pandas
~~~
{: .bash}

__9. Install networkx__

Windows: install networkx via the Anaconda prompt  
macOS/Linux: run the following command in your terminal:


~~~
conda install networkx
~~~
{: .bash}

{% include links.md %}
