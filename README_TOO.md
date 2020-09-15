# c06 Validating Input  ~ with Comments from Class Meeting

## Quick Recap
```
0. strFood = input('What is your favorite food? ')   # 'kahlua pig & cabbage'
1. strMany = input('How many do you want? ')         # '2'
```

Question: What is the problem?

Answer: _push pencil and type-in your answer ~ time: one minute_


## Using `.isnumeric()`
A FURTHER PROBLEM ARISES BECAUSE AN ALPHABETIC INPUT TO `int()` or `float()` WILL CAUSE EACH FUNCTION,
AND THEREFORE THE PROGRAM, TO CRASH!!!

How does `.isnumeric()` work?

Let's use the Python interpreter to find out....

First, let's run a Python program.  We need to download `favs.py` to our system.  To do this, duplicate this window....

* Scroll to the top of this page & click on the name of this remote repo, c06
* In the list of files, click on: `favs.py`
* To the __*LEFT*__ of the pencil (edit) icon, right-click the button: Raw
* Save link as: and browse for a place on your file system to save: `favs.py`
* _You may need to add the `.py` extension by hand_.

Open a shell or terminal.

|OS     | shell or terminal       | command |
|:-----:|:------------------------|:--------|
|Linux  | terminal                | `python` or `python3` |
|MacOS  | ⌘ [space] term [Enter] | `python` or `python3` |
|Windows| Windows PowerShell      | `python` |
|repl.it| The black console on the right is a Python interpreter | n/a |

Here are two important shell commands:

|desired result              | Unix (Linux & MacOS)     | Windows  |
|:---------------------------|:------------------------|:--------|
| list contents of directory | `ls`   | `dir` [PowerShell allows `ls`] |
| change directory <newdir>  | `cd`   | `cd`  |

Change directories, `cd` to the directory (a.k.a. ~ also known as ~ folder) to the
same folder where you saved the file `favs.py`.


If the terminal shell is in the same directory as the file `favs.py`, then enter the command:

```
> python favs.py
```
NOTE:  If the above fails, try:
```
$ python3 favs.py
```

What does the program do?

Why?

Above, we ran the Python interpreter and included a file with Python statements in it, and
the Python interpreter ran each Python statement.

Now, we will run the Python interpreter itself by just running `python`.  We will manually
type-in Python statements "DIRECTLY" into the interpreter that will execute them immediately.

NOTE:  If we type `python favs.py` (or `python3 favs.py`) we are instructing the Python
interpreter to go through all of the (Python) statements in the specified file.  When we type
`python` (or `python3`) by itself, we are running the Python interpreter.  When we enter
(Python) statements directly into the intpreter, it executes them immediately.  This allows
us to quickly experiment with Python syntax.

For Linux, MacOS, or Windows, notice that the prompt of the Python interpreter is `>>> `.

# `type()`
`type()` is yet another example of a __*polymorphic*__ function.  We can pass-in as arguments objects of
any type: `int`, `float`, `str`, etc. and the `return` is the type of the object, e.g.
```
>>> type('123')     # a string literal
<class 'str'>
>>> type(123)       # an integer
<class 'int'>
>>> type(123.0)     # a float
<class 'float'>
```

The following includes some examples of using `.isnumeric()`

Enter: `'123'.isnumeric()`

```
>>> '123'.isnumeric()
True

>>> 'aloha'.isnumeric()
False

>>> strText = 'a string'
>>> strText.isnumeric()
False

>>> strNumber = '246'
>>> strNumber.isnumeric()
True
```
### What is going on here?

`.isnumeric()` is behaving like a function, but technically speaking, it is something else (related).

#### QUESTION: Where is the input to `.isnumeric()` and what is it (`.isnumeric())
ANS: The input "argument" it .isnumeric() is IMMEDIATELY BEFORE THE DOT: .

This means that .isnumeric() is somehow related to or operating on the OBJECT before it (!)

The OBJECT that precedes it IS an input argument to the METHOD.

#### QUESTION:  What is the type of the return or output of .isnumeric()?
ANS: `bool` or Boolean

#### QUESTION:  If .isnumeric() is NOT a function (but it is something like a function), then what is it?
ANS: It is a METHOD ~ is a "captive" function that operates on an OBJECT.

CLASS is word that is a part of OOP.  CLASS is like a schema, and OBJECT is an instance of that class.

* CLASS ~ str
* OBJECT ~ strMany, strText, 'aloha',  ...

## What's going on?
Strings, str, follow OOP (!)  The ENCAPSULATION part of OOP allows programmers to define METHODS, which
are "captive functions" to the objects.

In-class exercise:

Modify `favs.py` so that it "gracefully" gives the user several chances to enter a number.

For example:
```
python favs.py

What is your favorite food? beef jerkey
How many do you want? a
    OOPS!  Please enter a number: ave
    OOPS!  Please enter a number: 5
We'll see if we can get you 10 beef jerkey.

python favs.py

What is your favorite food? loco moco
How many do you want? many
    OOPS!  Please enter a number: three
    OOPS!  Please enter a number: two
    OOPS!  Please enter a number: one
    OOPS!  Please enter a number: zero
    OOPS!  Please enter a number: 1
We'll see if we can get you 2 loco moco.
```

# Two types of loops
## "Deterministic" Loop ~ `for`
Characteristic: BEFORE the program enters the loop, programmer has some idea of the number of times the loop will execute.

## "Conditional" Loop ~ "Non-deterministic Loop" ~ `while`
Characteristic: BEFORE the program enters the loop, programmer as NO IDEA about the number of times the loop will exectute.

