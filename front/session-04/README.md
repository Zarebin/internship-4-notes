Selectors Part I
- Overview
- Basic Selectors
- Specifications
- Selectors API
- Brief intro to Specificity
- Global selector
- Relational selectors & combinators
- Attribute Selectors
- UI Pseudo-Class Selectors

# Selector

## Css Selector CheatSheet

[CheatSheet](https://www.dropbox.com/s/h2hni9o1m1di989/CSS%20selectors%20cheatsheet.pdf?dl=0)

## Selector level

[All the selectors](https://estelle.github.io/CSS/selectors/#slide15)

## Selectors API

[Link](https://developer.mozilla.org/en-US/docs/Web/API/Document_object_model/Locating_DOM_elements_using_selectors)

## Specificity

![Specifishity](https://specifishity.com/specifishity.png)

[SpeciFISHity](https://estelle.github.io/CSS/selectors/#slide20)

- 1-0-0 : ID selector
- 0-1-0 : Class selector (Also attribute selector & pseudoclass)
- 0-0-1 : Element Selector
- 0-0-0 : The * selector, or global selector, has no weight.
- 0-0-0 : Combinators, like ~, >, and + have no weight.

## Relational selectors & combinators

[estelle-link](https://estelle.github.io/CSS/selectors/#slide27)
[W3schools-link](https://www.w3schools.com/css/css_combinators.asp)

## Attribute Selectors

[W3schools-link](https://www.w3schools.com/css/css_attribute_selectors.asp)
[estelle-link](https://estelle.github.io/CSS/selectors/#slide39)



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
 
###What's polyfill

If the forwards-compatibility issue is not related to new syntax, but rather to a missing API method that was only recently added, the most common solution is to provide a definition for that missing API method that stands in and acts as if the older environment had already had it natively defined. This pattern is called a polyfill 

###Example 

The following  code uses an ES2019 feature, the finally(..) method on the promise prototype. If this code were used in a pre-ES2019 environment, the finally(..) method would not exist, and an error would occur.

```
// getSomeRecords() returns us a promise for some
// data it will fetch
var pr = getSomeRecords();

// show the UI spinner while we get the data
startSpinner();

pr
.then(renderRecords)   // render if successful
.catch(showError)      // show an error if not
.finally(hideSpinner)  // always hide the spinner

```
A polyfill for finally(..) in pre-ES2019 environments could look like this:

```
if (!Promise.prototype.finally) {
    Promise.prototype.finally = function f(fn){
        return this.then(
            function t(v){
                return Promise.resolve( fn() )
                    .then(function t(){
                        return v;
                    });
            },
            function c(e){
                return Promise.resolve( fn() )
                    .then(function t(){
                        throw e;
                    });
            }
        );
    };
}

```
The if statement protects the polyfill definition by preventing it from running in any environment where the JS engine has already defined that method. In older environments, the polyfill is defined, but in newer environments the if statement is quietly skipped.















