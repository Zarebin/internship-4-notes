Selectors Part I
- Overview
- Basic Selectors
- Specifications
- Selectors API
- Brief intro to Specificity
- Global selector
- Relational selectors & combinators

![specifishity](https://specifishity.com/specifishity.png)

# Selector

## Basic Selectors
 - ID
 > #myID
 - class
 > .myClass
 - tag name
 > li

## Selector level

### level1:

- Type selector : 
> E
- Descendant selector : 
> E F
- Class selector :
> .class
- ID selector :
> #elID
- pseudo-class :
> :link

### level2:

- Universal selector :
> *
- Lang pseudo-class :
> :lang(en)
- User action pseudo-class :
>  :hover/:focus
- Structural pseudo-class :
> :first-child
- Child combinator :
> E > F
- Attribute Selectors :
> [attribute]/[attribute='value']/[attribute~='value']/[attribute|='en']
- Adjacent sibling combinator :
> E + F
 
### level3:
- Target pseudo-class:
> :target
- ....

### level4:
- Case-insensitive attribute selector:
> [attribute='value' i]
- ....

[All the selectors](https://estelle.github.io/CSS/selectors/#slide15)

## selectors API
- document.querySelector()
- document.querySelectorAll()

[link](https://developer.mozilla.org/en-US/docs/Web/API/Document_object_model/Locating_DOM_elements_using_selectors)

## Specificity

[SpeciFISHity](https://estelle.github.io/CSS/selectors/#slide20)

- 1-0-0 : ID selector
- 0-1-0 : Class selector (Also attribute selector & pseudoclass)
- 0-0-1 : Element Selector
- 0-0-0 : The * selector, or global selector, has no weight.
- 0-0-0 : Combinators, like ~, >, and + have no weight.

## Relational selectors & combinators

### Descendant Selector
The descendant selector matches all elements that are descendants of a specified element.
> div p

### Child Selector (>)
The child selector selects all elements that are the children of a specified element.
> div > p

### Adjacent Sibling Selector (+)
The adjacent sibling selector is used to select an element that is directly after another specific element.
> div + p 

### General Sibling Selector (~)
The general sibling selector selects all elements that are next siblings of a specified element.
>  div ~ p

[link](https://www.w3schools.com/css/css_combinators.asp)

## Attribute Selectors

-------------------------------------------------------------------------

#JS

### What's paradigm
The term "paradigm" in programming language context refers to a broad (almost universal) mindset and approach to structuring code.

###Typical paradigm
-Procedural (like C)
-Object-oriented (like Java)
-Functional (like Haskell)

###Backwards & Forwards
Backwards compatibility means that once something is accepted as valid JS, there will not be a future change to the language that causes that code to become invalid JS

forwards-compatible means that including a new addition to the language in a program would not cause that program to break if it were run in an older engine. (like Html and CSS)

###What's Transpiling
Transpiling is a contrived and community-invented term to describe using a tool to convert the source code of a program from one form to another (but still as textual source code). 

###Babel
Babel is the most common transpiler [Babel](https://babeljs.io)

###Example of transpiling by babel

The code we write: 

```
if (something) {
    let x = 3;
    console.log(x);
}
else {
    let x = 4;
    console.log(x);
}

```
Code after transpiling :

```
var x$0, x$1;
if (something) {
    x$0 = 3;
    console.log(x$0);
}
else {
    x$1 = 4;
    console.log(x$1);
}

```
 














