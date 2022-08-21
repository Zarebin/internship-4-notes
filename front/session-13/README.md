# SESSION-13
(1401/05/29)

# js 
## chapter2

### Declaring and Using Variables
 1. values can either appear as literal values (as many of the preceding examples illustrate),
 2. they can be held in variables; think of variables as just containers for values.

#### type of declartion:
 1. var 
 2. let 
 3. const 

- Question : what is defference between var ,let and const ? [answer](https://www.developer.com/languages/javascript/javascript-var-let-const-variable-declaration/)

- Question : what is the meaning of "block scoping"?

 4. function 
  - we call "function" , procedure in js because : A procedure is a collection of statements that can be invoked one or more times, may be provided some inputs, and may give back
    one or more outputs.
  - function  appears in 3 ways : 
    1. as a statement by itself
```
     function awesomeFunction(coolThings) {
      return amazingStuff;
    }

```
    2. as an expression in another statement
```
     var awesomeFunction = function(coolThings) {
     return amazingStuff;
    };

```   
  - Question : whats the difference between these two ways?

   3. Since functions are values, they can be assigned as properties on objects
```
    var whatToSay = {
    greeting() {
        console.log("Hello!");
    },
    question() {
        console.log("What's your name?");
    },
    answer() {
        console.log("My name is Kyle.");
     }
    };

    whatToSay.greeting();
    // Hello! 

``` 
### Comparisons
  1. Equal...ish
    - ``` x==y; ```
    - ```  x===y; ```
 
- Question : whats difference between primitive value and object in comparison with "triple-equals" ?

#CSS

## IE Specific

 [link](https://developer.mozilla.org/en-US/docs/Web/CSS/Microsoft_Extensions)
 
 1- [::-ms-browse](http://man.hubwiz.com/docset/CSS.docset/Contents/Resources/Documents/developer.mozilla.org/en-US/docs/Web/CSS/__-ms-browse.html)
 
 The ::-ms-browse CSS pseudo-element represents the "button" to open the file picker of an <input> of type="file" . This button and pseudo-element are non-standard and only supported by Internet Explorer and Microsoft Edge.
 
 2- [::-ms-value](http://man.hubwiz.com/docset/CSS.docset/Contents/Resources/Documents/   developer.mozilla.org/en-US/docs/Web/CSS/__-ms-value.html)	
 
 
 3- [::-ms-check ](http://man.hubwiz.com/docset/CSS.docset/Contents/Resources/Documents/developer.mozilla.org/en-US/docs/Web/CSS/__-ms-check.html)
 
 The ::-ms-check CSS pseudo-element represents the checkmark of an <input> of type="checkbox" or type="radio".
 
 4- ::-ms-clear
 
 The ::-ms-clear CSS pseudo-element represents a button (the "clear button") at the edge of a text <input> which clears away the current value of the <input> element.
 

## Mozilla specific

 [link](https://developer.mozilla.org/en-US/docs/Web/CSS/Mozilla_Extensions)
 
 Example:
 [::-moz-color-swatch](https://developer.mozilla.org/en-US/docs/Web/CSS/::-moz-color-swatch)

## -webkit scrolling pseudo-elements


1- [::-webkit-progress-bar](https://developer.mozilla.org/en-US/docs/Web/CSS/::-webkit-progress-bar)

2- [::-webkit-progress-value](https://developer.mozilla.org/en-US/docs/Web/CSS/::-webkit-progress-value)

3- [::-webkit-inner-spin-button](https://developer.mozilla.org/en-US/docs/Web/CSS/::-webkit-inner-spin-button)



-----------------------


[CSS @keyframes Rule](https://www.w3schools.com/cssref/css3_pr_animation-keyframes.asp)

example:
[link](https://www.w3schools.com/cssref/tryit.asp?filename=trycss3_keyframes3)
```
<style> 
div {
  background: green !important;
}

div {
  width: 100px;
  height: 100px;
  background: red;
  position: relative;
  animation: mymove 5s infinite;
}

@keyframes mymove {
  0%   {top: 0px; background: red; width: 100px;}
  100% {top: 200px; background: yellow; width: 300px;}
}
</style>
```


