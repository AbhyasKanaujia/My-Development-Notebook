# React Class Components



* Before **React 16.8**:older\_man:, the **class component** was the **only way** :arrow\_right: to make a component
* These components **have a state**:sparkles: and a **lifecycle**:repeat:.&#x20;
* **Functional components** were considered **stateless**:mag:.
* **After** the introduction of **hooks**:hook:, **functional components** also **have** a **state**:sparkles:. There is **no difference between** a **functional** component **and** a **class** component.

## <mark style="color:blue;">Creating</mark> a Class Component

* The **name** of a component **starts** with an **upper case**
* It **inherits** the **`React.Component` ** class
* A class component **must have** a **`render()`** function that returns HTML.

To create a component called Car:

{% code title="Car.js" %}
```jsx
import React, { Component } from "react";

export class Car extends Component {
  render() {
    return <h2>Hi, I'm a Car.</h2>;
  }
}

export default Car;
```
{% endcode %}

* This component can now be **imported** and **used like** a regular **functional component**.

## Component <mark style="color:blue;">Constructor</mark>

* A **function** called **`constructor()`** in the class component is **called when** the **component is initialized**.
* This function **initializes** the **component's properties**.
* **Component properties** are **stored in** an **object** called **`state`**.
* A **call to** the **parent class's constructor** is made in this function by making the **`super()`** function call.

Adding a constructor to the car class and using the state in the render function:

```jsx
import React, { Component } from "react";

export class Car extends Component {
  constructor() {
    super();
    this.state = { color: "red" };
  }

  render() {
    return <h2>Hi, I'm a {this.state.color} Car.</h2>;
  }
}

export default Car;
```

## Props

* Arguments to the component can be sent through props.
* N**o need to capture `props`** like in functional components. It's just magically available through `this.props`

```jsx
import React, { Component } from "react";

export class Car extends Component {
  render() {
    return <h2>Hi, I'm a {this.props.color} Car.</h2>;
  }
}

export default Car;
```

### Props in Constructor

**If the value of `props`** is **used in** the **`constructor()`**, **then** it needs to be **captured** like in functional components.

* This **value also** needs to be **passed to** the **super** constructor.

```jsx
import React, { Component } from "react";

export class Car extends Component {
  constructor(props) {
    super(props);
    this.state = { color: this.props.color };
  }
  render() {
    return <h2>Hi, I'm a {this.state.color} Car.</h2>;
  }
}

export default Car;
```

## <mark style="color:blue;">Updating</mark> Component <mark style="color:blue;">State</mark>

* The state is changed by **using `this.setState()` method**
* This will **change the state** and cause the **component** to **re-render**.
* **No need** for the **spread operator like** in the **functional component**. **Just pass** the **changed state** and it works.&#x20;

```jsx
import React, { Component } from "react";

export class Car extends Component {
  constructor(props) {
    super(props);
    // the state
    this.state = { 
      color: this.props.color, 
      brand: "Lamborghini" 
    };
  }
  // function that changes state
  changeColor = () => {
    this.setState({ color: "yellow" });
  };

  render() {
    return (
      <>
        <h2>
          Hi, I'm a 
          {this.state.color} 
          {this.state.brand}.
        </h2>
        <button onClick={this.changeColor}>
          Change Color
        </button>
      </>
    );
  }
}

export default Car;
```

## Component Lifecycle

* Each component in React has a lifecycle that can be monitored and manipulated in 3 main phases.&#x20;
* There are three phases:
  * Mounting&#x20;
  * Updating
  * Unmounting

### Mounting Phase

Mounting means putting the element into the DOM.

React has four built-in methods that gets called, in this order:

1. `constructor()`
2. `getDerivedStateFromProps()`
3. `render()`
4. `componentDidMount()`

The **`render` method is required** and will **always** be **called**. **Others** are **optional** and will be **called if defined**.

#### Constructor()

* The constructor method is called before any other.
* This is a good place to initialize the component state.
* It takes a `props` argument and always states with `super(props)`.

{% tabs %}
{% tab title="React Class Component" %}
```jsx
import React, {Component} from 'react';

export class Header extends Component {
    constructor(props) {
        super(props);
        this.state = {favoriteColor: 'Red'};
    }
    
    render() {
        return (
            <h1>My Favourite Color is {this.state.favroriteColor}</h1>
        );
    }
}

export default Header;
```
{% endtab %}

{% tab title="React Functional Component" %}
```jsx
import React, {useState} from 'react';

export const Header = (props) => {
    const [favoriteColor, setFavoriteColor] = useState('Red');
    
    return <h1>My Favorite Color is {favoriteColor}</h1>
};

export default Header;
```
{% endtab %}
{% endtabs %}

