# Notes on React.js

## The framewoek

React is a declarative framework centered on the V of MVC. React uses mostly javascript to transform a Virtual DOM that will then be used to update the actual DOM.

[The React API] (https://reactjs.org/docs/react-api.html)

## Usage

### Creating elements

`React.createElement('type', 'prop', 'content')`

This must return a single root element, we would normally use `div` or `span` to represent that type of element but the content can be another React element.

Let's break down what each item can be:

`type` – either a string or a React Component
This can be a string of any existing HTML element (e.g. 'p', 'span', or 'header') or you could pass a React component (we'll be creating components with JSX, in just a moment).

`props` – either null or an object
This is an object of HTML attributes and custom data about the element.

`content` – null, a string, a React Element, or a React Component
Anything that you pass here will be the content of the rendered element. This can include plain text, JavaScript code, other React elements, etc.

Note: when passing a html class property it is worth noting that this should be done using the DOM element node className rather than the html string class which would be invalid from a React perspective.




#### When using arrays for elements
It is important to remember that when creating elements using an array, a unique key property (prop) will be required or else a js error will display in the console.



## JSX

JSX is a syntax extension in JavaScript that lets us write JS code that looks a lot like HTML making it more concise and easy to follow.

In order to evaluate a JS expression the code needs to be enveloped in curly braces `{expression here}`

Even though we are unsing JSX on the editor, when compiled the code will still compile to native JavaScript code.

JSX must return only a single element. This element may have any number of descendents but there must be just one single root element wrapping all the JSX code. This is usually a `div` or `span` element.

```javascript
const message = (
  <div>
    <h1>All About JSX:</h1>
    <ul>
      <li>JSX</li>
      <li>is</li>
      <li>awesome!</li>
    </ul>
  </div>
);
```




