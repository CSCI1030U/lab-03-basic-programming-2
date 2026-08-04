# Lab 03 - Basic Python: Strings, Lists, and Dictionaries

In this lab, we'll practise the tools from this week's lectures: pulling apart and
building up **strings** and collecting values in **lists** (the three core parts),
with a stretch that builds a **dictionary**. You'll write four small functions and
check them against a set of automated tests.

**Time:** this lab is meant to be finished in the 80-minute session. If you don't
finish, you may keep working during the week and submit any time up to the **first 10
minutes of next week's lab**.  After 10 minutes, though, the lab will not be accepted,
to avoid a cascade effect.

## Getting Started

Accept the GitHub Classroom assignment invitation in Canvas (the link is in the lab
assignment on Canvas), which will clone your own copy of the repository. In the folder
where you keep your CSCI 1030U labs:

```
git clone https://github.com/CSCI1030U/lab03-your-username
```

## Instructions

You will edit **`lab03.py`**. The four function definitions are already written for
you - **do not rename them or change their arguments**, because the tests call them by
name. Replace each `pass` with your code, and use **`return`** to send the answer back
(not `print`).

### Part 1 - `pig_latin(word)`

Write the body of `pig_latin`, which takes a single lowercase `word` and returns its
Pig Latin form:

- if the word starts with a **vowel** (`a`, `e`, `i`, `o`, `u`), add `"way"` to the end;
- otherwise, move the **first letter to the end** and add `"ay"`.

Hint: string slicing helps - `word[0]` is the first letter and `word[1:]` is the rest.

```python
pig_latin("banana")   # returns "ananabay"
pig_latin("python")   # returns "ythonpay"
pig_latin("apple")    # returns "appleway"
```

### Part 2 - `word_lengths(sentence)`

Write the body of `word_lengths`, which takes a `sentence` and returns a **list**
containing the length of each word. Words are separated by spaces.

Hint: `sentence.split()` breaks the sentence into a list of words. Start with an empty
list and `.append()` each word's length as you loop.

```python
word_lengths("the quick brown fox")   # returns [3, 5, 5, 3]
word_lengths("hello")                 # returns [5]
word_lengths("")                      # returns []
```

### Part 3 - `reverse_words(sentence)`

Write the body of `reverse_words`, which returns `sentence` with the **order of its
words reversed** (the letters within each word stay the same).

Hint: `sentence.split()` gives you a list of words, and you can reverse a list with a
slice (`words[::-1]`). Then join the words back together with spaces.

```python
reverse_words("the quick brown fox")   # returns "fox brown quick the"
reverse_words("hello")                 # returns "hello"
reverse_words("a b c")                 # returns "c b a"
```

### Part 4 - `letter_counts(text)`  *(stretch - optional)*

Write the body of `letter_counts`, which returns a **dictionary** mapping each letter
to how many times it appears in `text`. Ignore case (treat `A` and `a` as the same
letter) and ignore anything that isn't a letter (spaces, punctuation, digits).

Hint: loop through `text.lower()`; `ch.isalpha()` tells you whether a character is a
letter. Build the dictionary as you go - the first time you see a letter, start its
count at 1; after that, add 1.

```python
letter_counts("hello")         # returns {'h': 1, 'e': 1, 'l': 2, 'o': 1}
letter_counts("Mississippi")   # returns {'m': 1, 'i': 4, 's': 4, 'p': 2}
letter_counts("a a a")         # returns {'a': 3}
```

This part is optional - the three parts above are the core of the lab. Do it if you
have time.

## Verifying Correctness

Run the pre-written tests to check your work:

```
pytest
```

Read the output closely - a failing test tells you which function is wrong and shows
what it expected versus what your code returned. Fix, save, and run `pytest` again.

## Getting Help

There is a lab instructor present for the whole session. Ask them whenever you're
stuck.

*The instructor will usually help you find the problem rather than tell you how to
fix it - the goal is for you to get better at diagnosing and fixing your own bugs.*

## How to Submit

Once your tests pass (or the session is ending), commit and push:

```
git add --all
git commit -m "Lab 03 completed"
git push origin main
```

You can confirm the autograder ran correctly by opening the **Actions** tab on your
repository page in GitHub. It can take a minute or two.

## Using AI

You may use an AI assistant to **explain ideas and help you learn** - but **not to
generate code you submit** in this half of the term. Use only a **free** model, and be
ready to explain every line you wrote; the lab instructor may ask you to walk through
your code.
