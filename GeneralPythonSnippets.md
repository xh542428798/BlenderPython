This is a crash course in the Python subset. If you already master these you should not waste time reading this, unless you want to check for typos or factual inaccuracies. 

Any combination of the following topics will be present in useful Python scripts. This page hopes to introduce you to the broad outlines of the Python language and will contain links for more detailed information. It makes little sense to get very detailed early in the learning process so i'll cover things quickly. 

It's OK if this doesn't make a lot of sense. If you don't understand something remember that the way we write things is often a convention because a convention had to exist (just like if you look at a map of Africa and see straight line borders which have no relationship to geography, -- what's that all about?? exactly, it's a reality that exists only in the minds of the people who've seen those maps.). 

Follow along in Blender's Python console. Learning to type accurately is incredibly important for programming.   

| basic 1 | basic 2 | intermediate |
|---------|---------|--------------|
| [print](GeneralPythonSnippets#print) | [string manipulation](GeneralPythonSnippets#string-manipulation) | [decorators](GeneralPythonSnippets#decorators) |
| [integer](GeneralPythonSnippets#integer) | [for loop](GeneralPythonSnippets#for-loop) |  |
| [float](GeneralPythonSnippets#float) | [list comprehensions](GeneralPythonSnippets#list-comprehensions) |  |
| [string](GeneralPythonSnippets#string) | [while loop](GeneralPythonSnippets#while-loop) |  |
| [tuple](GeneralPythonSnippets#tuple) | [flow control](GeneralPythonSnippets#flow-control) |  |
| [list](GeneralPythonSnippets#list) | [try except](GeneralPythonSnippets#try-except) |  |
| [dictionary](GeneralPythonSnippets#dictionary) | [functions](GeneralPythonSnippets#functions) |  |
| [boolean](GeneralPythonSnippets#boolean) | [import libraries](GeneralPythonSnippets#import-libraries) |  |
| [if statements](GeneralPythonSnippets#if-statements) | [classes](GeneralPythonSnippets#classes) |  |
| [standard library](GeneralPythonSnippets#standard-library) |  |  |

### How to run this code  

(elaborate) : Open Blender, and get a Python console view open. You'll notice `>>>` , this is a prompt waiting for you to type stuff. What we'll be doing below is type stuff after the prompt, then hit Enter to run it.


### print

While you learn Python `print()` is your friend. It will try to display whatever is between the parenthesis `( )`.

```python
>>> print("Hello apprentice")
... Hello apprentice
```

I'll return to `print()` frequently on this page to show how to display information that you will find helpful while coding.

### integer

Whole numbers, positive or negative. You'll see plenty of these as you progress.
```python
# let's make a variable called hal
>>> hal = 3000
>>> print(hal * 3)
... 9000
```
### float

Numbers like these `100.0`, `0.0000003` and `34.4`. etc. You will often see unusual floats like `0.00200023423` when you expect to see just `0.002`, this is normal and will be explained later.  
You might also see scientific notation for small numbers namely `2e-7` which is equivalent to `0.0000002`.

A lot more can be said about _floats_ but it rarely makes sense to talk about them in isolation. You'll see more references to floats further down.

### string

The words you read right now are strings. In Python we express strings by wrapping them in single qoutes, double qoutes or tripple qoutes.
```python
>>> my_first_string = "I am a HAL 9000 computer"
>>> my_second_string = 'I am a HAL 9000 computer'
>>> my_third_string = """I am a HAL 9000 computer"""
```
You can add strings together, we call it 'concatenation':
```python
# notice the spaces at the end of string, why is that?
>>> var1 = "I am a "  
>>> var2 = "HAL "
>>> var3 = "9000 computer"
>>> print(var1 + var2 + var3)
... I am a HAL 9000 computer
```

to convert a non string to a string is done explicitly using `str()`:
```python
>>> some_number = 9000
>>> "Hal " + str(some_number) 
... "Hal 9000"`
```

Further _string manipulation_ is discussed at a later stage. Strings are used a lot in Python, but in Blender they're commonly used to name objects, data, or set the properties of data.

### tuple

This is a data type which is used to collect data, it holds any kind of data you want. You'll see a tuple defined in various ways.

```python
>>> some_number = 20
>>> tuple_one = ('some_string', some_number, 0.3444)
... ('some_string', 20, 0.3444)
```
but it's OK to drop the surrounding parenthesis, the comma separator is most important
```python
>>> tuple_two = 'some_string', some_number, 0.3444
>>> tuple_two
... ('some_string', 20, 0.3444)
```
you'll also see it written this way, but it is not common.
```python
>>> tuple_three = tuple(['some_string', some_number, 0.3444])
```
A tuple is _immutable_. This means you can not change any of the members of the tuple, once it's created it is unchangeable - also if the tuple was made with variables. If you change a variable, the tuple's content is not updated.. see what happens when we update var2 to hold a new string `SAL `.

```python
>>> var1 = "I am a "
>>> var2 = "HAL "
>>> var3 = "9000 computer"
>>> tuple_four = var1, var2, var3
>>> tuple_four
... ('I am a ', 'HAL ', '9000 computer')
>>> var2 = 'SAL '
>>> var4
... ('I am a ', 'HAL ', '9000 computer')    
```
To change a tuple you must assign a new tuple by overwriting the tuple stored in `var4`.
```python
>>> var4 = (var1, var2, var3)
>>> var4
... ('I am a ', 'SAL ', '9000 computer')
```
If you find the need to update members of a collection you might want to use a `List` instead.

### list

Lists are a very big topic, but you don't need to know much about them to do useful things. Lists are like tuples but with a few important differences. Firstly notation, lists use square brackets `[ ]` to enclose their data. These are _not optional_ as they are with tuples.
```python
>>> my_list = [0, 1, 2, 30, 34]
>>> my_other_list = [0.9, 1, 2, "30", "thirty nine"]
```
lists are mutable, you can change the content of lists without assigning a new list to the variable. A list's _elements_ are also called _members_. I'll use the two terms interchangeably. You can tell Python which element to change by using the element index. First element has index 0 (zero), the second element has index 1 (one). etc...the Tenth element has index 9 (nine). Why the off by one difference? -- because elements or indexed starting from 0, this is called 'zero indexing'. Most programming languages do it this way. It's a convention, you'll make mistakes -- we all make off by one mistakes at some point.

To tell Python that you want to use or modify an element you use the bracket notation.

```python
>>> some_list = [30, 40, 20]
>>> some_list[1]  # lets look up the second element, it has index 1.
... 40
```
how about changing the value stored in an element? easy!

```python
>>> my_new_list = [30, 40, 50]
>>> my_new_list[0] = 'First Element Changed'
>>> my_new_list
... ['First Element Changed', 40, 50]
```

**nested lists**

It's not uncommon to have nested lists, or Multi-Dimensional lists.

```python
>>> my_nested_list = [20, 30, my_list]
>>> my_nested_list
[20, 30, [0, 1, 2, 30, 34]]
>>> multi_dim_list = [[1.0, 0.1, 2.0], [0.2, 1.0, 0.3], [1.0, 0.3, 1.0]]
```

**list mutations**

```python
test_list = [[],[]]

def mutate_incoming(test_list, params):
    a, b = params
    list_a, list_b = test_list
    list_a.append(a)
    list_b.append(b)

a_list = [20,30,40]
b_list = ['huh', 'yes', 'ack']

for params in zip(a_list, b_list):
    mutate_incoming(test_list, params)

list_a, list_b = test_list
print(list_a, list_b)

>> [20, 30, 40] ['huh', 'yes', 'ack']
```
In the above snippet we treat the `test_list` like a reference, each time `mutate_incoming` is called it appends new data to the nested list (` [[],[]] `) that the symbol `test_list` represents. This allows for concise zips, abstracting away the .append operation that would be otherwise needed.

unfinished.

### Classes

basic classes


more specific / advanced dynamic class instances

The following example is not likely to be useful to most use cases. There are scenarios when you don't want (or can't) write a class method for each possible feature of your class. Adding methods (and hey they're handled) dynamically can help you make your classes code easier to use and maintain -- if you know what you're doing.

```python
class DemoClass:

    def __init__(self):
        self.power = 2

    def __getattr__(self, name):

        def method(*args, **kw):
            if name in ['work', 'stereo']:                
                if isinstance(kw, dict) and kw:
                    print('a dict', kw)
                elif isinstance(args, tuple) and args:
                    print('a tuple', args)

        return method


f = DemoClass()

f.work(damage=20, reverse=-1)
f.work(20, 1)

"""
a dict {'damage': 20, 'reverse': -1}
a tuple (20, 1)
"""
```

more!? OK :) what if I want to have attributes and functions with the same name, but have a unique behaviour if I do 
```python
c = NewClass()
c.bar   # <-- attr
c.bar(20)  # <-- method!
```

the way Python works doesn't allow us to share the names of attributes and methods. for instance the following is not permitted:
```python
some_class_instance.some_name  # <-- attr
some_class_instance.some_name()  # <-- method
```
##### Making a class iterable

sometimes you need to make a wrapper around some datatype, this lets you turn a class instance into something
that you can iterate over.

```python
class Emo:

    def __init__(self, data):
        self.twoo = []
        self.twoo.extend(data)

    def __iter__(self):
        return iter(self.twoo)


ak = Emo([20, 30, 40])

for g in ak:
    print(g)
```

### Standard Library

This is a massive topic. but for now..

##### pathlib 

> Iteration over paths.. the easy way

like this


```python
from pathlib import Path

dataset_root = Path(r'C:\Users\zeffi\Desktop\GITHUB\sverchok\nodes')
analyzer_path = dataset_root / 'analyzer'

for node_path in analyzer_path.iterdir():
    print(node_path)
```

##### Datetime

I love this module. This example finds all Mondays in the given date range
```python
from datetime import datetime, date, timedelta


def find_mondays_between(start, end, date_format="%m/%d/%Y"):
    a = datetime.strptime(start, date_format)
    b = datetime.strptime(end, date_format)
    delta = b - a
    num_days = delta.days

    mondays = []
    for i in range(delta.days + 1):
        day = a + timedelta(days=i)
        if day.weekday() == 0:
            day_str = day.strftime(date_format)
            mondays.append(day_str)

    return mondays
        

print(find_mondays_between("01/01/2018", "03/12/2018"))
```


# Try Except

what is Try/Except ? a good resource for deeper thought is here:
Personally i tend to use some form of the following. It display the line number and the error. If that isn't enough then it's probably more complicated, and wouldn't likely be conveyed by the error anyway. That's when you switch on your brain again and reason about the line that triggers the error.

```python
import sys

try:
    ...
except Exception as err:
    print('-----', err, end=' | ')
    print('Error on line {}'.format(sys.exc_info()[-1].tb_lineno))
```

