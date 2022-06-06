# Readings: React 1

Below you will find some reading material, code samples, and some additional resources that support today’s topic and the upcoming lecture.

Review the Submission Instructions for guidance on completing and submitting this assignment.

## NOTE

There’s a fair amount to read/watch here. So give everything at least a skim and plan on referring back to it later as we learn these new tools.

## ES6 Overview

[ES6 Syntax and Feature Overview](https://www.taniarascia.com/es6-syntax-and-feature-overview/)

Covered in this Article: 
- Variable declaration
- Constant declaration
- Arrow function syntax
- Template literals
- Implicit returns
- Key/property shorthand
- Method definition shorthand
- Destructuring (object matching)
- Array iteration (looping)
- Default parameters
- Spread syntax
- Classes/constructor functions
- Inheritance
- Modules - export/import
- Promises/callbacks

|Keyword|Scope|Hoisting|Can be Reassigned|Can be Redeclared|
|---|---|---|---|---|---|
|var|function scope|yes|yes|yes|
|let|block scope|no|yes|no|
|const|block scope|no|no|no|
### Variable declaration

ES6 introduced the `let` keyword, which allows for block-scoped variables which cannot be hoisted or redeclared.

### Constant declaration

ES6 introduced the `const` keyword, which cannot be redeclared or reassigned, but is not immutable.

### Arrow functions

The arrow function expression syntax is a shorter way of creating a function expression. Arrow functions do not have their own `this`, do not have prototypes, cannot be used for constructors, and should not be used as object methods.

### Concatenation/string interpolation

Expressions can be embedded in template literal strings.

### Multi-line strings

Using template literal syntax, a JavaScript string can span multiple lines without the need for concatenation.

### Implicit returns

The `return` keyword is implied and can be omitted if using arrow functions without a block body.

### Key/property shorthand

ES6 introduces a shorter notation for assigning properties to variables of the same name.

### Method definition shorthand

The `function` keyword can be omitted when assigning methods on an object.

### Destructuring (object matching)

Use curly brackets to assign properties of an object to their own variable.

### Array iteration (looping)

A more concise syntax has been introduced for iteration through arrays and other iterable objects.

### Default parameters

Functions can be initialized with default parameters, which will be used only if an argument is not invoked through the function.

### Spread syntax

Spread syntax can be used to expand an array.

### Classes/constructor functions

ES6 introducess the `class` syntax on top of the prototype-based constructor function.

### Inheritance

The `extends` keyword creates a subclass.

### Modules - export/import

Modules can be created to export and import code between files.

### Promises/Callbacks

Promises represent the completion of an asynchronous function. They can be used as an alternative to chaining functions.

## React

[React - Hello World](https://reactjs.org/docs/hello-world.html)

This is just an intro and how to read the guide!

[React - JSX](https://reactjs.org/docs/introducing-jsx.html)

#### Why JSX?

React embraces the fact that rendering logic is inherently coupled with other UI logic: how events are handled, how the state changes over time, and how the data is prepared for display.

Instead of artificially separating _technologies_ by putting markup and logic in separate files, React [separates _concerns_](https://en.wikipedia.org/wiki/Separation_of_concerns) with loosely coupled units called “components” that contain both. We will come back to components in a [further section](https://reactjs.org/docs/components-and-props.html), but if you’re not yet comfortable putting markup in JS, [this talk](https://www.youtube.com/watch?v=x7cQ3mrcKaY) might convince you otherwise.

React [doesn’t require](https://reactjs.org/docs/react-without-jsx.html) using JSX, but most people find it helpful as a visual aid when working with UI inside the JavaScript code. It also allows React to show more useful error and warning messages.

[React - Rendering Elements](https://reactjs.org/docs/rendering-elements.html)
## Rendering an Element into the DOM

Let’s say there is a `<div>` somewhere in your HTML file:

```
<div id="root"></div>
```

We call this a “root” DOM node because everything inside it will be managed by React DOM.

Applications built with just React usually have a single root DOM node. If you are integrating React into an existing app, you may have as many isolated root DOM nodes as you like.

To render a React element, first pass the DOM element to [`ReactDOM.createRoot()`](https://reactjs.org/docs/react-dom-client.html#createroot), then pass the React element to `root.render()`:

```
const root = ReactDOM.createRoot(
  document.getElementById('root')
);
const element = <h1>Hello, world</h1>;
root.render(element);
```

[React - Components & Props](https://reactjs.org/docs/components-and-props.html)
## Function and Class Components

The simplest way to define a component is to write a JavaScript function:

```
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}
```

This function is a valid React component because it accepts a single “props” (which stands for properties) object argument with data and returns a React element. We call such components “function components” because they are literally JavaScript functions.

You can also use an [ES6 class](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Classes) to define a component:

```
class Welcome extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}</h1>;
  }
}
```

The above two components are equivalent from React’s point of view.

[React - State & Lifecycle](https://reactjs.org/docs/state-and-lifecycle.html)

## Converting a Function to a Class

You can convert a function component like `Clock` to a class in five steps:

1.  Create an [ES6 class](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Classes), with the same name, that extends `React.Component`.
2.  Add a single empty method to it called `render()`.
3.  Move the body of the function into the `render()` method.
4.  Replace `props` with `this.props` in the `render()` body.
5.  Delete the remaining empty function declaration.

## Adding Local State to a Class

We will move the `date` from props to state in three steps:

1.  Replace `this.props.date` with `this.state.date` in the `render()` method
2. 2.  Add a [class constructor](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Classes#Constructor) that assigns the initial `this.state`
3. 3.  Remove the `date` prop from the `<Clock />` element


#### Let’s quickly recap what’s going on and the order in which the methods are called:

1.  When `<Clock />` is passed to `root.render()`, React calls the constructor of the `Clock` component. Since `Clock` needs to display the current time, it initializes `this.state` with an object including the current time. We will later update this state.
2.  React then calls the `Clock` component’s `render()` method. This is how React learns what should be displayed on the screen. React then updates the DOM to match the `Clock`’s render output.
3.  When the `Clock` output is inserted in the DOM, React calls the `componentDidMount()` lifecycle method. Inside it, the `Clock` component asks the browser to set up a timer to call the component’s `tick()` method once a second.
4.  Every second the browser calls the `tick()` method. Inside it, the `Clock` component schedules a UI update by calling `setState()` with an object containing the current time. Thanks to the `setState()` call, React knows the state has changed, and calls the `render()` method again to learn what should be on the screen. This time, `this.state.date` in the `render()` method will be different, and so the render output will include the updated time. React updates the DOM accordingly.
5.  If the `Clock` component is ever removed from the DOM, React calls the `componentWillUnmount()` lifecycle method so the timer is stopped.


[React - Handling Events](https://reactjs.org/docs/handling-events.html)


Handling events with React elements is very similar to handling events on DOM elements. There are some syntax differences:

-   React events are named using camelCase, rather than lowercase.
-   With JSX you pass a function as the event handler, rather than a string.

For example, the HTML:

```
<button onclick="activateLasers()">
  Activate Lasers
</button>
```

is slightly different in React:

```
<button onClick={activateLasers}>  Activate Lasers
</button>
```

## Tailwind CSS

[Utility First CSS](https://tailwindcss.com/docs/utility-first)

Traditionally, whenever you need to style something on the web, you write CSS.

With Tailwind, you style elements by applying pre-existing classes directly in your HTML.
Example:
```css
<div class="p-6 max-w-sm mx-auto bg-white rounded-xl shadow-lg flex items-center space-x-4"> 
	<div class="shrink-0"> 
		<img class="h-12 w-12" src="/img/logo.svg" alt="ChitChat Logo"> 
	</div> 
	<div> 
		<div class="text-xl font-medium text-black">ChitChat</div> 
		<p class="text-slate-500">You have a new message!</p> 
	</div> 
</div>
```

In the example above, we’ve used:

-   Tailwind’s [flexbox](https://tailwindcss.com/docs/display#flex) and [padding](https://tailwindcss.com/docs/padding) utilities (`flex`, `shrink-0`, and `p-6`) to control the overall card layout
-   The [max-width](https://tailwindcss.com/docs/max-width) and [margin](https://tailwindcss.com/docs/margin) utilities (`max-w-sm` and `mx-auto`) to constrain the card width and center it horizontally
-   The [background color](https://tailwindcss.com/docs/background-color), [border radius](https://tailwindcss.com/docs/border-radius), and [box-shadow](https://tailwindcss.com/docs/box-shadow) utilities (`bg-white`, `rounded-xl`, and `shadow-lg`) to style the card’s appearance
-   The [width](https://tailwindcss.com/docs/width) and [height](https://tailwindcss.com/docs/height) utilities (`w-12` and `h-12`) to size the logo image
-   The [space-between](https://tailwindcss.com/docs/space) utilities (`space-x-4`) to handle the spacing between the logo and the text
-   The [font size](https://tailwindcss.com/docs/font-size), [text color](https://tailwindcss.com/docs/text-color), and [font-weight](https://tailwindcss.com/docs/font-weight) utilities (`text-xl`, `text-black`, `font-medium`, etc.) to style the card text

[Tailwind in 15 minutes](https://www.youtube.com/watch?v=6zIuAyLZPH0)
Video is private :( 

## Next.js

[Learn Next.js](https://nextjs.org/learn/basics/create-nextjs-app)

To build a complete web application with React from scratch, there are many important details you need to consider:

-   Code has to be bundled using a bundler like webpack and transformed using a compiler like Babel.
-   You need to do production optimizations such as code splitting.
-   You might want to statically pre-render some pages for performance and SEO. You might also want to use server-side rendering or client-side rendering.
-   You might have to write some server-side code to connect your React app to your data store.

Next.js aims to have best-in-class developer experience and many built-in features, such as:

-   An intuitive [page-based](https://nextjs.org/docs/basic-features/pages) routing system (with support for [dynamic routes](https://nextjs.org/docs/routing/dynamic-routes))
-   [Pre-rendering](https://nextjs.org/docs/basic-features/pages#pre-rendering), both [static generation](https://nextjs.org/docs/basic-features/pages#static-generation-recommended) (SSG) and [server-side rendering](https://nextjs.org/docs/basic-features/pages#server-side-rendering) (SSR) are supported on a per-page basis
-   Automatic code splitting for faster page loads
-   [Client-side routing](https://nextjs.org/docs/routing/introduction#linking-between-pages) with optimized prefetching
-   [Built-in CSS](https://nextjs.org/docs/basic-features/built-in-css-support) and [Sass support](https://nextjs.org/docs/basic-features/built-in-css-support#sass-support), and support for any [CSS-in-JS](https://nextjs.org/docs/basic-features/built-in-css-support#css-in-js) library
-   Development environment with [Fast Refresh](https://nextjs.org/docs/basic-features/fast-refresh) support
-   [API routes](https://nextjs.org/docs/api-routes/introduction) to build AP

[Why to use Next.js](https://www.youtube.com/watch?v=rtgbaKBhdkk)
He thinks the future of React is Next.js
Talk about 5 things about next.js
1. background
2. performance
3. developer experience
4. deployment
5. community

next.js is a framework built ontop of react. Lets you choose if you want to render on client, dev or both sides.

