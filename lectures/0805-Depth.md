# SPIS 2022, Depth, 08/05 (10:15-11:30am)

Here's what we'll cover (based on suggestions/questions from students in the session):

* print vs. return
* for and while loops
* parameters (also called arguments)
  - related: function call vs. function definition

# function definitions

First line:

* start with `def`
* next is the name of the function
* next is parameters (in parentheses)
  - if there no parameters, empty parens like this: `()`
  - if there is one parameter, it looks like this: `(my_param)`
  - if more than one, separate with commas: `(a,b,c)`
* then a colon: `:`

Examples:

```python
def celsiusToFarenheit(celsius):
```

```python
def totalEnrollment(studentInfo):
```

```python
def isPrime(my_integer):
```

```python
def printGreeting():
```

```python
def firstRoot(a,b,c):
```

# Print vs Return: when they look the same

<img width="969" alt="image" src="https://user-images.githubusercontent.com/1119017/183130077-b527f1f9-37cc-49ed-b4ef-8cc06d61ea63.png">

# Print vs. Return: when they behave differently

<img width="1098" alt="image" src="https://user-images.githubusercontent.com/1119017/183130183-7cc2412a-854a-4a02-9533-6b8f82f44119.png">

Why? What is happening?

The first thing to realize is that when we type something like this:

```
celsiusToFarenheit(20) - 1
```

This is evaluated by first running the code inside the function definition of `celsiusToFarenheit` then _replacing the words `celsiusToFarenheit(20)` with the return value_.

So: 

```
celsiusToFarenheit(20) - 1
```

becomes:

```
68.0 - 1
```

Because `celsiusToFarenheit(20)` when you run it, returns the value 68.0

Now: What happens in the case of cToF?

The thing to understand is that every python function that doesn't encounter a `return` statement, when it reaches the end of the code, it does `return None`.

So: 

```python
def cToF(celsius):
  print( ((celsius / 5.0) * 9.0) + 32.0 )

```

But really, inside of Python's mind, it looks like this:


```python
def cToF(celsius):
  print( ((celsius / 5.0) * 9.0) + 32.0 )
  return None

```

We didn't type the `return None`.  Python put that in for us (whether we like it or not!)

So, when we have:

```
cToF(20) - 1
```

The `cToF(20)` is evaluated: meaning we go do the code inside the function defintion of `cToF`, with `celsius` having the value `20`.

And we end up printing the value `68.0` on the screen and then returning `None`.

So we get: 


```
None - 1
```

Which is an error!

We can see that directly if we type it in:

Note that these two expressions give the same error!

<img width="504" alt="image" src="https://user-images.githubusercontent.com/1119017/183130920-7551aec7-8c20-4182-85ea-1c5eb2f67d0c.png">


# Question: why use print at all, when return seems better

Answer: sometimes you really do just want to put some output on the screen, and you don't want your function to immediately end!

Consider this function that can print a conversion table from celsius to farenheit:

[Repl](https://replit.com/@phtcon/spis2022-depth-0805#main.py)

```python
def cToF(celsius):
  print( ((celsius / 5.0) * 9.0) + 32.0 )


def tempTable(first, last, step):
  print ("C","F")
  for temp in range(first,last+1,step):
    print(temp, celsiusToFarenheit(temp))


tempTable(0,100,10)

```

If we replaced the occurences of `print` inside the `tempTable` function with `return`, we wouldn't get the result we want.

Remember that `return` ends a function immediately.  If we want to go through every iteration of the loop, we need `print`

<img width="910" alt="image" src="https://user-images.githubusercontent.com/1119017/183132875-bf1a30ea-835a-4274-b5a0-c93d2a4e25c7.png">


# A small digression: formatting

Here's a link: [https://realpython.com/python-formatted-output/](https://realpython.com/python-formatted-output/)

What if we wanted a nicer table?

Instead of:

<img width="224" alt="image" src="https://user-images.githubusercontent.com/1119017/183132915-3fd00e92-861e-49a4-811e-ba52b17a9065.png">

We want all of the numbers to line up nicely in columns?

<img width="981" alt="image" src="https://user-images.githubusercontent.com/1119017/183133442-e1fc98a6-db12-4ca5-9549-2a752a38b251.png">

I can change the width of the fields from 5 to 4 and get a more compact table.  Here I also changed the step value from 10 to 5

<img width="799" alt="image" src="https://user-images.githubusercontent.com/1119017/183134763-b9f70974-a0a5-45aa-af9b-c1a629658f26.png">


We'll come back later and cover that in more detail.

I just wanted you to see a nicely formatted table as part of answering "why would we ever use print".

Typically when we are using print, it's because we are trying to format some nice output for a human to read.

Whereas, when we use return, are returning the result of a computation that we might want to use somewhere else in the program.

# What is Overloading?

It's when the same symbol has different meanings in different contexts.

So, for example:

```python
x = 3 + 5
```

Here the `+` means add.  3 plus 5.

But:

```python
name = "Phill"
school = "UC San Diego"
message = name + " is teaching for " + school
```

Here, the `+` means "string concatenation".  So, the `+` can have different meanings in different contexts.

There's even another meaning of `+`: concatenating lists:

<img width="486" alt="image" src="https://user-images.githubusercontent.com/1119017/183134107-99b1c863-3e85-46d0-b5f6-b1a585ae58ce.png">

In the same way `%` means mod in one context (i.e. remainder after division)

```
x = 121 % 10  #result is 1
y = 121 % 11  #result is 0
```

But in another context, it means string formatting:

```
print('%5d %5d' % ( temp, celsiusToFarenheit(temp) ) )
```

Here, the operand on the left of the `%` is a format string.  The `%d` means "decimal number" and `%5d` means a "decimal number with width of 5".

The operand on the right of the `%` is a tuple containing all of the values that are going to be printed by the "percent thingies".

Each percent thingy (i.e. `%5d` or `%5s` for a string) is replaced by one of the values in the tuple.)

# Hard Coded values vs. Parameters

We sometimed "hard code" values in a function definition, like this:

<img width="930" alt="image" src="https://user-images.githubusercontent.com/1119017/183135402-6fc458be-3882-4e81-94a4-d963ffa0bf14.png">
