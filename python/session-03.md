# Python Session-03

----
Chapter 1 and 2 of Fluent Python: 

### Magic Methods:
The term magic method is slang for special methods(like `__getitem__`).
Or you can call them **dunder methods** (double underscore before and after)
## `__repr__` vs `__str__`:
- `__repr__`
The string returned by this function should be unambiguous. Used for logging and debugging.
- `__str__`
The string returned by this function is for final user.
The goal of this function is to be readable.

### Reasons to use special method:
- Users don't have to memorize method for standard operations
- It's easier to benefit from the Python standard library and avoid reinventing them.

### How special methods are used?
The first thing to know about special methods is that they are meant to be called by the Python interpreter, and not by you.
You write len(my_object) and, if my_object is an instance of a user-defined class, then Python calls the __len__ method you implemented.
* But if my_object is an instance of one of those built-ins, then len(my_object) retrieves the value of the ob_size field.
* your code should not have many direct calls to special methods.