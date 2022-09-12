# Session-22
(1401-06-14)

## js

﻿### Accessing Properties
Property access of an existing object is preferably done with the `.` operator:

    myObj.favoriteNumber;    // 42
    
If the property name contains characters that cannot appear in identifiers, such as leading numbers or whitespace, `[ .. ]` brackets can be used instead of the `.`:

    myObj["2 nicknames"];    // [ "getify", "ydkjs" ]

### Object Entries
You can get a listing of the properties in an object, as an array of tuples (two-element sub-arrays) holding the property name and value:

    myObj = {
    favoriteNumber: 42,
    isDeveloper: true,
    firstName: "Kyle"
    };

    Object.entries(myObj);
    // [ ["favoriteNumber",42], ["isDeveloper",true], ["firstName","Kyle"] ]

It's possible to create a new object from a list of entries, using `Object.fromEntries(..)`

    myObjShallowCopy = Object.fromEntries( Object.entries(myObj) );

    // alternate approach to the earlier discussed:
    // myObjShallowCopy = { ...myObj };

### Destructuring
Another approach to accessing properties is through object destructuring. Think of destructuring as defining a "pattern" that describes what an object value is supposed to "look like" (structurally), and then asking JS to follow that "pattern" to systematically access the contents of an object value.

    myObj = {
    favoriteNumber: 42,
    isDeveloper: true,
    firstName: "Kyle"
    };
    
    const { favoriteNumber = 12 } = myObj;
    const {
        isDeveloper: isDev,
        firstName: firstName,
        lastName: lname = "--missing--"
    } = myObj;
    
    favoriteNumber;   // 42
    isDev;            // true
    firstName;        // "Kyle"
    lname;            // "--missing--"

### Conditional Property Access
ecently (in ES2020), a feature known as "optional chaining" was added to JS, which augments property access capabilities (especially nested property access). The primary form is the two-character compound operator  `?.`, like  `A?.B`.

This operator will check the left-hand side reference (`A`) to see if it's null'ish (`null`  or  `undefined`). If so, the rest of the property access expression is short-circuited (skipped), and  `undefined`  is returned as the result (even if it was  `null`  that was actually encountered!). Otherwise,  `?.`  will access the property just as a normal  `.`  operator would.

    myObj?.favoriteNumber
    myObj.address?.city

### Accessing Properties On Non-Objects

This may sound counter-intuitive, but you can generally access properties/methods from values that aren't themselves objects:

    fave = 42;

    fave;              // 42
    fave.toString();   // "42"

Note that `null` and `undefined` can be object-ified, by calling `Object(null)` / `Object(undefined)`. However, JS does not automatically box these null'ish values, so property access against them will fail.

## Assiging Properties
Whether a property is defined at the time of object literal definition, or added later, the assignment of a property value is done with the `=` operator, as any other normal assignment would be:

    myObj.favoriteNumber = 123;

It's also possible to assign one or more properties at once -- assuming the source properties (name and value pairs) are in another object -- using the `Object.assign(..)` :

    // shallow copy all (owned and enumerable) properties
    // from `myObj` into `anotherObj`
    Object.assign(anotherObj,myObj);
    
    Object.assign(
        /*target=*/anotherObj,
        /*source1=*/{
            someProp: "some value",
            anotherProp: 1001,
        },
        /*source2=*/{
            yetAnotherProp: false
        }
    );

## Deleting Properties
Once a property is defined on an object, the only way to remove it is with the `delete` operator:

    anotherObj = {
    counter: 123
    };
    
    anotherObj.counter;   // 123
    
    delete anotherObj.counter;
    
    anotherObj.counter;   // undefined

## Determining Container Contents
You can determine an object's contents in a variety of ways. To ask an object if it has a specific property:

    myObj = {
    favoriteNumber: 42,
    coolFact: "the first person convicted of speeding was going 8 mph",
    beardLength: undefined,
    nicknames: [ "getify", "ydkjs" ]
    };
    
    "favoriteNumber" in myObj;            // true
    
    myObj.hasOwnProperty("coolFact");     // true
    myObj.hasOwnProperty("beardLength");  // true
    
    myObj.nicknames = undefined;
    myObj.hasOwnProperty("nicknames");    // true
    
    delete myObj.nicknames;
    myObj.hasOwnProperty("nicknames");    // false

### Listing All Container Contents
There's a variety of other mechanisms available, as well.  `Object.keys(..)`  gives us list of the enumerable property names (aka, keys) in an object -- names only, no values;  `Object.values(..)`  instead gives us list of all values held in enumerable properties.

But what if we wanted to get  _all_  the keys in an object (enumerable or not)?  `Object.getOwnPropertyNames(..)`  seems to do what we want, in that it's like  `Object.keys(..)`  but also returns non-enumerable property names. However, this list  **will not**  include any Symbol property names, as those are treated as special locations on the object.  `Object.getOwnPropertySymbols(..)`  returns all of an object's Symbol properties. So if you concatenate both of those lists together, you'd have all the direct (_owned_) contents of an object.

