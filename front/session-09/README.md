# session9(js)
## what is interpertation?
- in interpret code execute line by line
- in compile first source code parsed and then change to AST
- js is a parsed and compiled language
  1. After a program leaves a developer's editor, it gets transpiled by Babel, then packed by Webpack (and perhaps half a dozen other build processes), then it gets delivered in that very different form to a JS engine.
  2. The JS engine parses the code to an AST
  3. Then the engine converts that AST to a kind-of byte code, a binary intermediate representation (IR), which is then refined/converted even further by the optimizing JIT compiler.
  4. Finally, the JS VM executes the program.
![flow of js source program](https://github.com/getify/You-Dont-Know-JS/raw/2nd-ed/get-started/images/fig3.png)
- **JS is a compiled language**

# React(1401.05.23)

## Handling Events

 [Source link](https://reactjs.org/docs/handling-events.html)

 - React events are named using camelCase
 - pass a function as the event handler

 `
        <button onClick={activateLasers}>
                Activate Lasers
        </button>
 `

 - to prevent default behavior in React ,You must call preventDefault explicitly.
 - In JavaScript, class methods are not bound by default.
 - This is not React-specific behavior; it is a part of how functions work in JavaScript. Generally, if you refer to a method without () after it, such as                           onClick={this.handleClick}, you should bind that method.
 
 ### 3 ways to use the event handler:

  #### 1- you should bind that method
         `
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
     `
     
 #### 2- You can use public class fields syntax to correctly bind callbacks
        `
                class LoggingButton extends React.Component {
                  // This syntax ensures `this` is bound within handleClick.  handleClick = () => {    console.log('this is:', this);  };  render() {
                    return (
                      <button onClick={this.handleClick}>
                        Click me
                      </button>
                    );
                  }
                }
        `
 
  #### 3- you can use an arrow function in the callback
        `
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
        `
 > We generally recommend binding in the constructor or using the class fields syntax, to avoid this sort of performance problem.

 ### Passing Arguments to Event Handlers
  - Inside a loop, it is common to want to pass an extra parameter to an event handler.

  `
  <button onClick={(e) => this.deleteRow(id, e)}>Delete Row</button>
  <button onClick={this.deleteRow.bind(this, id)}>Delete Row</button>
  `
  - With an arrow function, we have to pass "e" explicitly, but with bind any further arguments are automatically forwarded.

# css- 01.05.22

- Structual Selectors Level4

- [:nth-child(An+B)[of s]](https://estelle.github.io/CSS/selectors/index2.html#slide13)

   -  Question:  What is the specifity for :nth-child(An+B) ?   Answer: 0-1-0

   - [example](https://estelle.github.io/CSS/selectors/index2.html#slide14)
       
- [:root](https://estelle.github.io/CSS/selectors/index2.html#slide16)

   -  Question:  What is :root used for ?
     1. Declare font-size on :root if using rem units
     2. Style :root only if showing `<head>`
     3. In CSS4, define Defining Variables on root.

   - [example](https://estelle.github.io/CSS/selectors/exercises/19_root.html)

- [:not()](https://estelle.github.io/CSS/selectors/index2.html#slide1

   - Question: What is the difference between E:not(s1, s2) & E:not(s1):not(s2) ?
   - [Answer](https://developer.mozilla.org/en-US/docs/Web/CSS/:not)

   - [example](https://estelle.github.io/CSS/selectors/index2.html#slide21)
