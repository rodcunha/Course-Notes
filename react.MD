# Notes on React.js

## The framework

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

## Components

Components are one of React's key features and they enable us to create reusable pieces of code that will ultimately be responsible for returning the HTML necessary to render the page. More often than not, these will be written using JSX.

Since React's main focus is to build the app's UI, there is only one method that is absolutely required in a React component.

### Creating a component

```javascript
class ContactList extends React.Component {
// ...
}
```

### The `render()` method

```javascript
class ContactList extends React.Component {
  render() {
    // some JSX 
   }
}
```
- [Rendering Elements](https://reactjs.org/docs/rendering-elements.html)

A great mindset to have when building React apps is to think in components. Components represent the modularity and reusability of React. You can think of your component classes as factories that produce instances of components. These component classes should follow the single responsibility principle and just "do one thing". If it manages too many different tasks, it may be a good idea to decompose your component into smaller subcomponents.

## Scaffolding the React App

In order to be able to use JSX we will need to transpile the code to JavaScript and therefore need a build tool, the most popular one being Webpack. The nice people at Facebook however have already created a scaffolding platform to start any react app that does all we require to use JSX. To install this we will need to have node installed and to be able to run npm.

### Installing the scaffolding 

`npm install -g create-react-app`

### Instantiating a new app

`create-react-app [name of the app]`

### Yarn Package Manager

Once the instantiation of the new app conpletes we are told to use `yarn start` to start the development server. Yarn is a package manager which is in all similar to npm. Yarn was created from the ground up by Facebook to improve on some key aspects that are slow or lacking in NPM.

If we don't want to install Yarn, we don't have to! What's great about it is that almost every use of yarn can be swapped with npm and everything will work just fine! So if the command is `yarn start`, we can use `npm start` to run the same command.

### Create React App Resources

- [GitHub Repo](https://github.com/facebookincubator/create-react-app)
- [Create React App Release Post](https://reactjs.org/blog/2016/07/22/create-apps-with-no-configuration.html)
- [Updates to create-react-app from the React blog](https://reactjs.org/blog/2017/05/18/whats-new-in-create-react-app.html)

## State

State is an object that determines how that particular component renders and behaves. In other words, it is what allows us to have dynamic and interactive components.

#### A quick analogy to explain state

This might seem trivial, but please take a moment to consider this question: What’s the difference between water and ice?

That’s right — the temperature! Now, let's go one level deeper: what is “temperature”? The answer is that it’s a measurement of thermal energy — the key word for us being measurement, because that implies it is tracked with a known value (any number between absolute zero and absolute hot).

If you think about it, that’s kind of incredible. If you can change the value on a thermometer, that means you have the ability to put a piece of matter into a different state. With water, simply put it in your freezer (below 32F) and its state will change from liquid to a solid. If you put it on a hot stovetop (above 212F), its state will change from liquid to gas. All of this can be done just by changing one value: its temperature.

What if we could do the same thing with programs? What if we could define a set of properties that would determine how our program would behave in any situation, similarly to water’s relationship with temperature?

### Building UI State

In order to build an app correctly, we need to identify the minimal amount of state the app will need. For this we will follow the DRY (Don't Repeat Yourself) rule. We need to figure out the absolute minimal representation of state the app requires and compute everything else we need on demand.

## Other notes



### Where should state live?