"Mathematical" example: iteratively compute an irrational number, like `pi` or square root of n, where n is not a perfect square, e.g. square root of 2.

Edit the program `favs.py` (use VSC = Visual Studio Code or other editor -- copy & paste into repl.it).

# Example of writing a progam with error-checking
## 0. First-pass ~ Assume that there are no errors
This version of the program __*WILL*__ crash if the user enters an alphabetic character for the quantity
```python
#! /usr/bin/python3
'''\
favs.py

ICS 111 c07
favorite foods
'''

strFood = input('What is your favorite food? ')   # 'kahlua pig & cabbage'
strMany = input('How many do you want? ')         # '2'

# cast the string from input() to an int to be used below
intMany = int(strMany)

# Use an f-string for output
print(f"Let's see if we can get you {intMany*2} {strFood}.")
```

## 1. Examine the flow of the program with a (logical) if - else statement inserted
This version of the program __*WILL*__ crash if the user enters an alphabetic character for the quantity
```python
#! /usr/bin/python3
'''\
favs.py

ICS 111 c07
favorite foods
'''

strFood = input('What is your favorite food? ')   # 'kahlua pig & cabbage'
strMany = input('How many do you want? ')         # '2'

# Here is the if statement to see how it behaves
if strMany.isnumeric():
    print('Input is good -- OK to proceed')
else:
    print('INPUT IS BAD -- NEED TO ASK USER TO TRY AGAIN!!!')


# cast the string from input() to an int to be used below
intMany = int(strMany)

# Use an f-string for output
print(f"Let's see if we can get you {intMany*2} {strFood}.")
```
Running the above version of the program shows that a "conditional check" is needed right there.

HOWEVER, the "main `if:`" branch does NOT need any work.  UNFORTUNATELY the `else:` branch is where
the help is needed.


## 2. Examine the flow of the program with a `not` in the if - else statement
This version of the program __*WILL*__ crash if the user enters an alphabetic character for the quantity
```python
#! /usr/bin/python3
'''\
favs.py

ICS 111 c07
favorite foods
'''

strFood = input('What is your favorite food? ')   # 'kahlua pig & cabbage'
strMany = input('How many do you want? ')         # '2'

# Here is the if statement WITH not INSERTED to see how it behaves
if not strMany.isnumeric():                                         # not has been inserted here
    print('INPUT IS BAD -- NEED TO ASK USER TO TRY AGAIN!!!')
else:
    print('Input is good -- OK to proceed')

# cast the string from input() to an int to be used below
intMany = int(strMany)

# Use an f-string for output
print(f"Let's see if we can get you {intMany*2} {strFood}.")
```
In this version of the program, we can now do our work on it in the `if:` branch.  We can "comment-out"
the else branch in the next version.

## 3. Examine the flow of the program with a `not` in the if - else statement + "comment-out" the `else:` branch
This version of the program __*WILL*__ crash if the user enters an alphabetic character for the quantity.

This version is basically the same as above, except that now the `else:` branch has been commented-out.

In VSC, you can highlight the lines you want to comment-out (or comment-back-in) and on Windows push `ctrl + /`.
```python
#! /usr/bin/python3
'''\
favs.py

ICS 111 c07
favorite foods
'''

strFood = input('What is your favorite food? ')   # 'kahlua pig & cabbage'
strMany = input('How many do you want? ')         # '2'

# Here is the if statement WITH not INSERTED to see how it behaves
if not strMany.isnumeric():                                         
    print('INPUT IS BAD -- NEED TO ASK USER TO TRY AGAIN!!!')
# else:                                                       # COMMENT-OUT THESE LINES SO THAT
#    print('Input is good -- OK to proceed')                  # PYTHON INTERPRETER WILL SKIP THEM

intMany = int(strMany)

# Use an f-string for output
print(f"Let's see if we can get you {intMany*2} {strFood}.")
```

##  4. FINALLY, a version of the program that "nicely" prompts the user to re-enter numeric data
This version of the program (finally) will __*NOT*__ crash if the user enters an alphabetic character for the quantity!
```python
#! /usr/bin/python3
'''\
favs.py

ICS 111 c07
favorite foods
'''

strFood = input('What is your favorite food? ')   # 'kahlua pig & cabbage'
strMany = input('How many do you want? ')         # '2'

# Here is the if statement WITH not INSERTED to see how it behaves
if not strMany.isnumeric():                                         
    while not strMany.isnumeric():
        strMany = input('\t OOPS! Please enter a number: ')
# else:                                                       # COMMENT-OUT THESE LINES SO THAT
#    print('Input is good -- OK to proceed')                  # PYTHON INTERPRETER WILL SKIP THEM

intMany = int(strMany)

# Use an f-string for output
print(f"Let's see if we can get you {intMany*2} {strFood}.")
```
Actually, if you take a look at the if: statement, you can notice that it seems like it may be redundant!

OK, so try to remove it:
##  5. GOT IT!
This version of the program (finally) will __*NOT*__ crash if the user enters an alphabetic character for the quantity!
```python
#! /usr/bin/python3
'''\
favs.py

ICS 111 c07
favorite foods
'''

strFood = input('What is your favorite food? ')   # 'kahlua pig & cabbage'
strMany = input('How many do you want? ')         # '2'

# Removed if statement -- this is enough:
while not strMany.isnumeric():
   strMany = input('\t OOPS! Please enter a number: ')

intMany = int(strMany)

# Use an f-string for output
print(f"Let's see if we can get you {intMany*2} {strFood}.")
```
Actually, if you take a look at the if: statement, you can notice that it seems like it may be redundant!





If there is time, link from about to this remote repo.
