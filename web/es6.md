# ES6

## Classes <a href="#_i5lzn9ewzbx" id="_i5lzn9ewzbx"></a>

```javascript
class Car {
    constructor(name) {
        this.brand = name;
    }
}
```

* Class **names** starts with an **Uppercase**
* **Constructor** function is **automatically called by** the **new** keyword

### Creating Object of Class Car <a href="#_5yw9vzqv3asb" id="_5yw9vzqv3asb"></a>

```javascript
const myCar = new Car("Mahindra");
```

### Creating and using methods in classes <a href="#_vlv6kokttdeo" id="_vlv6kokttdeo"></a>

```javascript
class Car {
    constructor(name) {
        this.brand = name;
    }
    present() {
        return "I have a " + this.brand;
    }
}

cost myCar = new Car("Mahindra");
myCar.present();
```

### Inheritance <a href="#_c2srw0e22opr" id="_c2srw0e22opr"></a>

* Use the **extends** keyword

```javascript
class Car {
    constructor(name) {
            this.brand = name;
    }
    
    present() {
        return "I have a " + this.brand;
    }    
}

class Model extends Car {
    constructor(name, mod) {
        super(name);
        this.model = mod;
    }
    
    show() {
        return this.present() + ", it is a " + this.model;
    }
}

const myCar = new Model("Ford", "Mustang");
myCar.show();
```

* **super()** refers to the parent class

## Arrow Function <a href="#_lxfzos88df0f" id="_lxfzos88df0f"></a>

Arrow functions are used to write **shorter function syntax**

**Normal Function:**

```javascript
hello = function() {
    return "Hello World";
}
```

**Arrow Function:**

```javascript
hello = () => {
    return "Hello World";
}
```

Since the function has **only one statement,** and the statement is a **return statement,** we can **remove** both the **braces** and the **return keyword.**

```javascript
hello = () => "Hello World";
```

Thus, **arrow** function **return** value **by default.** This works **only when** the function has **a single return statement.**

### Arrow Function with parameters <a href="#_vo2zud1juuop" id="_vo2zud1juuop"></a>

```javascript
hello = (name) => "Hello " + name;
```

Since there is only one parameter, we can omit it

```javascript
hello = name => "Hello " + name;
```

### The 'this' keyword <mark style="color:red;">works differently</mark>! <a href="#_9s5atvd79cky" id="_9s5atvd79cky"></a>

In **normal function**, **this** keyword **represents** the **object that called** the **function**. In an **arrow function**, **this** keyword **represents** the **object that defined** the **function**.

## Variables <a href="#_hh36jd859e4r" id="_hh36jd859e4r"></a>

Variables can be defined using the <mark style="color:purple;">**var**</mark>**, **<mark style="color:purple;">**let**</mark> and <mark style="color:purple;">**const**</mark> keyword.

* **var** is function scoped
* **const** is block sloped
* **const does not mean constant.**
  * **const cannot reassign** value, array or object
  * **const can** change elements of const array or property of const object.

## Array Method <a href="#_2ettnd72qk8y" id="_2ettnd72qk8y"></a>

### Map <a href="#_ooomgzkwkbz2" id="_ooomgzkwkbz2"></a>

Map is an array function that **runs a function** **on** **each array element** and **returns a new array** as a result.

```javascript
const fruits = ["Apple", "Mango", "Watermelon"];
const list = fruits.map( fruit => <p>{fruit}</p>);
```

## Destructuring <a href="#_fm0jqm1afsox" id="_fm0jqm1afsox"></a>

To **make** a **sandwich** we **only take what** we **need** from a **refrigerator**. **Not all** the items inside the refrigerator. **This is how destructuring helps**.

**From** an **array** or **object**, we **only need some** of the **items** contained in these. **Destructuring** makes it **easier** to **extract only what** is **needed**.

### Destructuring an <mark style="color:blue;">array</mark> <a href="#_9ayg3od6afk8" id="_9ayg3od6afk8"></a>

Given an array:

```javascript
const vehicles = ["Mustang", "F-150" ,"Expedition"];
```

#### Making 3 variables <mark style="color:red;">**without destructuring**</mark>:

```javascript
const car = vehicles[0];
const truck = vehicles[1];
const suv = vehicles[2];
```

Making 3 variables <mark style="color:green;">**with destructuring**</mark>:

```javascript
const [car, truck, suv] = vehicles;
```

Here order is important.&#x20;

We can also <mark style="color:blue;">**skip intermediate elements**</mark>**:**

```javascript
const [car, , suv] = vehicles;
```

### Destructuring an <mark style="color:blue;">object</mark> <a href="#_5u242cxk4rbo" id="_5u242cxk4rbo"></a>

