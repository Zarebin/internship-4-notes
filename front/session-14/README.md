# Session14
(1401/05/30)

## React

- Often, several components need to reflect the same changing data.React recommend lifting shared state up to their closest common ancestor.

- React explain lifting state up by creating a program consisted of two input boxs in which changing a input box would effect the other one. 

### TemperatureInput components are like :

```
class TemperatureInput extends React.Component {
  constructor(props) {
    super(props);
    this.handleChange = this.handleChange.bind(this);
  }

  handleChange(e) {
    this.props.onTemperatureChange(e.target.value);  }

  render() {
    const temperature = this.props.temperature;    const scale = this.props.scale;
    return (
      <fieldset>
        <legend>Enter temperature in {scaleNames[scale]}:</legend>
        <input value={temperature}
               onChange={this.handleChange} />
      </fieldset>
    );
  }
}

```
### Calculator component(source of truth or closest common ancestor for TemperatureInput components )

```
class Calculator extends React.Component {
  constructor(props) {
    super(props);
    this.handleCelsiusChange = this.handleCelsiusChange.bind(this);
    this.handleFahrenheitChange = this.handleFahrenheitChange.bind(this);
    this.state = {temperature: '', scale: 'c'};  }

  handleCelsiusChange(temperature) {
    this.setState({scale: 'c', temperature});  }

  handleFahrenheitChange(temperature) {
    this.setState({scale: 'f', temperature});  }

  render() {
    const scale = this.state.scale;    const temperature = this.state.temperature;    const celsius = scale === 'f' ? tryConvert(temperature, toCelsius) : temperature;    const fahrenheit = scale === 'c' ? tryConvert(temperature, toFahrenheit) : temperature;
    return (
      <div>
        <TemperatureInput
          scale="c"
          temperature={celsius}          onTemperatureChange={this.handleCelsiusChange} />        <TemperatureInput
          scale="f"
          temperature={fahrenheit}          onTemperatureChange={this.handleFahrenheitChange} />        <BoilingVerdict
          celsius={parseFloat(celsius)} />      </div>
    );
  }
}

```
### What happens when we edit an input.

- React calls the function specified as onChange on the DOM <input>. In our case, this is the handleChange method in the TemperatureInput component.

- The handleChange method in the TemperatureInput component calls this.props.onTemperatureChange() with the new desired value. Its props, including onTemperatur  eChange, were provided by its parent component, the Calculator.

- When it previously rendered, the Calculator had specified that onTemperatureChange of the Celsius TemperatureInput is the Calculator’s handleCelsiusChange      method, and onTemperatureChange of the Fahrenheit TemperatureInput is the Calculator’s handleFahrenheitChange method. So either of these two Calculator         methods gets called depending on which input we edited.

- Inside these methods, the Calculator component asks React to re-render itself by calling this.setState() with the new input value and the current scale of the  input we just edited.

- React calls the Calculator component’s render method to learn what the UI should look like. The values of both inputs are recomputed based on the current       temperature and the active scale. The temperature conversion is performed here.

- React calls the render methods of the individual TemperatureInput components with their new props specified by the Calculator. It learns what their UI should   look like.

- React calls the render method of the BoilingVerdict component, passing the temperature in Celsius as its props.

- React DOM updates the DOM with the boiling verdict and to match the desired input values. The input we just edited receives its current value, and the other    input is updated to the temperature after conversion.

## Js

### Coercive Comparisons

1- What is the meaning of Coercion?
 Coercion means a value of one type being converted to its respective representation in another type (to whatever extent possible)
 
2- What is the different between == and ===?

 - Between the same value type:
 In fact, both operators consider the type of the values being compared. And if the comparison is between the same value type, both == and === do exactly the same thing, no difference whatsoever.
 
 - Between different value type:
  The == differs from === in that it allows coercion before the comparison.
  Once the types have been converted to be the same on both sides, then == does the same thing as === .
  
 3- Use relational comparison operators :
  They'll allow coercion first (generally, to numbers) if the types differ.
  In the case where both values being compared are already strings; in this case, they use alphabetical (dictionary-like) comparison of the strings



















