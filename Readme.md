# React Interview Prep

# Question1: what is React and what are its features?
- React was created by jordane walke , a software engineer at facebook in the year 2011 and it was deployed at facebook newsfeed and later it was used in facebook and instagram. 

- React is  a open source front end js library created by facebook in 2011.it follows the component based approach for building reusable UI component for SPA and it is used for developing interactive view layer of web and mobile application.

## what are its features?

- JSX (JavaScript Syntax Extension)

- Virtual DOM

- One-way data binding

- Performance

- Components

- Simplicity

---



# Question2: What do you mean by JSX?

- JSX is a XML-like syntax extension to ECMAScript (the acronym stands for JavaScript XML). Basically it just provides syntactic sugar for the React.createElement() function, giving us expressiveness of JavaScript along with HTML like template syntax. In the example below text inside
tag is returned as JavaScript function to the render function. 



    
      class App extends React.Component { 
        render() {
             return(
                  {'Welcome to React world!'} // this is a jsx
                  )
                }
            } 

JSX or JavaScript XML combines HTML and JavaScript, making the code easier to read and understandable for the user. JSX combines interactivity with markup rather than separating the two. It makes it easier to visualize DOM. In JSX we can directly write HTML tags inside JavaScript code. One of the advantages of JSX is that React creates a virtual DOM (a virtual representation of the page) to track changes and updates. Instead of rewriting the entire HTML, React modifies the DOM of the page whenever the information is updated. This is one of the main issues React was created to solve.


---

# Question3: what is virtual DOM?

The Virtual DOM (VDOM) is an in-memory representation of Real DOM. The representation of a UI is kept in memory and synced with the "real" DOM. It's a step that happens between the render function being called and the displaying of elements on the screen. This entire process is called reconciliation. (or) DOM is a document object model, created by converting HTML CSS and JS Real DOM, which is an object which gets created whenever any React application gets loaded on the screen for the first time., whenever React components gets mounted on the screen for the first time. 
- Now when any user makes any changes on the screen like button click because of which the state variable will get updated so in this case the changes will not directly go to Real DOM , instead in react we have concept known Virtual DOM. So we are having two virtual doms, one virtual dom gets created at the time of mounting of react component so it is a copy of your real dom. Another virtual dom is the dom which contains the new changes, updated state variables values. 

- Now these two virtual doms will get compared with each other and will check for the new changes. this complete procedure is known as diffing algorithm.
- Now the new changes will be updated in your Real dom. this procedure is known as Recoinciliation.

---

# Question4: What is difference between class and functional component?

## Class based Component: 

A class component requires you to extend from React. Component and create a render function which returns a React element.

It must have the render() method returning JSX (which is syntactically similar to HTML)

Also known as Stateful components because they implement logic and state.

React lifecycle methods can be used inside class components (for example componentDidMount).

It requires different syntax inside a class component to implement hooks.

Constructor are used as it needs to store state.

 ## Example:


    import React, {Component} from "react";
    
    export default class App extends Component{
        constructor(){
        super();
        this.state={
            name:"PrepBytes"
        }
    }

    render(){
        return(
            <>
            {this.state.name}
            </>
        )
    }
    }


  

## Functional Based Component: 

A functional component is just a plain JavaScript function that accepts props as an argument and returns a React element.

There is no render method used in functional components.

Also known as Stateless components as they simply accept data and display them in some form, that they are mainly responsible for rendering UI.

React lifecycle methods (for example, componentDidMount) cannot be used in functional components.

Hooks can be easily used in functional components to make them Stateful. 

Constructors are not used.

## Example:

    import React from "react";

    const App=()=>{
        return(
            <>
            
            </>

        )
    }
    export default App;

---




# Question 5: What is SPA? and What is the difference between the SPA and MPA?

SPA stands for the single page application. 

Single page application : Any web application , in which when you are clicking on any button or selecting option from navigation bar then if your page which means browser page is reloading then that means that application is your multi - page application .

 If it does not reload the browser page and just only updates the page without reloading then that application is known as Single Page application.
 
 When you create React application using CRA, (create-react-app boilerplate , developed by Facebook) it always create the application which will be Single page application.

 ## SPA v/s MPA

- In terms of speed and performance SPA no reloading is needed i.e.= to high speed & responsive.

-  In MPA which is having slow speed & performance is effective by reloading.

-   acc. to maintenance SPA is fast And easy maintaenanace but for MPA maintainance required for each page.

- SPA secures only endpoints but in MPA secures end to end.

---

# Question 6: what is package.JSON?

It contains the information about the project and also contains the libraries which the project is using and it also has the description of the commands which gets used to run test or build your project.

---


# Question 7: What does mean by state and its use in react?

