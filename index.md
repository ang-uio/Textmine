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
## Introduction to Jupyter Notebook

This course teaches programming in Python to text mine. It uses the application [Jupyter Notebook](https://jupyter.org) from the navigator [Anaconda](https://www.anaconda.com/) as the environment for Python. The Natural Language Toolkit, [NLTK](https://www.nltk.org/), a leading platform for building Python programs to work with human language data ("natural language processing" or NLP), also comes with Anaconda as one of many packages and libraries you can select to install and run in Jupyter Notebook, and will be used in this course. Python, Jupyter, and NLTK are open source and free.

Download and install [Anaconda](https://www.anaconda.com/) (free and easy to install). Open Anaconda, launch Jupyter Notebook from Anaconda, and select new Notebook in Python. 

![Starting a new notebook](/fig/start-notebook.png)

Once the new notebook opens you can give it a name by changing the word "Untitled" in the first line of the new notebook that opens up. You can see and change the location for where the notebook is saved in the browser window, see also the finder menu. 

![A new notebook](/fig/new-notebook.png)

You will see the first cell in your new notebook.  You can enter python code into this cell and press "Run" as long as it is marked as "Code" in the menu at the top of your notebook.  This will run your code and you will see any output created by the code immediately below it.

---
## Introduction to Python Fundamentals
Keypoints:
- "Use ```name = value``` to assign a value to a variable with a specific name in order to record it in memory"
- "Use the ```print(variable)``` function to print the value of the variable"
- "Create the list by giving it different values (```list-name['value1','value2','value3']```) and use a for loop to iterate through each value of the list"

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


> ### Task 1: Printing text
>
> Print a bit of text of your choice using print()
>
> > ### Answer
> > ```python
> > print("Humpty Dumpty sat on the wall")
> > ```
> >     Humpty Dumpty sat on the wall

> ### Task 2: Create a list
>
> Create a list containing different first names, iterate through them
>
> > ### Answer
> > ```python
> > names = ['Mary', 'John', 'Bob']
> > for name in names:
> >   print(name)
> > ```
> >     Mary
> >     John
> >     Bob

---
## Tokenising Text
Keypoints:
- "Tokenisation means to split a string into separate words and punctuation, for example to be able to count them."
- "Text can be tokenised using a tokeniser, e.g. the punkt tokeniser in NLTK."

### But first ... importing packages

Python has a selection of pre-written code that can be used. These come as in built functions and a library of packages of modules. We have already used the in-built function ```print()```.  In-built functions are available as soon as you start python. There is also a (software) library of modules that contain other functions, but these modules need to be imported.

For this course we need to import a few libraries into Python, including the [Natural Language Toolkit](https://www.nltk.org/) (NLTK). To do this, we need to use the ```import``` command and run ```import nltk```. We will also use ```numpy``` to represent information in arrays and matrices, ```string``` to process some strings, and ```matplotlib``` to visualise the output.

If there is a problem importing any of these modules you may need to revisit the appropriate install above.

```python
import nltk
import numpy
import string
import matplotlib.pyplot as plt
```

### Tokenising a string
In order to process text we need to break it down into tokens.  As we explained at the start, a token is a letter, word, number, or punctuation which is contained in a string.

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

> ### Task: Printing token in list
>
> Print the 13th token of the nursery rhyme (remember that a list index starts with 0).
>
> > ### Answer
> > ~~~python
> > print(lower_humpty_tokens[12])
> > ~~~
> >     fall

--
## Data Preparation

Text data comes in different formats that must be parsed into plain text for Python to read it. In this part of the lesson we will show you how to load a single document and how to load the text of an entire corpus into Python for further analysis. For more on corpora you can access and preprocessing of data, we recommend the chapters on [accessing text corpora](https://www.nltk.org/book/ch02.html) and [processing raw text](https://www.nltk.org/book/ch03.html) in the [NLKT textbook](https://www.nltk.org/book/). You may also want to consult the first couple of chapters in the textbook [Humanities Data Danalysis: Case Studies with Python](https://www.humanitiesdataanalysis.org/) regarding [data formats](https://www.humanitiesdataanalysis.org/getting-data/notebook.html#plain-text) and [preprocesing](https://www.humanitiesdataanalysis.org/vector-space-model/notebook.html#text-preprocessing).

### Download some data

Firstly, please download a dataset and make a note of where it is saved on your computer.  We need the path to dataset in order to load and read it for further processing.

We will use the [Medical History of British India](https://data.nls.uk/data/digitised-collections/a-medical-history-of-british-india/) collection provided by the [National Libarry of Scotland](https://www.nls.uk) as an example:

<img src="/fig/mhbi.png" width="700">

> This dataset forms the first half of the Medical History of British India collection, which itself is part of the broader India Papers collection held by the Library. A Medical History of British India consists of official publications varying from short reports to multi-volume histories related to disease, public health and medical research between circa 1850 to 1950. These are historical sources for a period which witnessed the transition from a humoral to a biochemical tradition, which was based on laboratorial science and document the important breakthroughs in bacteriology, parasitology and the developments of vaccines in a colonial context.

This collection has been made available as part of NLS's DataFoundry platform which provides access to a number of their digitised collections.

We are only interested in the text the Medical History of British India collection for this course so at the bottom of the website, download the "Just the text" data or [download it directly here](https://nlsfoundry.s3.amazonaws.com/text/nls-text-indiaPapers.zip).

Note that this dataset requires approx. 120 MB of free file space on your computer once it has been unzipped.  Most computers automatically uncompress ```.zip``` files as the one you have downloaded.  If your computer does not do that then right-click on the file and click on uncompress or unzip.

You should be left with a folder called ```nls-text-indiaPapers``` containing all the ```.txt``` files for this collection.  Please check that you have that on your computer and find out what its path is.  In my case it is ```/Users/balex/Downloads/nls-text-indiaPapers/```.

### Loading and tokenising a single document

You can use the ```open()``` function to open one of the files in the Medical History of British India corpus. You need to specify the path to a file in the downloaded dataset and the mode of opening it ('r' for read). The path will be different to the one below depending on where you saved the data on your computer.

The ```read()``` function is used to read the file. The file's content (the text) is then stored as a string variable called ```india_raw```.

You can then tokenise the text and convert it to lowercase. You can check it has worked by printing out a slice of the list ```lower_india_tokens```.

```python
file = open('/Users/annesabo/Downloads/nls-text-indiaPapers/74457530.txt','r')  # replace the path with the one on your computer
india_raw = file.read()
india_tokens = word_tokenize(india_raw)
lower_india_tokens = [word.lower() for word in india_tokens]
lower_india_tokens[0:10]
```
    ['no', '.', '1111', '(', 'sanitary', ')', ',', 'dated', 'ootacamund', ',']

### Loading and tokenising a corpus

We can do the same for an entire collection of documents (a corpus).  Here we choose a collection of raw text documents in a given directory.  We will use the entire Medical History of British India collection as our dataset.

To read the text files in this collection we can use the ```PlaintextCorpusReader``` class provided in the ```corpus``` package of NLTK.  You need to specify the collection directory name and a wildcard for which files to read in the directory (e.g. ```.*``` for all files) and the text encoding of the files (in this case ```latin1```).  Using the ```words()``` method provided by NLTK, the text is automatically tokenised and stored in a list of words. As before, we can then lowercase the words in the list.

```python
from nltk.corpus import PlaintextCorpusReader
corpus_root = '/Users/annesabo/Downloads/nls-text-indiaPapers/'
wordlists = PlaintextCorpusReader(corpus_root, '.*', encoding='latin1')
corpus_tokens = wordlists.words()
print(corpus_tokens[:10])
```
    ['No', '.', '1111', '(', 'Sanitary', '),', 'dated', 'Ootacamund', ',', 'the']


```python
lower_corpus_tokens = [str(word).lower() for word in corpus_tokens]
lower_corpus_tokens[0:10]
```
    ['no', '.', '1111', '(', 'sanitary', '),', 'dated', 'ootacamund', ',', 'the']


> ## Task 1: Print slice of tokens in list
>
> Print out a larger slice of the list of tokens in the Medical History of British India collection, e.g. the first 30 tokens.
>
> > ## Answer
> > ~~~python
> > print(corpus_tokens[:30])
> > ~~~
> >
> {: .solution}
{: .challenge}

> ## Task 2: Print slice of lowercase tokens in list
>
> Print out the same slice but for the lower-cased version.
>
> > ## Answer
> > ~~~python
> > print(lower_corpus_tokens[0:30])
> > ~~~

---
## Concordance Analysis or Keywords in Context (KWIC)

Next, we will display concordances for a particular token, i.e. all contexts a particular token appears in. We can do this by first importing the ```Text``` class, a wrapper which supports exploration and analysis through a variety of analyses, including by concordancing. See full description of ```Text``` class functionality at [NLTK](https://www.nltk.org/api/nltk.text.Text.html). The concordance list of a token is displayed using the ```concordance()``` method as shown below.

```python
from nltk.text import Text
t = Text(lower_india_tokens)
t.concordance('woman')
```

```
Displaying 20 of 20 matches:
s of age , a sweeper , who married a woman who had leprosy , and at the age of
e of sitabu , aged 40 , a muhammadan woman . her grand- father and father were
ung man deliberately married a leper woman , and became himself a leper at the
contrary . in no . 6 a man marries a woman whose grandfather and father had bee
 lepers . in no . 10 a man marries a woman whose father had died of leprosy . i
applies to these cases . in no . 2 a woman marries a man whose father and elder
n in the case of a man who marries a woman of notoriously leper family . in no
toriously leper family . in no . 5 a woman marries a man whose elder brother wa
d continued to cohabit with a native woman after she had been attacked with lep
isen from intermarriage of a man and woman in both of whom leprosy was heredita
s a leper ; he is now married to the woman , and they both live in the asylum .
een accompanied by a healthy looking woman , and by this means , although all h
editary transmission . in one case a woman got the disease about two years afte
 passed their thirtieth year , one a woman about 25 years of age , and the seve
 fracture of femur in middle third . woman well nourished and skin healthy , no
 ; had a brother with same disease . woman recovered and able to move about ; o
re or less related to each other . a woman got leprosy first from a leprous hus
s village assured me that before the woman returned home after her husband 's d
against it . this case was that of a woman with two leprous children , aged abo
ions had been lepers , who married a woman with tubercular leprosy , he being a
 ```

 In the output for the next bit of code which creates a concordance list for the word "he", we can see that there are many more results in the list than displayed on screen (```Displaying 25 of 170 matches```). The ```concordance()``` method only prints the first 25 results by default (or less if there are less).

```python
t = Text(lower_india_tokens)
t.concordance('he')
```

```
Displaying 25 of 170 matches:
leprosy treated by gurjun oil , which he was able to watch for a length of tim
 diminished . during these two months he gained three pounds in weight , which
does not seem much , considering that he did no work and was fairly well fed o
se from jail on the 23rd january 1876 he was again suffering from the sores th
n 5th and died on 20th october 1875 . he was seriously ill when he was brought
ober 1875 . he was seriously ill when he was brought to the hospital , and cou
itted on the 8th september 1875 , and he went home of his own accord on 20th d
is own accord on 20th december 1875 . he was much improved under treat- ment b
evalence of leprosy in the district , he had had but very few opportunities of
even half this number . the natives , he says , call every chronic skin diseas
in the legs , the feet and the ears . he has perfect taste , hearing , sight a
te laboured under it . the leper says he was quite free from leprosy until he
 he was quite free from leprosy until he associated with this man and took din
prosy of 15 years ' standing . states he had first gonorrha , then syphillis ,
been affected 6 years ; was well when he married . had two children who died ,
ve of the territory beyond the hubb . he had lost some parts of his hands and
 feet previous to his incarceration . he was treated with large doses of iodid
ease be removed . dr. bloomfield says he sent two interesting specimens of thi
ant medical college museum , but that he never heard of them after , nor did h
e never heard of them after , nor did he discover them in the museum when he v
d he discover them in the museum when he visited it afterwards . should the di
er and elder sister were lepers , and he himself became a leper at 30 years of
. his elder brother was a leper , and he himself became a leper at 32 . his wi
one year after she was affected , and he suffered from leprosy . no . 7.-the c
ied . afterwards , at the age of 43 , he him- self was attacked with leprosy .
```

You can specify the number of lines using an additional ```lines``` parameter, e.g.:

```python
t.concordance('he',lines=170)
```

> ### Task: Create a new concordance list
>
> Create a concordance list for a different search term, e.g. the word "great" or choose your own.
>
> > ### Answer
> >
> > ~~~python
> > t.concordance('great')
> > ~~~