Given an object:

```javascript
const vehilcleOne = {
    brand: "Ford",
    modle: "Mustang",
    type: "car",
    year: 2022,
    color: "red"
};
```

#### Using <mark style="color:red;">old dot notation</mark>:

```javascript
function myVehicle(vehicle) {
    console.log(`My ${vehicle.type} is a ${vehicle.color} ${vehicle.brand} ${vehicle.model}`);
}
```

#### Using <mark style="color:green;">object destructuring</mark>:

```javascript
function myVechile({brand, model, type, color}) {
    console.log(`My ${type} is a ${color} ${brand} ${model}`);
}
```

* Notice **that we did not need** year so **we did not get** year
* **Order** of destructuring object **doesn't matter**.

#### Destructuring <mark style="color:blue;">nested objects</mark> <a href="#_9jhcl89donyt" id="_9jhcl89donyt"></a>

Given a nested object:

```javascript
class vehicleOne = {
    brand: "Ford",
    modle: "Mustang",
    type: "car",
    year: 2022,
    color: "red"
    registration: {
        city: "Kanpur",
        state: "Uttar Pradesh",
        country: "India"
    }
};
```

Getting model, and state from registration

```javascript
const {model, registration: {state}} = vehicleOne;
```

## Spread Operator <a href="#_6liy5jcz8d4k" id="_6liy5jcz8d4k"></a>

* **`...`** is used as spread operator along **with** an **array** or an **object**
* Spread operator is **used to copy** all or part of **some array** or **object into some other** array or object

### <mark style="color:blue;">Combining</mark> two <mark style="color:blue;">arrays</mark> into one using spread operator <a href="#_2af7vok8xdj" id="_2af7vok8xdj"></a>

```javascript
const numberOne = [1, 2, 3];
const numberTwo = [4, 5, 6];
const numberCombined = [...numberOne, ...numberTwo];
// numberCombined = [1, 2, 3, 4, 5, 6]
```

### <mark style="color:blue;">Append</mark> one <mark style="color:blue;">array at the end</mark> of another array <a href="#_p61z2333nvwd" id="_p61z2333nvwd"></a>

```javascript
const numberOne = [3, 4, 5];
const numbers = [1, 2, ...numberOne]; // numbers = [1, 2, 3, 4, 5]
```

### <mark style="color:blue;">Rest Operator</mark> <a href="#_4s4o83vb9le6" id="_4s4o83vb9le6"></a>

```javascript
const numbers = [1, 2, 3, 4, 5];
const [one, two, ...rest] = numbers; // one = 1, two = 2, rest = [3, 4, 5]
```

### <mark style="color:blue;">Combining</mark> two <mark style="color:blue;">objects</mark> into one using spread operator <a href="#_ng00wih30uia" id="_ng00wih30uia"></a>

```javascript
const myVehicle = {
    brand: "Ford",
    model: "Mustang",
    color: "red"
};

const updateMyVehicle {
    type: "car",
    year: 2022,
    color: "yellow"
};

const myUpdatedVehicle = {...myVehicle, ...updateMyVehicle};

/*
myUpdatedVehicle = {
brand: "Ford",
model: "Mustang",
type: "car",
year: 2022,
color: "yellow"
}
*/
```

* Notice that the **last object's info** about **color**(<mark style="color:yellow;">**yellow**</mark>) overrides the **previous object info about color**(<mark style="color:red;">**red**</mark>)

## Modules <a href="#_3ozz0d7d9tfp" id="_3ozz0d7d9tfp"></a>

Modules are **used to separate** JS **code into** separate **files**. It makes <mark style="color:green;">**maintenance**</mark> of code easier

Modules are managed by using `import` and `export` statements.

### Export <a href="#_caf5tepiuasp" id="_caf5tepiuasp"></a>

There are two types of exports:

1. Named Export
2. Default Export

#### Named Export

Named export can be inline

{% code title="Person.js" %}
```jsx
export const name = "Kavya";
export const age = 23;
```
{% endcode %}

Named Export can be at the bottom of the flie

{% code title="Person.js" %}
```jsx
const name = "Kavya";
const age = 23

export {name, age};
```
{% endcode %}

#### Default Export

There can only be one default export

```jsx
const message = {
    const name = "Kavya";
    const age = 23;
    return `${name} is ${age}.`;
};

export default message
```

### Import

Importing can be done based on how modules were exported.&#x20;

1. Importing named modules
2. Importing default modules

#### Importing named exports

These imports can be destructured using curly braces.&#x20;

```jsx
import {name, age} from './Person.js';
```

#### Importing default exports

```jsx
import message from './Person.js';
```

