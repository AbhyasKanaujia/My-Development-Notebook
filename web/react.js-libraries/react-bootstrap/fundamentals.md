# Fundamentals



## Installation

In the frontend folder

```bash
npm install react-bootstrap bootstrap
```

In `index.js`

```jsx
import 'bootstrap/dist/css/bootstrap.min.css';
```

## Breakpoints

Bootstrap includes six default breakpoints.

| Breakpoint        | Class infix | Dimensions |
| ----------------- | ----------- | ---------- |
| X-Small           | _None_      | <576px     |
| Small             | `sm`        | ≥576px     |
| Medium            | `md`        | ≥768px     |
| Large             | `lg`        | ≥992px     |
| Extra large       | `xl`        | ≥1200px    |
| Extra extra large | `xxl`       | ≥1400px    |

## Grid

Bootstrap’s grid system uses a series of **containers**, **rows**, and **columns** to layout and align content. It’s built with [flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS\_Flexible\_Box\_Layout/Using\_CSS\_flexible\_boxes) and is fully responsive.

### Container

Container centre and horizontally pad the site's content. It makes the width of the content responsive.&#x20;

```jsx
<Container>
    <Row>
        <Col>
            <Children/>
        </Col>
    </Row>
</Container>
```

#### Fluid Container

Fluid Container makes the container have a width of 100% across all screen sizes.&#x20;

```jsx
<Container fluid>
    <Row>
        <Col>
            <Children/>
        </Col>
    </Row>
</Container>
```

#### Breakpoints

Adding a breakpoint for fluid makes the container fluid until that breakpoint. Larger than that breakpoint and the container will be sized responsively.&#x20;

{% code overflow="wrap" %}
```jsx
<Container  fluid='md'>
    <Row>
        <Col>
            {/*This component will be fluid until `md` and then it will be responsive.*/}
            <Children/>
        </Col>
    </Row>
</Container>
```
{% endcode %}

### Columns

One row can have many columns. If the width of the row is not specified then each will take an equal amount of width.&#x20;

```jsx
const Container = ReactBootstrap.Container;
const Row = ReactBootstrap.Row;
const Col = ReactBootstrap.Col;
const element = <Container fluid='sm'>
  <Row>
    <Col>
      Hello Bootstrap
    </Col>  
    <Col>
      Hello Bootstrap
    </Col>  
    <Col>
      Hello Bootstrap
    </Col>  
    <Col>
      Hello Bootstrap
    </Col>  
    <Col>
      Hello Bootstrap
    </Col>  
    <Col>
      Hello Bootstrap
    </Col>  
    <Col>
      Hello Bootstrap
    </Col>  
    
  </Row>
</Container>;

ReactDOM.render(element, document.getElementById("app"));
```

<figure><img src="../../../.gitbook/assets/image (12).png" alt=""><figcaption></figcaption></figure>

#### Specifying size

A bootstrap grid has a full width of 12. We can specify the width of a column using any breakpoint specificaion. Eg. `md = 8` which means that the column will be fluid until it hits `md`, after which, it will take 8/12 of the width.&#x20;

```jsx
const Container = ReactBootstrap.Container;
const Row = ReactBootstrap.Row;
const Col = ReactBootstrap.Col;
const element = <Container fluid='sm'>
  <Row>
    <Col>
      Auto Sized
    </Col>  
    <Col xs='8'>
      xs = 8 here
    </Col>  
    <Col>
      Auto Sized
    </Col>  
    
  </Row>
</Container>;

ReactDOM.render(element, document.getElementById("app"));
```

<figure><img src="../../../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

It also sets the upper bound on how wide a column can be

```jsx
const Container = ReactBootstrap.Container;
const Row = ReactBootstrap.Row;
const Col = ReactBootstrap.Col;
const element = <Container fluid='sm'>
  <Row>
    <Col xs='8'>
      xs = 8 here
    </Col> 
  </Row>
</Container>;

ReactDOM.render(element, document.getElementById("app"));
```

<figure><img src="../../../.gitbook/assets/image (15).png" alt=""><figcaption></figcaption></figure>

### Variable Width Content

