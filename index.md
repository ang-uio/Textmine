## Introduction to Text Mining

[What is text mining?](https://www.ub.uio.no/english/libraries/dsc/research-methods/text-mining/)

"Text Mining is the discovery by computer of new, previously unknown information, by automatically extracting information from different written resources... The difference between regular data mining and text mining is that in text mining the patterns are extracted from natural language text rather than from structured databases of facts." - [from What is Text Mining?](https://people.ischool.berkeley.edu/~hearst/text-mining.html) by [Marti Hearst](https://en.wikipedia.org/wiki/Marti_Hearst)

[Types of text mining and digital analysis of text](https://www.ub.uio.no/english/libraries/dsc/research-methods/text-mining/text-mining-types.html)

[Tools and software bundles for text mining](https://www.ub.uio.no/english/libraries/dsc/research-methods/text-mining/tools-software-bundles.html)

Text mining requires data - a note on the value of platforms such as [NLTK](https://www.nltk.org/) and [DH-Lab](https://www.nb.no/dh-lab/).

Quick look at DH-Lab Tools and [Voyant Tools](https://voyant-tools.org/) - option to revert to these during the course.

Learning a programming language is like learning any new language. It requires copying, repeating, using a dictionary, practicing, learning enough of the ‘grammar’ of the language to detect typos and mistakes.

- Learn how to look things up ([textbooks](https://www.nltk.org/book/), [online resources](https://github.com/sgsinclair/alta/blob/2eb10ab6787d032e317ce883fb0bc3427406333d/ipynb/Useful%20Resources.ipynb), [published tutorials](https://programminghistorian.org/en/lessons/?topic=python), [forums](https://stackoverflow.com/)).

> Learning goals: 
> 
> Get a sense of how the Python program works (the math behind it with strings and loops etc.).
> 
> Get a feel for how Python code can be used to text mine.

---
### Introduction to Jupyter Notebook

This course teaches programming in Python to text mine. It uses the application [Jupyter Notebook](https://jupyter.org) from the navigator [Anaconda](https://www.anaconda.com/) as the environment for Python. The Natural Language Toolkit, [NLTK](https://www.nltk.org/), a leading platform for building Python programs to work with human language data ("natural language processing" or NLP), also comes with Anaconda as one of many packages and libraries you can select to install and run in Jupyter Notebook, and will be used in this course. Python, Jupyter, and NLTK are open source and free.

Download and install [Anaconda](https://www.anaconda.com/) (free and easy to install). Open Anaconda, launch Jupyter Notebook from Anaconda, and select new Notebook in Python. 

![Starting a new notebook](/fig/start-notebook.png)

Once the new notebook opens you can give it a name by changing the word "Untitled" in the first line of the new notebook that opens up. You can see and change the location for where the notebook is saved in the browser window, see also the finder menu. 

![A new notebook](/fig/new-notebook.png)

You will see the first cell in your new notebook.  You can enter python code into this cell and press "Run" as long as it is marked as "Code" in the menu at the top of your notebook.  This will run your code and you will see any output created by the code immediately below it.

---
### Keypoints:
- "Use ```name = value``` to assign a value to a variable with a specific name in order to record it in memory"
- "Use the ```print(variable)``` function to print the value of the variable"
- "Create the list by giving it different values (```list-name['value1','value2','value3']```) and use a for loop to iterate through each value of the list"
---

## Introduction to Python Fundamentals

This introduction to Python will give you a basic understanding of the language and its logic, which is important for understanding all the steps that follow through the course. You may also want to confer with the recommended textbooks, [Natural Language Processing with Python: Analyzing Text with the Natural Language Toolkit](https://www.nltk.org/book/) and [Humanities Data Analysis: Case Studies with Python](https://www.humanitiesdataanalysis.org/index.html). The first chapters have good introductions: ["Language Processing and Python"](https://www.nltk.org/book/ch01.html) and ["What you should know"](https://www.humanitiesdataanalysis.org/introduction-cook-books/notebook.html#what-you-should-know) on variables, strings, loops, lists, dictionaries, conditional expressions (if, elif, else), and reading files. 

### Printing text

We first want to test that Python works by asking it to print a string, so type ```print("Hello World")``` into the next Jupyter Notebook cell as shown below and run it as code.

```python
print("Hello World")
```
    Hello World

### Variables and how to assign them

In Python, you can assign information to variables. A variable is a memory location used to hold data which has a name associated with it.  You can think of it like a box which can contain information and which also has a name, so you can refer to it in code.

For example we can put the string "text mining" into the box named "text".

We do that by assigning the string to the variable named text. When assigning variables in python, the name of the variable is on the left followed by an equal sign and the value of the variable, as follows:


```python
text = "Text Mining"
```

You can see the content of the variable (what's in the box) by printing the value of it using the ```print()``` function and the variable name as shown:

```python
print(text)
```
    Text Mining

In addition to strings we can assign other data types such as numbers and floats to variables.

```python
text = "Text Mining"  # An example of a string
number = 42  # An example of an integer
pi_value = 3.1415  # An example of a float (a number with a decimal)
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
sentence = ['Just', 'think', 'happy','thoughts', 'and', 'you', '’ll', 'smile', '.']
print(sentence) # print all elements

```
    ['Just', 'think', 'happy', 'thoughts', 'and', 'you', '’ll', 'smile', '.']

The list holds an ordered sequence of elements (in this case words or punctuation) and each element can be accessed using its index or position in the list.  To do that you need to specify the index.

> ## Note
> Python indexes start with 0 instead of 1.  So the first element in the list is called using a 0 in square brackets after the name of the list
{: .callout}

```python
print(sentence[0]) # print the first element
```
    Just

You can also print a slice of the list (e.g. the first two elements of the list):

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

The syntax for a for loop starts with ```for x in y:``` where y is the thing you want to loop through (in our case a list) and x is a new variable which each element of y is assigned to while looping.  So when looping, x keeps getting overwritten by the next element of y until the end of y is reached.

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

In the following example, the code specifies that if the sentence list contains 5 elements then print text to confirm that, else if the list contains more than 5 elements then print text to say it does.  If neither of those two conditions are true (else) which means the sentence list contains less than 5 elements, then print something saying that is the case.  Finally print the entire list to show which elements it contains.  The last line of code is not indented as it is supposed to run independent of the if/elif/else statements.

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

### Dictionary

A dictionary works a lot like a list but it contains 'key/value' pairs. A key acts as a name for a single or a set of values in the dictionary.

In the example below the values are integers (e.g. counts).  So a dictionary could be used to store the number of times (the value) a word (the key) occurs in a text.

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
