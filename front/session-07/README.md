# Session 07 
(1401/05/18)

## React 
[React doc](https://reactjs.org/docs/state-and-lifecycle.html)

### State and Lifecycle
Questions:
- props vs state
- How to pass a prop from child to parent in react
- What's wrong with this code:
```
const root = ReactDOM.createRoot(document.getElementById('root'));

function Clock(props) {
  return (
    <div>      
	<h1>Hello, world!</h1>
        <h2>It is {props.date.toLocaleTimeString()}.</h2>    
    </div>  );
}

function tick() {
  root.render(<Clock date={new Date()} />);}

setInterval(tick, 1000);
```

- Do we have global state in react?
- How we could convert a functional comp. to class based one?
- How to define and use a state in a class component?
- What is lifecycles in react?
- Explain is difference between ComponentDidMount and ComponentWillUnmount?
- Could we modify states directly?
- 

#### Converting a Function to a Class 

#### Adding Local State to a Class  

#### Using State Correctly  
- Do Not Modify State Directly



