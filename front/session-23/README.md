
# Session-23
(1401-06-15)

  

## React

  

### Using the State Hook

  

#### Equivalent Class Example

  

```

  

class Example extends React.Component {

  

constructor(props) {

  

super(props);

  

this.state = {

  

count: 0

  

};

  

}

  
  
  

render() {

  

return (

  

<div>

  

<p>You clicked {this.state.count} times</p>

  

<button onClick={() => this.setState({ count: this.state.count + 1 })}>

  

Click me

  

</button>

  

</div>

  

);

  

}

  

}

  

```

  

#### Hooks and Function Components

  

```

const Example = (props) => {

  

// You can use Hooks here!

  

return <div />;

  

}

  

```

  

or

  

```

  

function Example(props) {

  

// You can use Hooks here!

  

return <div />;

  

}

  

```

  

- Hooks don’t work inside classes. But you can use them instead of writing classes.

  

#### What’s a Hook?

  

- What is a Hook?

  

- When would I use a Hook?

  

#### Declaring a State Variable

  

In a function component, we have no this, so we can’t assign or read this.state. Instead, we call the useState Hook directly inside our component:

  

```

  

import React, { useState } from 'react';

  

function Example() {

  

// Declare a new state variable, which we'll call "count" const [count, setCount] = useState(0);

  

```

  

- What does calling useState do?

  

- What do we pass to useState as an argument?

  

- What does useState return?

-

  

```

  

import React, { useState } from 'react';

function Example() {

// Declare a new state variable, which we'll call "count" const [count, setCount] = useState(0);

  

```

  

We declare a state variable called count, and set it to 0. React will remember its current value between re-renders, and provide the most recent one to our function. If we want to update the current count, we can call setCount.

  

#### Reading State

  

- In a function, we can use count directly

  

```

<p>You clicked {count} times</p>

```

  

#### Updating State

  

- In a function, we already have setCount and count as variables so we don’t need this

  

```

<button onClick={() => setCount(count + 1)}> Click me</button>

```

  

#### What Do Square Brackets Mean

  

This JavaScript syntax is called “array destructuring”. It means that we’re making two new variables fruit and setFruit, where fruit is set to the first value returned by useState, and setFruit is the second.

  

```

const [fruit, setFruit] = useState('banana');

```

  

#### Using Multiple State Variables

  

You don’t have to use many state variables. State variables can hold objects and arrays just fine, so you can still group related data together.

  

## CSS

  

### Numbers, lengths, and percentages

  

There are various numeric value types that you might find yourself using in CSS. The following are all classed as numeric:

  

["img for Numbers"](./Nmbers.PNG  "Numbers, lengths, and percentages")

  

#### Lengths

  

The numeric type you will come across most frequently is `<length>`. For example, `10px` (pixels) or `30em`. There are two types of lengths used in CSS — relative and absolute. It's important to know the difference in order to understand how big things will become.

  

##### Absolute length units

  

The following are all absolute length units — they are not relative to anything else, and are generally considered to always be the same size.

  

["img for Absoulte units"](./Absoulte.PNG  "Absolute length units")


  

Most of these units are more useful when used for print, rather than screen output. For example, we don't typically use `cm` (centimeters) on screen. The only value that you will commonly use is `px` (pixels).

  

##### Relative length units

  

Relative length units are relative to something else, perhaps the size of the parent element's font, or the size of the viewport. The benefit of using relative units is that with some careful planning you can make it so the size of text or other elements scales relative to everything else on the page. Some of the most useful units for web development are listed in the table below.

  

["img for Relative units"](./Relative.PNG  "Relative length units")
