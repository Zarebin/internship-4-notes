# SET

> A set is an unordered collection of items. Every set element is unique (no duplicates) and must be immutable (cannot be changed).

> However, a set itself is mutable. We can add or remove items from it.

> Sets can also be used to perform mathematical set operations like union, intersection, symmetric difference, etc.

## Creating Python Sets

> A set is created by placing all the items (elements) inside curly `braces {}`, separated by comma, or by using the built-in `set()` function.

> It can have any number of items and they may be of different types (integer, float, tuple, string etc.). But a set cannot have mutable elements like lists, sets or dictionaries as its elements.

```
# Different types of sets in Python
# set of integers
my_set = {1, 2, 3}
print(my_set)

# set of mixed datatypes
my_set = {1.0, "Hello", (1, 2, 3)}
print(my_set)
```
Output

```
{1, 2, 3}
{1.0, (1, 2, 3), 'Hello'}
```

Creating an empty set is a bit tricky.

Empty curly braces {} will make an empty dictionary in Python. To make a set without any elements, we use the set() function without any argument.
```
# Distinguish set and dictionary while creating empty set

# initialize a with {}
a = {}

# check data type of a
print(type(a))

# initialize a with set()
a = set()

# check data type of a
print(type(a))
```

## Modifying a set in Python

> Sets are mutable. However, since they are unordered, indexing has no meaning.

> We cannot access or change an element of a set using indexing or slicing. Set data type does not support it.

> We can add a single element using the `add()` method, and multiple elements using the `update()` method. The `update()` method can take tuples, lists, strings or other sets as its argument. In all cases, duplicates are avoided.


## Removing elements from a set

> A particular item can be removed from a set using the methods `discard()` and `remove()`.

> The only difference between the two is that the `discard()` function leaves a set unchanged if the element is not present in the set. On the other hand, the `remove()` function will raise an error in such a condition (if element is not present in the set).

> Similarly, we can remove and return an item using the `pop()` method.

> Since set is an unordered data type, there is no way of determining which item will be popped. It is completely arbitrary.

> We can also remove all the items from a set using the `clear()` method.