```jsx
const Container = ReactBootstrap.Container;
const Row = ReactBootstrap.Row;
const Col = ReactBootstrap.Col;
const element = <Container fluid='sm'>
  <Row>
    {/* First Row */}
    <Col xs='auto'>
      xs = auto here. If the content is too large then it automatically takes the full width. If content is too large then it automatically takes the full width. 
    </Col>  
    <Col xs='auto'>
      xs = auto here. If it is too small then it takes as much as needed.
    </Col>  
    <Col>
      Unspecified. Takes the maximum possible. 
    </Col>      
  </Row>
        
        
        {/* First Row */}
  <Row>
    <Col>
      Unspecified. Even though the content is too large, the width is still the same. Even though the  content is too large, the width is still the same. 
    </Col>  
    <Col>
      Unspecified. Works like fluid
    </Col>  
    <Col>
      Unspecified
    </Col>      
  </Row>
  <Row>
    <Col xs='auto'>
      xs = auto here
    </Col>  
    <Col xs='auto'>
      xs = auto here
    </Col>  
    <Col xs='auto'>
      xs = auto here. only as much as needed. 
    </Col>      
  </Row>
  
</Container>;

ReactDOM.render(element, document.getElementById("app"));
```

<figure><img src="../../../.gitbook/assets/image (1) (2).png" alt=""><figcaption></figcaption></figure>



### Responsive Grid

We can specify the width of a `Col` for multiple breakpoints.&#x20;

```jsx
<Col sm={3} md={4} lg={8}>
    sm=3 md=4 lg=8
</Col>
```

### span, order, offset&#x20;

We can specify the column size, order and position more precisely by passing an object as props to the breakpoint.&#x20;

#### Order

Order can be anything from 0 to 12. By default, all elements have the order of 0. If two elements have the same order then the one that appears first is placed leftmost.&#x20;

Order can also be set as `first` (for -1) and `last` (for columns + 1)

```jsx
<Container fluid='sm'>
  <Row>
    <Col xs={{ order: 4 }}>Col1</Col>
    <Col xs={{ order: 0 }}>Col2: 0 means first</Col>
    <Col>Col3</Col>      
  </Row>  
</Container>;
```

<figure><img src="../../../.gitbook/assets/image (10).png" alt=""><figcaption></figcaption></figure>

#### Offset

Move a column to a particular grid position. Alternatively, use margin utilities.&#x20;

```jsx
<Container fluid='sm'>
  <Row>
    <Col>Col1</Col>
    <Col xs={{ offset: 5 }}>Col 2</Col>  
  </Row>  
</Container>;
```

<figure><img src="../../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

### Rows

#### Setting Number of columns in each row

```jsx
  <Row xs={2} md={4} lg={6}>
    <Col>Col 1</Col>
    <Col>Col 2</Col>  
    <Col>Col 3</Col>
    <Col>Col 4</Col>  
    <Col>Col 5</Col>
    <Col>Col 6</Col>  
  </Row>  
```

<figure><img src="../../../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

## Stacks

* Stacks are verticle by default
* Stacks take full width by default
* To add a gap between stack items, use `gap={x}`

```jsx
<Stack gap={3}>
  <div>First item</div>
  <div>Second item</div>
  <div>Third item</div>
</Stack>
```

![](<../../../.gitbook/assets/image (9).png>)

Stacks can be horizontal

```jsx
<Stack direction="horizontal" gap={3}>
  <div>First item</div>
  <div>Second item</div>
  <div>Third item</div>
</Stack>
```

<figure><img src="../../../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

Use horizontal margin utitlities like `ms-auto` for spacing them out.&#x20;

Example Usage:

```jsx
<Stack gap={2} className="col-md-5 mx-auto">
  <Button variant="secondary">Save changes</Button>
  <Button variant="outline-secondary">Cancel</Button>
</Stack>
```

<figure><img src="../../../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

Create an inline form with horizontal stacking:

```jsx
<Stack direction="horizontal" gap={3}>
  <Form.Control className="me-auto" placeholder="Add your item here..." />
  <Button variant="secondary">Submit</Button>
  <div className="vr" />
  <Button variant="outline-danger">Reset</Button>
</Stack>
```

<figure><img src="../../../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>
