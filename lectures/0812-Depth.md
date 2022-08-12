# Depth for 0812 

More on recursion and references, plus "Ask me anything" about FOCS lectures weeks 1-2

Link to FOCS Lectures: [https://sites.google.com/eng.ucsd.edu/ucsd-cse-spis-2022/lectures](https://sites.google.com/eng.ucsd.edu/ucsd-cse-spis-2022/lectures)


# Q: How do you remember all the things?

Python has so many keywords, structures, syntax, symbols... how do you keep it all in your head?

A: 1st answer: practice, practice, practice

[https://codingbat.com/python](https://codingbat.com/python)

A: 2nd answer: Honestly, some parts you do and some parts you dont.

For example: In Python, I have for, while, if/else, function defintion, list syntax in my head.

BUT: when it comes to things like:
* How do you add something to a list
* How do you search for something in a list
* etc.

I know that Python has a way to do it.  So does: Java, JavaScript, Ruby, C++ (in the STL), etc.

But I don't necessarily remember the specifics!  I often have to look it up, every single time.

So, that's ok!

# How to simplify functions that return a True/False value.

Anytime you have a function like this:

```python

def my_function(some_parameters):
  if something_goes_here:
    return True
  else:
    return False
```

You can replace it with:

```python

def my_function(some_parameters):
  return something_goes_here
```

Why does this work?  It works because of the way that if/else works.  
* If the condition (something_goes_here) is True, we `return True`
* If the condition (something_goes_here) if False, we `return False`

So we just `return something_goes_here` and the same thing happens. 

We can reduce 4 lines of code down to one.

Example: The first problem in Codingbat.com/python:

```python

def sleep_in(weekday, vacation):
  # if not weekday or vacation:
  #   return True
  # else:
  #   return False
  
  # Using elif, applying DeMorgan's law
  
  # if not weekday or vacation:
  #   return True
  # elif weekday and not vacation:
  #   return False

  # can we do it in one line?
  
  return not weekday or vacation

```

# A bit about references

Let's talk about Pointer Assignment vs. Deep Copy