## Temporary Containers
Using a container to hold multiple values is sometimes just a temporary transport mechanism, such as when you want to pass multiple values to a function via a single argument, or when you want a function to return multiple values:

    function formatValues({ one, two, three }) {
    // the actual object passed in as an
    // argument is not accessible, since
    // we destructured it into three
    // separate variables

    one = one.toUpperCase();
    two = `--${two}--`;
    three = three.substring(0,5);

    // this object is only to transport
    // all three values in a single
    // return statement
    return { one, two, three };
    }

    // destructuring the return value from
    // the function, because that returned
    // object is just a temporary container
    // to transport us multiple values
    const { one, two, three } =

    // this object argument is a temporary
    // transport for multiple input values
    formatValues({
       one: "Kyle",
       two: "Simpson"
       three: "getify"
    });

    one;     // "KYLE"
    two;     // "--Simpson--"
    three;   // "getif"
    
    
 ## React
 
 ## state hook##
- We call it inside a function component to add some local state to it
- useState returns a pair: the current state value and a function that lets you update it. You can call this function from an event handler or somewhere else.
- it’s similar to this.setState in a class, except it doesn’t merge the old and new state together. We’ll show an example comparing useState to this.state in Using the State Hook.
### Declaring multiple state variables ###
- The array destructuring syntax lets us give different names to the state variables we declared by calling useState. These names aren’t a part of the useState API. Instead, React assumes that if you call useState many times, you do it in the same order during every render
```
function ExampleWithManyStates() {
  // Declare multiple state variables!
  const [age, setAge] = useState(42);
  const [fruit, setFruit] = useState('banana');
  const [todos, setTodos] = useState([{ text: 'Learn Hooks' }]);
  // ...
}
```
### what is hook ###
- Hooks are functions that let you “hook into” React state and lifecycle features from function components.
- Hooks don’t work inside classes 
**two type of hooks**
1. built in hooks 
2. custom hooks
## effect hooks ##
- data fetching, subscriptions, or manually changing the DOM from React components are side effects 
- It serves the same purpose as componentDidMount, componentDidUpdate, and componentWillUnmount in React classes
- React runs the effects after every render
- Effects may also optionally specify how to “clean up” after them by returning a function
- Just like with useState, you can use more than a single effect in a component:
## rules of hook ##
- Only call Hooks at the top level. Don’t call Hooks inside loops, conditions, or nested functions.
- Only call Hooks from React function components. Don’t call Hooks from regular JavaScript functions. (There is just one other valid place to call Hooks — your own custom Hooks. We’ll learn about them in a moment.
## Building Your Own Hooks ##
- Custom Hooks let you reuse some stateful logic between components. but without adding more components to your tree.
- Custom Hooks are more of a convention than a feature. If a function’s name starts with ”use” and it calls other Hooks, we say it is a custom Hook.
## other hooks ##
- `useContext` :  lets you subscribe to React context without introducing nesting
- `useReducer` : lets you manage local state of complex components with a reducer


## Css

# Accessibility Media Features

## prefers-reduced-motion
The user prefers less motion on the page.
Example:
```CSS
    @media (prefers-reduced-motion) {
        // do something
    }
```
```CSS
    @media (prefers-reduced-motion:reduce) {
        // do something
    }
```
## prefers-reduced-transparency

The user prefers reduced transparency.
## prefers-contrast

Detects if the user has requested the system increase or decrease the amount of contrast between adjacent colors.
Example:
```CSS
    @media (prefers-contrast: more) {
        // do something
    }
```
```CSS
    @media (prefers-contrast: less) {
        // do something
    }
```

## prefers-color-scheme

Detect if the user prefers a light or dark color scheme.

Example:
```CSS
    @media (prefers-color-scheme: dark) {
        .dark-scheme   { background:  #333; color: white; }
        .dark-scheme { background: black; color:  #ddd; }
    }
```
```CSS
    @media (prefers-color-scheme: light) {
        .light-scheme   { background: white; color:  #555; }
        .light-scheme { background:  #eee; color: black; }
    }
```
## forced-colors

Detect whether user agent restricts color pallete.

Example:
```CSS
    @media (forced-colors: active) {
        .button {
                /* Use a border instead, since box-shadow is forced to 'none' in forced-colors mode */
                border: 2px solid;
                }
    }
```

---

# Viewport
## Viewport meta tag

```HTML
    <meta name="viewport" content="width=device-width,initial-scale=1, maximum-scale=1"/>
```
## Viewport rule

```CSS
    @viewport {
        width: device-width; zoom: 0.5;
    }
```
Note: The use of `<meta name="viewport">` tag overrides `@viewport`.

---

# Mobile Specific CSS
## user-select

### values:
    1. none:Element and its sub-elements are not selectable.
    2. text: text can be selected by the user.
    3. In an HTML editor, if a double-click or context-click occurred in sub-elements, the highest ancestor with this value will be selected.

## touch-action

### single finger (panning) vs multi fingers (manipulation value) in touch:

    ![alt-touch](https://www.mediaevent.de/css/svg/touch-action.svg)

### Note:
    1. Multiple directions can be combined
    2. pan-left pan-right is not valid (use pan-x).
    3. pan-up pan-down is not valid (use pan-y).

---

# supports rule
## What CSS properties does your browser support?
```CSS
    @supports (display: grid) {
    div {
        display: grid;
    }
    }
```

