# React.js

## Component <a href="#_encztzq463i2" id="_encztzq463i2"></a>

Component is a function which returns **an element** (HTML)

```jsx
const Greet = ({name,age}) => {
    return <h1>{name} {age}</h1>;
};

export default Greet;
```

* Components are **imported before using**
* We can have **components inside other components**
* **rafce** (VScode Snippet) for direct making component

## Props <a href="#_9v04l8pim3om" id="_9v04l8pim3om"></a>

Props are **values** that are **passed** to **component**

* Syntax is same as HTML **attributes**
* Props are received by props object
  * We can **destructure** this using curly braces
* Props can be accessed using **dot syntax** eg. props.name

## Events <a href="#_a8w60xmswzry" id="_a8w60xmswzry"></a>

* We can perform **action based** on **user event.**
* There can be various **events like click, swipe**,(search event html)
* To add event we **pass function as parameter**

```jsx
const SayHello = () => {
    const buttonClickHandle = () => {
        alert('You have clicked the button')
    };
    
    return (
        <div>
            <button onClick={buttonClickHandle}>Say Hello</button>
        </div>
    );
};
```

## Template Literals <a href="#_ik88ahr8cxko" id="_ik88ahr8cxko"></a>

Template literals help us to **put the value** of **variable inside** a **string**

```jsx
const res = 2 + 99;
alert(`Result is ${res} `);
```

## Conditional Rendering <a href="#_e2s6p2cdxbkh" id="_e2s6p2cdxbkh"></a>

Componenets can be rendered based on some conditions. Example use cases can be user login, out of stock etc.&#x20;

### Using <mark style="color:blue;">traditional</mark> JS if statement

```javascript
const Stock = ({count}) => {

    const InStock = ({ count }) => {
        return <h3 style={{ color: "green" }}>{count} remaining in stock</h3>;
    };
    
    const OutOfStock = () => {
        return <h3 style={{ color: "red" }}>Out of Stock</h3>;
    };
    
    if (count > 0) 
        return <InStock count={count} />;
    else 
        return <OutOfStock />;
};
```

### Using <mark style="color:blue;">ternary operator</mark>

```javascript
const Stock = ({ count }) => {
    return <h3>{count > 0 ? `${count} remaining in stock` : "Out of stock"}</h3>;
};
```

### Using <mark style="color:blue;">**short circuit**</mark>** evaluation**

```javascript
{inStock > 0 && <button> BuyNow </button> }
```

## <mark style="color:blue;">Rendering</mark> Components using a <mark style="color:blue;">list</mark> <a href="#_kn559m5bttt" id="_kn559m5bttt"></a>

We can use JavaScript `map` to render a list

{% code title="App.js" %}
```javascript
const App = () => {
    // comes from database
    const list = ["Buy", "cook", "Eat", "Sleep"];
    
    return (
        <div>
            <ToDoList list={list} />
        </div>
    );
};
```
{% endcode %}

{% code title="ToDoList.js" %}
```javascript
const ToDoList = ({ list }) => {
    return (
        <div>
            <h1>ToDoList</h1>
            
            <ul>
                {list.map((item) => {
                return <li>{item}</li>;
                })}
            </ul>
        </div>
    );
};
```
{% endcode %}

#### Adding <mark style="color:blue;">Key prop</mark> to each rendered item

Previous example will not work as predicted since **each item cannot be identified**. To **solve this** problem we need to **pass a prop** called a **key**.

{% code title="App.js" %}
```jsx
const App = () => {
    // comes from database
    const list = [
    { key: 1, taskName: "Buy" },
    { key: 2, taskName: "Cook" },
    { key: 3, taskName: "Eat" },
    ];
    
    return (
        <div>
            <ToDoList list={list} />
        </div>
    );
};
```
{% endcode %}

{% code title="ToDoList.js" %}
```jsx
const ToDoList = ({ list }) => {
    return (
        <div>
            <h1>ToDoList</h1>
            <ul>
                {list.map((item) => {
                return <li key={item.key}>{item.taskName}</li>;
                })}
            </ul>
        </div>
    );
};
```
{% endcode %}