# Dictionary
> [Dict paper](https://www.programiz.com/python-programming/dictionary)

In this tutorial, you'll learn everything about Python dictionaries; how they are created, accessing, adding, removing elements from them and various built-in methods.
## Creating Dictionaty

> Creating a dictionary is as simple as placing items inside curly braces `{}` separated by commas.

> An item has a key and a corresponding value that is expressed as a pair `(key: value)`.

> While the values can be of any data type and can repeat, keys must be of immutable type (string, number or tuple with immutable elements) and must be unique.
> As you can see from above, we can also create a dictionary using the built-in `dict()` function.


##Accessing Element from Dictionary

> While indexing is used with other data types to access values, a dictionary uses keys. Keys can be used either inside square brackets `[]` or with the `get()` method.

> If we use the square brackets `[]`, KeyError is raised in case a key is not found in the dictionary. On the other hand, the `get()` method returns None if the key is not found.

## Removing elemnts from Dictionary

> We can remove a particular item in a dictionary by using the `pop()` method. This method removes an item with the provided key and returns the value.

> The `popitem()` method can be used to remove and return an arbitrary `(key, value)` item pair from the dictionary. All the items can be removed at once, using the `clear()` method.

> We can also use the del keyword to remove individual items or the entire dictionary itself.

## Numeric Range Loop
> [loop paper](https://www.programiz.com/python-programming/for-loop)


The most basic for loop is a simple numeric range statement with start and end values. The exact format varies depending on the language but typically looks something like this:
```
for i = 1 to 10
    <loop body>```    
Here, the body of the loop is executed ten times. The variable i assumes the value 1 on the first iteration, 2 on the second, and so on. This sort of for loop is used in the languages BASIC, Algol, and Pascal.
```
## Three-Expression Loop
> Another form of for loop popularized by the C programming language contains three parts:

1. An initialization
2. An expression specifying an ending condition
3. An action to be performed at the end of each iteration.
This type of loop has the following form:
```
for (i = 1; i <= 10; i++)
    <loop body>
```

## Collection-Based or Iterator-Based Loop
> This type of loop iterates over a collection of objects, rather than specifying numeric values > or conditions:

```for i in <collection>
     <loop body>
```

## Functions in Python

Python’s functions are first-class objects. We can assign them to variables, store them in data structures, pass them as arguments to other functions, and even return them as values from other functions.

The aim of this article is to understand these concepts intuitively, which in turn will help in grasping advance features in Python like lambdas and decorators much easily. We’ll go through some examples to help us develop this intuitive understanding.

So Let’s get started.

We’ll be using our simple greet method for demonstration purposes. It’s a simple toy example with easy recognizable output.
```
def greet(name):
    return "Welcome {}!!".format(name)
>>> greet('Sarah')
'Welcome Sarah!!'
```
1. Functions Are Objects
All data in a Python program is represented by objects or relations between objects. Things like strings, lists, modules and functions are all objects. There’s nothing particularly special about functions in Python. They’re also just objects.

Since greet function is an object, we can assign it to another variable, just like any other object:

>>> `receive = greet`
 
The above line does’t call the function. It takes the function object reference by greet and creates a second name, receive, that points to it. We can execute the method by calling receive:

>>> `receive('Sarah')`
'Welcome Sarah!!'
Function objects and their names are two separate things. We can delete the functions’ original name (greet) and still call the function, since another name (receive) still points to it.
```
>>> del greet
>>> greet('Sarah')
NameError: "name 'greet' is not defined"
>>> receive('Sarah')
'Welcome Sarah!!'
```
Therefore, a variable pointing to a function and the function itself are two separate concerns.

2. Functions Can Be Stored in Data Structures
Since functions are first-class citizens, we can store them in data structures, just like we can with other objects. For example, we can add functions to a list:
```
>>> funcs = [len, str.isdigit, str.lower]
>>> funcs
[ <built-in function len>,
 <method 'isdigit' of 'str' objects>,
 <method 'lower' of 'str' objects> ] 
Accessing the function objects stored inside the list works like it would with any other type of object:

>>> for f in funcs:
...    print(f, f('Hello World!'))
<built-in function len> 12
<method 'isdigit' of 'str' objects> False
<method 'lower' of 'str' objects> hello world
3. Functions Can Be Passed to Other Functions
Because functions are objects, we can pass them as arguments to other functions.

def accept(func):
    msg = func('Roark')
    print(msg)
>>> accept(greet)
'Welcome Roark!!'
We can influence the resulting msg by passing in different functions. For example:

def leave(name):
    return "Good Bye {}!".format(name)
>>> accept(leave)
'Good Bye Roark!'
The ability to pass function objects as arguments to other functions is powerful. It allows us to abstract away and pass around behaviours. In above example, accept function stays the same but we can influence its output by passing in different behaviours.

4. Functions Can Be Nested
Perhaps surprisingly, Python allows functions to be defined inside other functions. They are often called nested functions or inner functions.

def speak(text):
    def whisper(t):
        return t.lower + "..."
    return whisper(text)
>>> speak('Hello World')
'hello world...'
Now, what’s happening above? Every time we call speak, it defines a new inner function whisper and then calls it immediately after.

Also, what’s noteworthy here is — whisper does not exists outside speak:

>>> whisper('hello')
NameError: "name 'whisper' is not defined"
NOTE: if we really want to access that nested whisper function from outside speak, we can return the inner function to the caller of parent function. For example:

def get_func(flag):
    def add(a, b):
        return a + b
    def multiply(a, b):
        return a * b
    if flag > 0.5:
        return multiply
    else:
        return add
>>> func_inst = get_func(0.7)
>>> func_inst
<function get_func.<locals>.multiply at 0x102d54290>
>>> func_inst(10, 6)
60
This means not only can functions accept behaviours through arguments but they can also return behaviours.

5. Objects Can Behave Like Functions
While all functions are objects in Python, the reverse isn’t true. Objects aren’t functions. But they can be made callable, which allows us to treat them like functions in many cases.

If an object is callable it means we can use the round parentheses function call syntax on it and even pass in function call arguments. This is all powered by the __call__ dunder method.

Here’s an example of class defining a callable object:

class Foo:
    def __init__(self):
        print("init")
    def __call__(self):
        print("call")
>>> obj = Foo()
init
>>> obj()
call
Behind the scenes, “calling” an object instance as a function attempts to execute the object’s __call__ method.

Conclusions:
Everything in Python is an object, including functions. We can assign them to variables, store them in data structures, and pass or return them to and from other functions.
First-class functions allows us to abstract away and pass around behaviour in our program.
Objects can be made callable. In many cases this allows us to treat them like functions.
```

## Python Exceptions

[all about python Exceptions](https://docs.python.org/3/library/exceptions.html#:~:text=In%20Python%2C%20all%20exceptions%20must,from%20which%20it%20is%20derived).)

## python Modules and Package and Script Writing
[all about python Modules and Package and Script Writing ] (https://www.aparat.com/v/NM9cA?playlist=8840)

