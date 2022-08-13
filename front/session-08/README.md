# session 08
(1401/05/19)

## React 
[React doc](https://reactjs.org/docs/state-and-lifecycle.html)

### Using State Correctly 

1- Do Not Modify State Directly 

How to modify the state in a component?
> use setState()

2- State Updates May Be Asynchronous 

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
3- State Updates are Merged 

How can you update states independently with separate setState() calls?

### The Data Flows Down 

- A component may choose to pass its state down as props to its child components
- This is commonly called a “top-down” or “unidirectional” data flow. Any state is always owned by some specific component, and any data or UI derived from that state can only affect components “below” them in the tree.

[Example](https://codepen.io/gaearon/pen/vXdGmd?editors=0010)
