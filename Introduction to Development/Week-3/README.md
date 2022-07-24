# Welcome to the Week 3 of Learner's Space React & NextJS!

The outline for this week is as follows:

<ul>
<li>Props in React</li>
<li> State of an application </li>
<li> Lifecycle </li>
<li> React Hooks </li>
<li> React Custom Hooks </li>
</ul>

## What are props in React JS?

By now we know that React components are Javascript functions. These functions accept arbitrary inputs known as <b>props</b> (properties or arguments) and then these components return react elements describing what should appear on the screen.

We use props in React JS to pass data from one component to another. Ideally the props should be passed from a parent component to a child component. Props are generally useful when we want the flow of data in our app to be dynamic.

For those who understand better by looking at some examples: <a href = "https://www.freecodecamp.org/news/how-to-use-props-in-react/"> this is a great article</a> and this is a <a href = "https://www.youtube.com/watch?v=m7OWXtbiXX8&ab_channel=Codevolution"> great video tutorial</a>.

I am personally a big fan of React JS official documentation so do check out <a href = "https://reactjs.org/docs/components-and-props.html">this official docs page</a> to deepen your understanding about React components and props.

## State of an application in React JS

The state is an instance of React Component Class and it can be defined as an object of a set of observable properties that control the behavior of the component. In other words, the State of a component is an object that holds some information that may change over the lifetime of the component.

The state in a component can change over time. The change in state over time can happen as a response to user action or system event. A component with the state is known as stateful components. It is the heart of the react component which determines the behavior of the component and how it will render. They are also responsible for making a component dynamic and interactive.

The react components can be of two types:

<ul>
<li>Stateless Components</li>
<li>Stateful Components</li>
</ul>
If you remember the landing page of the first React app bootstrapped from <b>Create React App or Vite</b>, there was a component displaying a counter and the value of the counter increased if you clicked on it. That component was a stateful component.
<br></br>
At this point of time, you might feel overwhelmed by state, props and the difference between these two, so I'd suggest you to follow along <a href = "https://www.youtube.com/watch?v=dMH1_YtUTSQ&ab_channel=DevEd">this video </a> and the concepts would make much more sense to you.
<br></br>

## Difference between State and Props

Although you might have understood the differences by watching the video recommended in the last section, this topic is just to make the differences absolutely clear and emphasize on their importance so that you can follow good design principles later on.

<ol>
<li>Props and state are both plain JavaScript objects, both hold information that influences the output of render.</li>
<li>Props get passed to the component (very similar to function parameters) whereas state is managed within the component (very similar to variables declared inside a function).</li>
</ol>

For those who want to get into finer details, please <a href= "https://github.com/uberVU/react-guide/blob/master/props-vs-state.md"> refer this amazing article</a>.

## Hooks in React JS

Hooks allow function components to have access to state and other React features. Because of this, class components are generally no longer needed.

Before learning about hooks, let's revise some core react concepts:

### Stateful vs Stateless functions

<ul>
<li>A stateful component declares and manages local state in it</li>
<li>A stateless component is a pure function that doesn't have a local state and side-effects to manage</li>
</ul>

### Pure functions in React JS

A pure function is a function without any side-effects. This means that a function always returns the same output for the same input.

### React Hooks and Stateful Logic

With React Hooks, we can isolate stateful logic and side-effects from a functional component. Hooks are JavaScript functions that manage the state's behaviour and side effects by isolating them from a component.

So, we can now isolate all the stateful logic in hooks and use (compose them, as hooks are functions, too) into the components.

The question is, what is this stateful logic? It can be anything that needs to declare and manage a state variable locally.

For example, the logic to fetch data and manage the data in a local variable is stateful. We may also want to reuse the fetching logic in multiple components.

<b>React Hooks are simple JavaScript functions that we can use to isolate the reusable part from a functional component. Hooks can be stateful and can manage side-effects.</b>

I hope you got the meaning of a react hook, if yes, its absolutely necessary for you to read the five articles that I am providing here and keep on reading and implementing these articles till you aren't absolutely clear with them.

<ul>
<li><a href = "https://reactjs.org/docs/hooks-intro.html"> Introduction to Hooks</a></li>
<li><a href = "https://reactjs.org/docs/hooks-overview.html">Hooks at Glance</a></li>
<li><a href = "https://reactjs.org/docs/hooks-state.html">Using the State Hook</a></li>
<li><a href = "https://reactjs.org/docs/hooks-effect.html">Using the Effect Hook</a></li>
<li><a href = "https://reactjs.org/docs/hooks-rules.html">Rules of Hooks</a></li>
</ul>

Well, I hope you had a good time reading these articles and now you have a deeper understanding of React Hooks. Now its time for actually creating something.

Please follow along <a href = "https://www.youtube.com/watch?v=_N6LQd6Y2UY&ab_channel=ChrisBlakely">this</a> tutorial to create a basic app using React Hooks!

## Custom Hooks

Building your own Hooks lets you extract component logic into reusable functions. A custom Hook is a JavaScript function whose name starts with ”use” and that may call other Hooks. Read <a href = "https://reactjs.org/docs/hooks-custom.html">this official documentation</a> inorder to start building your own hooks. You can also watch <a href = "https://www.youtube.com/watch?v=O6FhJvcvVOE&ab_channel=JavaScriptMastery">this video</a> and code side by side to build your own react hooks. 

## Assignment: Week-3
--Coming Soon--