The state is a built-in React object that is used to contain data or information about the component. A component’s state can change over time; whenever it changes, the component re-renders. The change in state can happen as a response to user action or system-generated events and these changes determine the behavior of the component and how it will render.  



    class User extends React.Component {
    constructor(props) {
      super(props)

      this.state = {
        message: 'Welcome to React world'
      }
    }

    render() {
      return (
        <div>
          <h1>{this.state.message}</h1>
        </div>
      )
    }
    }
  
- A state can be modified based on user action or network changes
- Every time the state of an object changes, React re-renders the component to the browser
- The state object is initialized in the constructor
- The state object can store multiple properties
this.setState() is used to change the value of the state object
- setState() function performs a shallow merge between the new and the previous state


# Props V/S states

<img src="./props.png"/>


---

# Question8: What is the Difference between react and react native? Which one is library or framework?

<img src="./pic.png"/>

---

# Question 9: What is the package name you are using for routing and Routing Implementation?

- React Router is a standard library system built on top of the React and used to create routing in the React application using React Router Package.

- React Router Dom is used to build single-page applications i.e. applications that have many pages or components but the page is never refreshed instead the content is dynamically fetched based on the URL. This process is called Routing and it is made possible with the help of React Router Dom.

Example:


    import React from 'react'
    import { BrowserRouter as Router,Routes, Route, Link } from 'react-router-dom'
    import CompA from './CompA'
    import CompB from './CompB'
    const Routing = () => {
    return (
        <div>
            <Router>

                <Link to="/" >CompA</Link>
                <Link to="/CompB" >CompB</Link>

                <Routes>
                    <Route path='/' element={<CompA />} />
                    <Route path='/CompB' element={<CompB />} />
                </Routes>

            </Router>
        </div>
    )
    }
     export default Routing

---



# Question10: How do you pass data from parent to child?

Parent Component: 


        import React, { useState } from 'react';
        import Child from "./Child"

        function Parent(){
   
        const[data, setData] = useState(" Send Data");

        const parentToChild = () =>{
         setData("this is data sending from parent to child");
         console.log("Sent successfully");
        }

         return(
            <div>
                 <h1>Data transfer from Parent to Child</h1>
                 <Child parentToChild={data}/>
                  <button onClick={() =>parentToChild()}>Click Parent</button>
            </div>
          )
        }

        export default Parent;

Child component:

    import React from 'react';

    function Child ({parentToChild}){
    return(
        <div>
          Parent to Child:{parentToChild}
        </div>
         )
     }
     export default Child;

---

# Question 11: What is lazy loading in react ?

Lazy loading is a technique in React where the component or a module is loaded and rendered only when it is actually required or requested by the user. This helps in improving the overall performance and speed of the application by loading only the necessary components and deferring the loading of others until they are needed. This results in a faster initial loading time and a better user experience.


Example: 

## App component:

    import React, { lazy, Suspense } from 'react';

    const LazyComponent = lazy(() =>import('./LazyComponent'));

    function App() {
      return (
        <div>
          <Suspense fallback={<div>Loading...</div>}>
            <LazyComponent />
          </Suspense>
        </div>
      );
    }

    export default App;


## LazyComponent:


    import React from 'react';

    const LazyComponent = () => {
    return (
    <div>
      <h1>I am a lazy-loaded component</h1>
      <p>This component was loaded only when it was needed.</p>
    </div>
    );
    };

    export default LazyComponent;


---

# Question12: Difference b/w Stateful and stateless Component?

## Stateless: 
If the behaviour is independent of its state then it can be a stateless component. You can use either a function or a class for creating stateless components. But unless we need to use a lifecycle hook in your components, we should go for function components. There are a lot of benefits if you decide to use function components here; they are easy to write, understand, and test, a little faster, and you can avoid the this keyword altogether.



      const App = (props) => {
      const [count, setCount] = useState(0);

      return (
        // JSX
      )
     }


## Stateful:

If the behaviour of a component is dependent on the state of the component then it can be termed as stateful component. These stateful components are always class components and have a state that gets initialized in the constructor. 
    
    class App extends Component { 
        constructor(props) {
             super(props)
              this.state = {
                 count: 0 
                 } 
        }
          render() {
                    <>
                   </>
    }
    }
---

# Question 13: How do you switch one component to another, Conditional Rendering?

## Link
 Link is used to manage the navigation and it worked as an anchor tag. Check below code for the demonstration. import { Link } from 'react-router-dom'; ... ...About


## NavLink
 NavLink behaves the same as Link but in addition, it comes with a new attribute called “activeClassName” which helps us to add the class to the anchor tag when page url will match.

import { NavLink } from 'react-router-dom'; ... ... About

---

# Question 14: https://jsonplaceholder.typicode.com/users  how to fetch the data from the JSON format?

     console.log(item)
     useEffect(() => {
               fetch("https://jsonplaceholder.typicode.com/comments")
              .then(response => response.json())
             .then(data => setItem(data))
     }, [])

