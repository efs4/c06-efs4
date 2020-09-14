## Quick Recap
```
0. strFood = input('What is your favorite food? ')  # 'kahlua pig & cabbage'
1. strMany = input('How many do you want: ')        # '2'
```
Question: What is the problem?

FACT: The `return` of the `input()` function* is a string: `str`.

In the first case, `0`, you are expecting to receive a string, so you can use it as is.
So there is no problem with this case....

However, __*the problem is with the second case*__, `1`, you really want a numeric value, but you have a string!

So, you need to __*cast*__† the value from `str` to either:
* `int` or
* `float`.

To perform the cast to `int`, we use a function `int()`.

To perform the cast to `float`, we use the function `float()`.

Note that to distinguish between the type vs. the function, we use parenthesis, `()`, with the function.


### Footnotes
*__*function*__ a function is a named sequence of statements ~ like a program within a program (!)
```
       ____________           +-----------------+             ________________
      /           /           |                 |            /               /
     /   INPUT   /   ----->   |    PROCESSING   |  ---- >   /    OUTPUT     /
    /___________/             |                 |          /_______________/
                              +-----------------+
```
function:
```
       ____________           +-----------------+             ________________
      /           /           |                 |            /               /
     / arguments /   ----->   |       body      |  ---- >   /    return     /
    /___________/             |                 |          /_______________/
                              +-----------------+
```
OOP (object-oriented programming) includes three "big ideas" or concepts:
* __*E*__ ncapsulation
* __*I*__ nheritance
* __*P*__ olymorphism
A function, by itself, is __*NOT*__ OOP.  However, the idea of "breaking-off" a set of statements,
giving them a name, allowing the statements to be run by calling the name is a form of encapsulation.

†__*cast*__: The need to change the type of a variable occurs so frequently in programming
that we have a special word: __*cast*__, which means to change the type of a value
(from any type to another).

```python

                            # strMany       intMany   fltMany
intMany = int(strMany)      # "100"   --->   100
fltMany = float(strMany)    # "100"   --->             100.0
```

Both `int()` and `float()` are functions.  The input is a `str` (but could be `int` or `float`) and the
output or `return` is `int` for `int()` and `float` for `float()`.

Lambert 2-4b Mixed-Mode Arithmetic and Type Conversions
