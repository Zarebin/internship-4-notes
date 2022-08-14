#React
(1401.05.23)

## Handling Events

 [Source link](https://reactjs.org/docs/handling-events.html)
 
 - React events are named using camelCase
 - pass a function as the event handler
 
 ```
 	<button onClick={activateLasers}>  
 		Activate Lasers
	</button>
 ```
 
 - to prevent default behavior in React ,You must call preventDefault explicitly.
 - In JavaScript, class methods are not bound by default. 
 - This is not React-specific behavior; it is a part of how functions work in JavaScript. Generally, if you refer to a method without () after it, such as    			     onClick={this.handleClick}, you should bind that method. 
 
 ### 3 ways to use the event handler:
  
  #### 1- you should bind that method
	 ```
		 class Toggle extends React.Component {
		  constructor(props) {
		    super(props);
		    this.state = {isToggleOn: true};

		    // This binding is necessary to make `this` work in the callback    this.handleClick = this.handleClick.bind(this);  }

		  handleClick() {    this.setState(prevState => ({      isToggleOn: !prevState.isToggleOn    }));  }
		  render() {
		    return (
		      <button onClick={this.handleClick}>        {this.state.isToggleOn ? 'ON' : 'OFF'}
		      </button>
		    );
		  }
		}
	```

  #### 2- You can use public class fields syntax to correctly bind callbacks
	```
		class LoggingButton extends React.Component {
		  // This syntax ensures `this` is bound within handleClick.  handleClick = () => {    console.log('this is:', this);  };  render() {
		    return (
		      <button onClick={this.handleClick}>
			Click me
		      </button>
		    );
		  }
		}
	```

  #### 3- you can use an arrow function in the callback
	```
		class LoggingButton extends React.Component {
		  handleClick() {
		    console.log('this is:', this);
		  }

		  render() {
		    // This syntax ensures `this` is bound within handleClick    return (      <button onClick={() => this.handleClick()}>        Click me
		      </button>
		    );
		  }
		}
	```

  > We generally recommend binding in the constructor or using the class fields syntax, to avoid this sort of performance problem.

 ### Passing Arguments to Event Handlers 
  - Inside a loop, it is common to want to pass an extra parameter to an event handler.
   
  ```
  <button onClick={(e) => this.deleteRow(id, e)}>Delete Row</button>
  <button onClick={this.deleteRow.bind(this, id)}>Delete Row</button>
  ```
  - With an arrow function, we have to pass "e" explicitly, but with bind any further arguments are automatically forwarded.