---

# Question 15: Difference between the Fetch and Axios?

<img src="./axiosandfetch.png"/>

---

# Question 16: What is UseState Hook ?(Implementation)

State is the place where the data comes from. We should always try to make our state as simple as possible. With React 16.8, hooks are released which allow us to handle the state with less coding.

It accepts two parameters – state and setState. State is the current state, while setState is used to change the state of the functional component.

On every state change, the component re-renders with the updated state.

## Example:

    import React ,{useState} from "react";

    const App=()=>{
        const [count,setCount]=useSatate(0)
        return(
            <>
            {count}
            <button onClick={()=>{setCount(count+1)}}>
            click me
            </button>
        )
    }
    export default App;

---

# Question 17: What is UseEffect Hook?(Implementation)
 The Effect Hook allows us to perform side effects (an action) in the function components. It does not use components lifecycle methods which are available in class components. 
 
 In other words, Effects Hooks are equivalent to componentDidMount(), componentDidUpdate(), and componentWillUnmount() lifecycle methods.


Side effects have common features which the most web applications need to perform, such as:

- Updating the DOM,



- Fetching and consuming data from a server API,
- Setting up a subscription, etc.

## Example:

    import React,{useState,useEffect} from "react";

    Const App=()=>{
        const [data,setData]=useState([]);

        useEffect(()=>{
            fetch("https://jsonplaceholder.typicode.com/users)
            .then((response)=>response.json())
            .then((data)=>{setData(data)})
        },[])
        return(
            <>
            {data.map((e)=>{
                return(
                    <>
                    {console.log(e)}
                    </>

                )
            })}
            </>
        )

    }
    export default App;
---

# Question 18: What is UseReducer Hook ?(Implementation)
This hook is a better alternative of the useState hook, as it is used when we want to attach a function along with handling the state or when we want to handle the state based on the previous values.
Example:

    const [state, dispatch] = useReducer(reducer, initialArgs, init);

<b>Parameters:</b>

<b>Reducer</b> − The function to handle or update the state

<b>initialArgs</b> − Iitial state

<b>Initial</b> − To load the state lazily or when it is required

## Example

    import React ,{useReducer,useState}from "react";

    const App=()=>{
        const reducer=(state,action)=>{
            switch(action.type){
                case("Inc"):
                return(state+1);
                case("Dec"):
                return(state-1);

            }
        }
        let initial=0;
    const [state,dispatch]=useReducer(reducer,initial)
        return(
            <>
            {state}
            <button onClick={()=>{dispatch({type:"Dec"})}}>
                
            </button>
            <button onClick={()=>{dispatch({type:"Inc"})}}>
               increment
            </button>
        )

    }
    export default App;

---
# Question 19: What is UseMemo Hook ?(Implementation)

This hook is used to optimize the React application by returning a memoized value which helps to prevent doing the complex calculations on every re-rendering. This hook stores the cached value and only updates the function on certain defined conditions.

<b>Important Note :Don’t call side-effects in useMemo hooks; use useEffect hook instead. </b>


## Example
    
    import React, { useState, useMemo } from 'react'

    const UseMemo = () => {
    const [one, setOne] = useState(0)
    const [two, setTwo] = useState(0)
      function Change() {
            setOne(one + 1)

     }
        function Changetwo() {
           setTwo(two + 1)

        }

       const isEven = useMemo(() => {
         let i = 0;
         while (i < 1000000000) i++;
        return one % 2 === 0
        }, [one])

            return (
              <div>
                <button onClick={Change}>Example{one}</button>
                       <span>{isEven ? "Even" : "Odd"}</span>
                <button onClick={Changetwo}>Example{two}</button>
              </div>
            )
            }

       export default UseMemo


---

# Question 20: What is UseRef Hook ?(Implementation)

This hook is used to access any DOM element in a component and it returns a mutable ref object which will be persisted as long as the component is placed in the DOM.

If we pass a ref object to any DOM element, then the .current property to the corresponding DOM node elements will be added whenever the node changes.


## Example:

    import React ,{useRef}from 'react'

    const App = () => {

    const name=useRef(null);
    const email=useRef(null);
    const handleclick=()=>{
        const names=name.current.value;
        const emails=email.current.value;
        console.log(names,emails)
    }
     return (
    <div>

        <input type="text" ref={ name}/>
        <input type="text" ref={ email}/>
        <input type="submit" onClick={handleclick}/>

    </div>
    )
     }

    export default App;


---

# Question 21: What do you mean by useCallback Hook?

This hook is used to optimize a React application by returning a memoized function which helps to prevent unnecessary re-rendering of a function. This hook stores the cached value of the function and only updates the function if the passed dependencies changes.

## Example: 

  

---

# Question 22: what do understand by useContext Hook? (implementation)

 
