# Session-19
(1401-06-09)

## Js

### Chapter 1: Object Foundations

- JS definitely has objects, but that doesn't mean that all values are objects.
- objects are arguably the most important (and varied!) value type in the language.

- The object mechanism is certainly the most flexible and powerful container type

- Why are prototypes (along with the this keyword, covered later in the book) so core to JS as to be one of its three pillars?  prototypes are how JS's object system can express the class design pattern, one of the most widely relied on design patterns in all of programming. 

### Objects As Containers
Objects are collections of key/value pairs. There are also sub-types of object in JS with specialized behaviors, such as :

1- arrays (numerically indexed) 
2- functions (callable)

- Keys are often referred to as "property names", with the pairing of a property name and a value often called a "property".

```
-myObj = {
    // ..
};
using myObj = new Object()
```

It's easy to get confused what pairs of { .. } mean, since JS overloads the curly brackets to mean any of the following, depending on the context used:

- delimit values, like object literals
- define object destructuring patterns (more on this later)
- delimit interpolated string expressions, like `some ${ getNumber() } thing`
- define blocks, like on if and for loops
- define function bodies

### Defining Properties

```
myObj = {
    favoriteNumber: 42,
    isDeveloper: true,
    firstName: "Kyle"
};
 
function twenty() { return 20; }
 
myObj = {
    favoriteNumber: (twenty() + 1) * 2,
};

```

-JS does not have lazy expressions,

```
function twenty() { return 20; }
function myNumber() { return (twenty() + 1) * 2; }

myObj = {
    favoriteNumber: myNumber   // notice, NOT `myNumber()` as a function call
};
```

### Looks Like JSON?

- The biggest differences between JS's object literals and JSON are, for objects defined as JSON:
1- property names must be quoted with " double-quote characters
2- property values must be literals (either primitives, objects, or arrays), not arbitrary JS expressions

- In JS programs, an object literal does not require quoted property names -- you can quote them (' or " allowed), but it's usually optional. There are however characters that are valid in a property name, but which cannot be included without surrounding quotes; for example, leading numbers or whitespace:

```
{
    "favoriteNumber": 42,
    "isDeveloper": true,
    "firstName": "Kyle"
}

myObj = {
    favoriteNumber: 42,
    isDeveloper: true,
    firstName: "Kyle",
    "2 nicknames": [ "getify", "ydkjs" ]
};
```

- One other minor difference is, JSON syntax -- that is, text that will be parsed as JSON, such as from a .json file -- is stricter than general JS. For example, JS allows comments (// .. and /* .. */), and trailing , commas in object and array expressions; JSON does not allow any of these. Thankfully, JSON does still allow arbitrary whitespace.

### Property Names

```
anotherObj = {
    42:       "<-- this property name will be treated as an integer",
    "41":     "<-- ...and so will this one",

    true:     "<-- this property name will be treated as a string",
    [myObj]:  "<-- ...and so will this one"
};
```

- The 42 property name will be treated as an integer property name (aka, index); the "41" string value will also be treated as such since it looks like an integer. By contrast, the true value will become the string property name "true", and the myObj identifier reference, computed via the surrounding [ .. ], will coerce the object's value to a string (generally the default "[object Object]").

- Note:
If you need to actually use an object as a key/property name, never rely on this computed string coercion; its behavior is surprising and almost certainly not what's expected, so program bugs are likely to occur. Instead, use a more specialized data structure, called a Map (added in ES6), where objects used as property "names" are left as-is instead of being coerced to a string value.

```
anotherObj = {
    ["x" + (21 * 2)]: true
};
```

- The expression "x" + (21 * 2), which must appear inside of [ .. ] brackets, is computed immediately, and the result ("x42") is used as the property name.
