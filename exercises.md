### Exercises from the Natural Language Toolkit (NLKT)

First, import ```nltk.book```, a collection of texts you can practice your text mining on that accompanies the [NLKT textbook](https://www.nltk.org/book/). This text collection is already wrapped with the ```Text``` class that supports a variety of exploration, e.g. concordancing, counting, and collocation discovery. 

```python
from nltk.book import *
```

See what texts are imported. You can search for concordances in them.

```python
text1.concordance('monstrous')
```
```python
text2.concordance('monstrous')
```
Your Turn: Try searching for other words and in some of the other texts included in ```nltk.book```. For example, search *Sense and Sensibility* for the word affection, using ```text2.concordance('affection')```. Search the book of Genesis to find out how long some people lived, using ```text3.concordance('lived')```. You could look at text4, the *Inaugural Address Corpus*, to see examples of English going back to 1789, and search for words like *nation, terror, god* to see how these words have been used differently over time. We've also included text5, the *NPS Chat Corpus*: search this for unconventional words like *im, ur, lol*. 

```python
text3.concordance('lived')
```

A concordance permits us to see words in context. For example, we saw that monstrous occurred in contexts such as the ___ pictures and a ___ size . What other words appear in a similar range of contexts? We can find out by appending the term similar to the name of the text in question, then inserting the relevant word in parentheses.

```python
text1.similar('monstrous')
```
```python
text2.similar('monstrous')
```

The term common_contexts allows us to examine just the contexts that are shared by two or more words, such as monstrous and very. We have to enclose these words by square brackets as well as parentheses, and separate them with a comma:

```python
text2.common_contexts(['monstrous', 'very'])
```

Your Turn: Pick another pair of words and compare their usage in two different texts, using the similar() and common_contexts() functions.

We use the term len to get the length of something. Measure the length of some of the texts with len. 

```python
len(text3) #book of Genesis
```

Collocations are essentially just frequent bigrams (word pairs), except that we want to pay more attention to the cases that involve rare words and ignore stopwords. In particular, we want to find bigrams that occur more often than we would expect based on the frequency of the individual words. The collocations() function does this for us. 

```python
text4.collocations() # inaugurals
```

```python
text8.collocations() # personals
```
We have the option to specify measures for exactly how collocations are scored and retrieved as we will see in the section on collocations.
