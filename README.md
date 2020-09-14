# c06 Validating Input

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

Enter: `'123'.isnumeric()`

```
>>> '123'.isnumeric()
0___

>>> 'aloha'.isnumeric()
1___

>>> strText = 'a string'
>>> strText.isnumeric()
2____

>>> strNumber = '246'
>>> strNumber.isnumeric()
3___

What is going on here?

`.isnumeric()` is behaving like a function, but technically speaking, it is something else (related).

Where is the input to `.isnumeric()` and what is it (`.isnumeric())

ANS

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
    OOPS!  Please enter a number: 
We'll see if we can get you 10 beef jerkey.
```

Edit the program `favs.py` (use VSC = Visual Studio Code or other editor -- copy & paste into repl.it).

If there is time, link from about to this remote repo.
