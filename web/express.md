# Express



Express.js is a **back-end web application framework** for building **RESTful APIs** with **Node.js**.

* Express can be **used to serve static files** using `app.use(express.static("public"));`
* The most important concept in react is **Routing.**
* Express uses **Middleware** to **provide** more **functionalities**.&#x20;

## Routing

Express **takes a client request**, **matches** it against any **routes** that are present, and **executes the handler function** that is associated with that route. This is Routing.&#x20;

A route specification consists of:&#x20;

1. An **HTTP method** (GET, POST, etc.)
2. A **path specification** that matches the request URI
3. The **route handler**

### Request matching

The requests are matched in the order in which they are specified. So the more specific routes must appear before more general routes.&#x20;

`/*` Appears at the very end.&#x20;

### Handler Function

The handler function is expected to generate the appropriate response.

* The handler is passed in a **request object** and a **response object**.
* The request **object** can be **inspected** to get the various **details of the request**.
* The response object’s **methods** can be **used to send** the **response** to the client.

#### Middleware vs Route

A middleware function deals with _any_ request matching the path specification, regardless of the HTTP method.

A route can match a request with a specific HTTP method. So, instead of `app.use()`, `app.get()` has to be used in order to match the GET HTTP method.

### Parameters to a handler function

A handler function is provided with two parameters, the request object and the response object.&#x20;

#### Request Object



### Route Parameters

**Route parameters** are **named URL segments** that are used to **capture** the **values** specified **at their position in** the **URL**.

It has the following form:&#x20;

```javascript
app.get('/products/:productId', getSingleProductById);
```

This will match `app.com/products/123`
