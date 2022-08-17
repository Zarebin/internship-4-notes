# session 08
(1401/05/19)

# REACT
[React doc](https://reactjs.org/docs/state-and-lifecycle.html)

### Using State Correctly 

#### 1- Do Not Modify State Directly 

How to modify the state in a component?
> use setState()

#### 2- State Updates May Be Asynchronous 

- What is Asynchronous?
- How will the output of these items be shown?
```
console.log(1);
f(5);
console.log(2);

f(){
console.log(51);
sleep(5 min);
console.log(52);<F11>
}

```
- this code may fail to update the counter,Why,what is the solution?
```
this.setState({
  counter: this.state.counter + this.props.increment,
});
```
#### 3- State Updates are Merged 

How can you update states independently with separate setState() calls?

### The Data Flows Down 

- A component may choose to pass its state down as props to its child components
- This is commonly called a “top-down” or “unidirectional” data flow. Any state is always owned by some specific component, and any data or UI derived from that state can only affect components “below” them in the tree.

[Example](https://codepen.io/gaearon/pen/vXdGmd?editors=0010)


# CSS

- Selectors Part II
- Structural selectors
-- :nth- pseudo-classes

## Structural selectors
  1. Target elements on the page based on their relationships to other elements in the DOM.
  2. Updates dynamically if page updates.
  3. Reduced need for extra markup, classes and IDs
 [structual seslectors list](https://www.sitepoint.com/getting-to-know-css3-selectors-structural-pseudo-classes/)

### introduction
 - [:first-child](https://developer.mozilla.org/en-US/docs/Web/CSS/:first-child)
 - [:first-type-of](https://www.sitepoint.com/getting-to-know-css3-selectors-structural-pseudo-classes/)

  **question**
  *What is the difference between :first-child and :first-of-type?*
  **answer :** *[link](https://stackoverflow.com/questions/24657555/what-is-the-difference-between-first-child-and-first-of-type)*

 - [:last-child](https://developer.mozilla.org/en-US/docs/Web/CSS/:last-child)
 - [:last-type-of](https://developer.mozilla.org/en-US/docs/Web/CSS/:last-of-type)
 
  **question**
  *What is the difference between :last-child and :last-of-type?*

 - [:only-child](https://developer.mozilla.org/en-US/docs/Web/CSS/:only-child)
 - [:only-type-of](https://developer.mozilla.org/en-US/docs/Web/CSS/:only-of-type)

  **question**
  *What is the difference between :only-child and :only-of-type?*
 
### :nth- pseudo-classes
- :nth-child
- [:nth:last-child()](https://developer.mozilla.org/en-US/docs/Web/CSS/:nth-last-child) 
- [example 1](https://estelle.github.io/CSS/selectors/index2.html#slide8)
- [example 2](https://estelle.github.io/CSS/selectors/index2.html#slide8)
  
 [reference](https://estelle.github.io/CSS/selectors/index2.html#slide1)