## Form handling <a href="#_aidri4d9v3gm" id="_aidri4d9v3gm"></a>

1. First **create** the **form element** then **input element** then **submit button**
2. **Create** a **state** by which we can **save the input value**
3. **Handle input value changing**
4. **Handle form submission**
5. **Capture the form through event**
6. **Stop default function**
7. **Use** the **form value** from **state**.

<pre class="language-jsx"><code class="lang-jsx">const FormComponent = () => {
<strong>    // state
</strong>    const [name, setName] = useState("");
    const [submittedName, setSubmittedName] = useState("");
    
    // handler
    const handleSubmit = (e) => {
        e.preventDefault();
        setSubmittedName(name);
    };
    
    // return component
    return (
        &#x3C;Container>
            &#x3C;form onSubmit={(e) => handleSubmit(e)}>
                &#x3C;label htmlFor="name">Enter your name&#x3C;/label>
                &#x3C;br />
                
                &#x3C;input
                    type="text"
                    name="name"
                    id="name"
                    value={name}
                    onChange={(e) => setName(e.target.value)}
                />
                &#x3C;br />
                
                &#x3C;button type="submit">Submit&#x3C;/button>
            &#x3C;/form>
            
            {submittedName !== "" &#x26;&#x26; &#x3C;h1>Welcome, {submittedName}&#x3C;/h1>}
        &#x3C;/Container>
    );
};</code></pre>

### Calculator App Example <a href="#_jxqost37hha8" id="_jxqost37hha8"></a>

A simple app that adds two numbers. Uses the following concepts:

* State
* Form
* Event handling
* Bootstrap Forms

```jsx
import React, { useState } from "react";
import Container from "react-bootstrap/Container";
import Form from "react-bootstrap/Form";
import Button from "react-bootstrap/Button";
import Alert from "react-bootstrap/Alert";

const Calculator = () => {
    const [num1, setNum1] = useState(0);
    const [num2, setNum2] = useState(0);
    const [sum, setSum] = useState("");
    
    const handleSubmit = (e) => {
        e.preventDefault();
        setSum(parseInt(num1) + parseInt(num2));
    };
    
    return (
        <Container>
            <h1 className="my-4">Addition Calculator</h1>
            
            <Form onSubmit={(e) => handleSubmit(e)}>
                <Form.Group>
                    <Form.Label>Number 1</Form.Label>
                    <Form.Control
                    type="number"
                    value={num1}
                    onChange={(e) => setNum1(e.target.value)}
                    />
                </Form.Group>
                
                <Form.Group>
                    <Form.Label>Number 2</Form.Label>
                    <Form.Control
                    type="number"
                    value={num2}
                    onChange={(e) => setNum2(e.target.value)}
                    />
                </Form.Group>
                
                <Button className="my-3" type="submit">
                Add
                </Button>
            </Form>
            {sum !== "" && <Alert>The sum is {sum}</Alert>}
        </Container>
    );
};
export default Calculator;
```

#### Output

![](<../../.gitbook/assets/image (4).png>)

### Multiple input values using single state

<pre class="language-jsx"><code class="lang-jsx"><strong>const FacebookSignup = () => {
</strong>    const [userInfo, setUserInfo] = useState({
    firstName: "",
    surname: "",
    phone: "",
    password: "",
    });
    
    return (
        &#x3C;Container className="m-3 mx-auto">
            &#x3C;h1 className="text-primary">facebook&#x3C;/h1>
            
            &#x3C;Card className="p-3">
                &#x3C;h2>Create a new account&#x3C;/h2>
                
                &#x3C;p>It's quick and easy&#x3C;/p>
                
                &#x3C;hr />
                &#x3C;Form>
                    &#x3C;Row>
                        &#x3C;Col>
                            &#x3C;Form.Group>
                                &#x3C;Form.Control
                                type="text"
                                placeholder="First name"
                                value={userInfo.firstName}
                                onChange={(e) =>
                                setUserInfo((prev) => ({
                                ...prev,
                                firstName: e.target.value,
                                }))
                                }
                                />
                                &#x3C;/Form.Group>
                        &#x3C;/Col>
                        &#x3C;Col>
                            &#x3C;Form.Group>
                                &#x3C;Form.Control
                                type="text"
                                placeholder="Surname"
                                value={userInfo.surname}
                                onChange={(e) =>
                                setUserInfo((prev) => ({
                                ...prev,
                                surname: e.target.value,
                                }))
                                }
                                />
                            &#x3C;/Form.Group>
                        &#x3C;/Col>
                    &#x3C;/Row>
                &#x3C;/Form>
            &#x3C;/Card>
        &#x3C;/Container>
<strong>    )
</strong><strong>};</strong></code></pre>

### Multiple form input <a href="#_ivp9lq8etapa" id="_ivp9lq8etapa"></a>

* We can store **multiple value** in **single state** by creating an **object**
* We should create a **separate function** to **handle** on **change**
* Each **input control** will have a **name attribute**
* **On** **change function** will **use `e.target.value`** and **`e.target.name`**
* `e.target.name` used to `[ propertyName ]` bracket for evaluation

```jsx
import React, { useState } from "react";
import Container from "react-bootstrap/Container";
import { Card, Form, Row, Col, Button } from "react-bootstrap";

const FacebookSignup = () => {
    const [userInfo, setUserInfo] = useState({
        firstName: "",
        surname: "",
        phone: "",
        password: "",
    });    
    const handleChange = (e) => {
        setUserInfo((prev) => ({
        ...prev,
        [e.target.name]: e.target.value,
        }));
    };
    //JSX {value evaluate}
    //JS [propertyName]
    const handleSubmit = (e) => {
        e.preventDefault();
        
        if (userInfo.password.length < 8) alert("You password is too short");
        else if (userInfo.phone.length < 10) {
            alert("Invalid phone number");
        } else {
            alert(`Welcome to facebook ${userInfo.firstName} ${userInfo.surname}`);
        }
    };
    return (
        <Container className="m-3 mx-auto">
            <h1 className="text-primary">facebook</h1>
            
            <Card className="p-3">
                <h2>Create a new account</h2>
                <p>It's quick and easy</p>
                <hr />
                <Form onSubmit={(e) => handleSubmit(e)}>
                    <Row>
                        <Col>
                            <Form.Group>
                                <Form.Control
                                type="text"
                                placeholder="First name"
                                name="firstName"
                                value={userInfo.firstName}
                                onChange={(e) => handleChange(e)}
                                />
                            </Form.Group>
                        </Col>
                        <Col>
                            <Form.Group>
                                <Form.Control
                                type="text"
                                placeholder="Surname"
                                name="surname"
                                value={userInfo.surname}
                                onChange={(e) => handleChange(e)}
                                />
                            </Form.Group>
                        </Col>
                    </Row>
                    <Form.Group className="my-2">
                        <Form.Control
                        type="tel"
                        placeholder="Mobile number"
                        name="phone"
                        value={userInfo.phone}
                        onChange={(e) => handleChange(e)}
                        />
                    </Form.Group>
                    <Form.Group className="my-2">
                        <Form.Control
                        type="password"
                        placeholder="New Password"
                        name="password"
                        value={userInfo.password}
                        onChange={(e) => handleChange(e)}
                        />
                    </Form.Group>
                    
                    <Button type="submit" className="w-100" variant="success">
                    Sign up
                    </Button>
                </Form>
            </Card>
        </Container>
    );
};
export default FacebookSignup;
```

### Handling text area <a href="#_79qxg5x1ux4f" id="_79qxg5x1ux4f"></a>

```jsx
<Form.Control
    as="textarea"
    rows={3}
    placeholder="About me"
    name="about"
    value={userInfo.about}
    onChange={(e) => handleChange(e)}
/>
```
