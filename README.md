---
title: 'Assignment 10: Wikipedia Chatbot'
author: Assignment written by Nathan Shelly
date: 'Due Friday, May 31st'
geometry: margin=1in
urlcolor: cyan
---

You may work alone or in a pair. If you work in a pair make sure to document who you are working with both in google classroom and commented in your program.

The purpose of this assignment is to get more practice with "regular expressions" (regex) and expand your chatbot to answer questions about famous people/places/things via wikipedia. You can imagine the system that you are building to be the backend of a system like Siri or Alexa.

# Setup

Pip install nltk (like you did for Wikipedia in Assignment 8) then enter the Python interpreter and run the following commands:

```python
import nltk
nltk.download('punkt')
nltk.download('averaged_perceptron_tagger')
nltk.download('maxent_ne_chunker')
nltk.download('words')
```

# Example Usage

Below is an example of interacting with the chatbot:

```python
>>> from a10 import *
>>> query_loop()
Welcome to the Wikipedia chatbot!

Your query? when was grace hopper born

1906-12-09

Your query? when was anita borg born

1949-01-17

Your query? what is the polar radius of earth

6356.752
```

# Your job

Your job is to write at least 3 more functions (similar to `birth_date` and `polar_radius`) and add patterns to the `pa_list` to trigger the calling of these functions. Note how in the code we've provided the two action functions, `birth_date` and `polar_radius`, call corresponding helper functions named `get_birth_date` and `get_polar_radius`. Here the action functions take matches and extract the match to search on then call a function in order separate logic in our code and keep things clean. These helper functions are simply more complicated versions of helper functions like `movie_made_in_year` that we defined inside our functions in Assignment 3.

You might consider adding multiple patterns to correspond to one action to account for different ways in which one might ask a question to the chatbot. For example, `When was % born?` and `What is %'s birth date?`.

For ideas, spend some time looking at the 'infoboxes' on Wikipedia pages for various celebrities, universities, cities, countries, presidents, singers, etc.

In addition to writing the actual code, you need to demonstrate this code working by providing a transcript similar to the transcript above (paste and comment it out at the bottom of your `.py` file).

Notice that this code uses the regular expressions that you wrote in Assignment 9 to capture the radius of a plant and the birth date of a person from Wikipedia. Lines 106-142 of the starter code are the most important for you to understand -- the functions from Assignment 9 and the `pa_list`.

# Optional Extension

If you are satisfied with your new extended chatbot, consider ways to hold context. For example, imagine that we asked you "when was Michael Jackson born?" and then "when did he die?". How could you write your system to understand that 'he' is 'Michael Jackson'?

If you complete this, include a transcript demonstrating it at the end of your code.
