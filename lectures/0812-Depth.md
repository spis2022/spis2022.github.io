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

# Q: When would you use an `elif`? Is it between `if` and `else`

A: Yes!  Here's an example of when you might use it:

Write a function that takes in a number representing a grade between 0 and 100.

Return the letter grade, assuming that 90-100 is an A, 80-any number less than 90 is an B, etc.

To simplify the problem, we won't worry about + and - grades.


Examples:

* grade2letter(90) should return A
* grade2letter(89.9) should return B
* grade2letter(75) should return C, 
* grade2letter(40) should return F.

In any if/elif/elif/else block:
* ONLY ONE of the blocks of code will be executed.
* there is a condition on each of the ifs, and elifs
* the FIRST condition that is TRUE, we execute that block of code, then we SKIP THE REST!
* we only do the else, if ALL of the conditions are False!

Here's a proposed solution (not necessarily correct) crowdsourced from students in the session

<img width="288" alt="image" src="https://user-images.githubusercontent.com/1119017/184415981-4dbff870-45ba-4f99-86a5-5c6985ca7f96.png">

Here is a repl where we worked towards a correct solution:

[https://replit.com/@phtcon/spis2022-depth-0812-num2lettergrade#main.py](https://replit.com/@phtcon/spis2022-depth-0812-num2lettergrade#main.py)

# Purpose of Console and Shell windows in repl.it

We also discussed the purpose of the Console and the Shell windows in repl.it

<img width="306" alt="image" src="https://user-images.githubusercontent.com/1119017/184425187-fb860725-54ce-4a64-bb12-266e2615a2d4.png">

* The Console is a python prompt
* The Shell is a Linux command line prompt

The Shell can be used for:
* Listing all of your files with `ls`
* To install pytest, with: `python3 -m poetry add pytest`
* Running `pytest file.py` to run the tests inside `file.py`
* Running `python3 file.py` to run the regular Python code inside `file.py`
* And for many other things.

# We talked a bit about iterators

There was question about iterators.  In lab03, the following code made an iterator go through
all of the lines in the file of data (a csv, or "comma separated value" file).

```python

    hurricaneFile = "data/irma.csv"
    # The line below is a little magical. It opens the file,
    # with awareness of any errors that might occur.
    with open(hurricaneFile, 'r') as csvfile:
        # This line gives you an "iterator" you can use to get each line
        # in the file.
        pointreader = csv.reader(csvfile)


```

The student had solved the problem, but wasn't sure what an iterator was.

We explored that in this repl:

[https://replit.com/@phtcon/spis2022-depth-0812-iterators#read_food.py](https://replit.com/@phtcon/spis2022-depth-0812-iterators#read_food.py)

# A bit about references

Let's talk about Pointer Assignment vs. Deep Copy

