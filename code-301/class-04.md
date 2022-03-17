## Readings: React and Forms
Below you will find some reading material, code samples, and some additional resources that support today’s topic and the upcoming lecture.

Review the Submission Instructions for guidance on completing and submitting this assignment.

## Reading
[React Docs - Forms](https://reactjs.org/docs/forms.html)

* What is a ‘Controlled Component’?
  * In HTML forms maintain their own state, but in react mutable states are kept in the state property of components and updated with setState(). Combining both ideas React components render a form that also controls what happens to that form upon user input. This is what is called a Controlled Component. 
* Should we wait to store the users responses from the form into state when they submit the form OR should we update the state with their responses as soon as they enter them? Why.
  * I think they were saying to update the state with their responses as soon as they enter them since their handleChange method updates on every keystroke. I think this is to keep the state dynamic and interactive with the user. 
* How do we target what the user is entering if we have an event handler on an input field?
  * they used the code to grab what the user is entering 
  ```js
  handleChange(event){
    this.setState({value: event.target.value});
  }
  <input type='text' value={this.state.value} onChange={this.handleChange}/>
  ```

[The Conditional (Ternary) Operator Explained](https://codeburst.io/javascript-the-conditional-ternary-operator-explained-cac7218beeff)

* Why would we use a ternary operator?
   * if you have a simple if statement returning true or false then ternary provides a simple and clean way to express this on one line. 
* Rewrite the following statement using a ternary statement:

``` js
if(x===y){
  console.log(true);
} else {
  console.log(false);
}
```

```js
x===y ? true : false;
```

## Bookmark/Skim
[React Bootstrap - Forms](https://react-bootstrap.github.io/forms/overview/)
[React Docs - conditional rendering](https://reactjs.org/docs/conditional-rendering.html)

## Things I want to know more about


## Stream of conscious reading notes 
1. HTML forms work different than other DOM elements in react. 
Naturally the elements keep some internal state. 
The form has the default html behavior of browsing to a new page when the user submits the form
if you want this behavior in react it just works. 
in most cases its convenient to have a js function that handles the submission of the form and has access to the data that the user entered
the standard way to achieve this is with controlled components. 
Combining the two ways of html forms and the mutable state in react 
"single source of truth" 
then the react component that renders a form also controls what happens ini that form on subsequent user input
an input form element whose value is controlled by react in this way is what they call a controlled component

``` js
class NameForm extends React.component {
  constructor(props) {
    super(props);
    this.state = {value: ''};
    
    this.handleChange = this.handleChange.bind(this);
    this.handleSubmit = this.handleSubmit.bind(this);
  }
  handleChange(event){
    this.setState({value: event.target.value});
  }
  handleSubmit(event){
    alert('A name was submitted: ' + this.state.value);
    event.preventDefault();
  }
  render() {
    return (
      <form onSubmit={this.handleSubmit}>
        <label>
          Name:
          <input type="text" value={this.state.value} onChange={this.handleChange}/>
        </label>
        <input type="submit" value="Submit" />
      </form>
    );
  }
}
```
since the value attribute is set on the form element the displayed value will always be this.state.value 
making the react state the source of truth
since handleChange Runs on every keystroke to update the react state the displayed value will update as the user types

with a controlled component, the input's value is driven by the react state. 
this means you have to type a bit more code you can now pass the value to other UI elements too or reset it from other handlers

#### Textarea tag 
in html a textarea element defines its text by its children 

```html
<textarea>
  Hello there, this is some text in a text area
</textarea>
```

In react a textarea uses a value attribute instead. this way a form using a textarea can be written similarly to a form that uses a single line input

```js
class EssayForm extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      value: 'Please write an essay about your favorite DOM element'
    };
    this.handleChange = this.handleChange.bind(this);
    this.handleSubmit = this.handleSubmit.bind(this);
  }
  handleChange(event){
    this.setState({value: event.target.value});
  }
  handleSubmit(event){
    alert('An essay was submitted: ' + this.state.value);
    event.preventDefault();
  }
  render(){
    return (
      <form onSubmit={this.handleSubmit}>
        <label>
          Essay:
            <textarea value={this.state.value} onChange={this.handleChange}/>
        </label>
        <input type="submit" value="Submit"/>
      </form>
    );
  }
}
```

#### Select tag
Select can be used to create a drop-down list 
Select in html 
```html
<select>
  <option value="grapefruit">Grapefruit</option>
  <option value="lime">Lime</option>
  <option selected value="coconut">Coconut</option>
  <option value="mango">Mango</option>
</select>
```

Select in React
```js 
class FlavorForm extends React.Component {
  constructor(props) {
    super(props);
    this.state = {value: 'coconut'};

    this.handleChange = this.handleChange.bind(this);
    this.handleSubmit = this.handleSubmit.bind(this);
  }

  handleChange(event) {
    this.setState({value: event.target.value});
  }

  handleSubmit(event) {
    alert('Your favorite flavor is: ' + this.state.value);
    event.preventDefault();
  }

  render() {
    return (
      <form onSubmit={this.handleSubmit}>
        <label>
          Pick your favorite flavor:
          <select value={this.state.value} onChange={this.handleChange}>
            <option value="grapefruit">Grapefruit</option>
            <option value="lime">Lime</option>
            <option value="coconut">Coconut</option>
            <option value="mango">Mango</option>
          </select>
        </label>
        <input type="submit" value="Submit" />
      </form>
    );
  }
}
```
