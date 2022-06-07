# Readings: React 2

Below you will find some reading material, code samples, and some additional resources that support today’s topic and the upcoming lecture.

Review the Submission Instructions for guidance on completing and submitting this assignment.

## Reading
All Contents Reference the corresponding Links Below. 

[React - Conditional Rendering](https://reactjs.org/docs/conditional-rendering.html)

In React, you can create distinct components that encapsulate behavior you need. Then, you can render only some of them, depending on the state of your application.

**Conditional rendering**
in React works the same way conditions work in JavaScript. Use JavaScript operators like if or the conditional operator to create elements representing the current state, and let React update the UI to match them.

**Element Variables**
You can use variables to store elements. This can help you conditionally render a part of the component while the rest of the output doesn’t change.

**Preventing Component from Rendering** 
In rare cases you might want a component to hide itself even though it was rendered by another component. To do this return null instead of its render output.


[React - Lists & Keys](https://reactjs.org/docs/lists-and-keys.html)
**Lists and Keys**
Given the code below, we use the map() function to take an array of numbers and double their values. We assign the new array returned by map() to the variable doubled and log it:
```javascript
const numbers = [1, 2, 3, 4, 5];
const doubled = numbers.map((number) => number * 2);
console.log(doubled);
```
This code logs [2, 4, 6, 8, 10] to the console.

**Rendering Multiple Components**
You can build collections of elements and include them in JSX using curly braces {}.

**Basic List Component**
Usually you would render lists inside a component.

**Keys**

Keys help React identify which items have changed, are added, or are removed. Keys should be given to the elements inside the array to give the elements a stable identity

**Extracting Components with Keys**

Keys only make sense in the context of the surrounding array.
6
For example, if you extract a `ListItem` component, you should keep the key on the `<ListItem />` elements in the array rather than on the `<li>` element in the `ListItem` itself.

**Keys Must Only Be Unique Among Siblings**

Keys used within arrays should be unique among their siblings. However, they don’t need to be globally unique. We can use the same keys when we produce two different arrays

[React - Forms](https://reactjs.org/docs/forms.html)
**Forms**
HTML form elements work a bit differently from other DOM elements in React, because form elements naturally keep some internal state. For example, this form in plain HTML accepts a single name:
```
<form>
  <label>
    Name:
    <input type="text" name="name" />
  </label>
  <input type="submit" value="Submit" />
</form>
```

This form has the default HTML form behavior of browsing to a new page when the user submits the form. If you want this behavior in React, it just works. But in most cases, it’s convenient to have a JavaScript function that handles the submission of the form and has access to the data that the user entered into the form. The standard way to achieve this is with a technique called “controlled components”.

**Controlled Components**
In HTML, form elements such as `<input>`, `<textarea>`, and `<select>` typically maintain their own state and update it based on user input. In React, mutable state is typically kept in the state property of components, and only updated with setState().

We can combine the two by making the React state be the “single source of truth”. Then the React component that renders a form also controls what happens in that form on subsequent user input. An input form element whose value is controlled by React in this way is called a “controlled component”.

**Handling Multiple Inputs**
When you need to handle multiple controlled input elements, you can add a name attribute to each element and let the handler function choose what to do based on the value of event.target.name.

**Alternatives to Controlled Components**
It can sometimes be tedious to use controlled components, because you need to write an event handler for every way your data can change and pipe all of the input state through a React component. This can become particularly annoying when you are converting a preexisting codebase to React, or integrating a React application with a non-React library. In these situations, you might want to check out uncontrolled components, an alternative technique for implementing input forms.

[React - Lifting State](https://reactjs.org/docs/lifting-state-up.html)
**Lifting State Up**
Often, several components need to reflect the same changing data. We recommend lifting the shared state up to their closest common ancestor. Let’s see how this works in action.
You can add a second input as well

Let’s recap what happens when you edit an input:

-   React calls the function specified as `onChange` on the DOM `<input>`. In our case, this is the `handleChange` method in the `TemperatureInput` component.
-   The `handleChange` method in the `TemperatureInput` component calls `this.props.onTemperatureChange()` with the new desired value. Its props, including `onTemperatureChange`, were provided by its parent component, the `Calculator`.
-   When it previously rendered, the `Calculator` had specified that `onTemperatureChange` of the Celsius `TemperatureInput` is the `Calculator`’s `handleCelsiusChange` method, and `onTemperatureChange` of the Fahrenheit `TemperatureInput` is the `Calculator`’s `handleFahrenheitChange` method. So either of these two `Calculator` methods gets called depending on which input we edited.
-   Inside these methods, the `Calculator` component asks React to re-render itself by calling `this.setState()` with the new input value and the current scale of the input we just edited.
-   React calls the `Calculator` component’s `render` method to learn what the UI should look like. The values of both inputs are recomputed based on the current temperature and the active scale. The temperature conversion is performed here.
-   React calls the `render` methods of the individual `TemperatureInput` components with their new props specified by the `Calculator`. It learns what their UI should look like.
-   React calls the `render` method of the `BoilingVerdict` component, passing the temperature in Celsius as its props.
-   React DOM updates the DOM with the boiling verdict and to match the desired input values. The input we just edited receives its current value, and the other input is updated to the temperature after conversion.

[React - Composition vs Inheritance](https://reactjs.org/docs/composition-vs-inheritance.html)

**Composition vs Inheritance**
React has a powerful composition model, and we recommend using composition instead of inheritance to reuse code between components.

**Containment**
Some components don’t know their children ahead of time. This is especially common for components like `Sidebar` or `Dialog` that represent generic “boxes”.

**Specialization**
Sometimes we think about components as being “special cases” of other components. For example, we might say that a `WelcomeDialog` is a special case of `Dialog`.

**So What About Inheritance?**
""At Facebook, we use React in thousands of components, and we haven’t found any use cases where we would recommend creating component inheritance hierarchies.""

[Thinking in React](https://reactjs.org/docs/thinking-in-react.html)
**Thinking in React**
React is, in our opinion, the premier way to build big, fast Web apps with JavaScript. It has scaled very well for us at Facebook and Instagram.

- Step 1: Break The UI Into A Component Hierarchy
- Step 2: Build A Static Version in React
- Step 3: Identify The Minimal (but complete) Representation Of UI State
- Step 4: Identify Where Your State Should Live
- Step 5: Add Inverse Data Flow

## Videos

Optional: [Hero Icons](https://www.youtube.com/watch?v=cVa1UiKPJN8)

## Bookmark and Review

[React - Comprehensive Guide](https://tylermcginnis.com/reactjs-tutorial-a-comprehensive-guide-to-building-apps-with-react/)

[Heroicons](https://heroicons.com/)