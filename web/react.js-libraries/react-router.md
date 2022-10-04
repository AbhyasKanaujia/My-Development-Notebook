# React Router

React router is a fully featured **client**:mobile\_phone: **** and **service-side**:cloud: **routing library** for React.&#x20;

* It helps to **create** and **navigate different URLs**:globe\_with\_meridians: **** that make up the application.&#x20;
* I also provide unique URLs for different component in the app and makes the UI easily shareable with other users.&#x20;

## Installing React Router

In an existing react app :atom:, **install react-router** :arrow\_down: **** using **`npm i react-router-dom@6`**. This will specifically **install version 6** :point\_left: of the react-router-dom.

## Configuring Routes

Let's assume a **scenario** where when a **user visits** the **home route `/`**, then the user will **see** the **Home page** component and **when** they **visit `/about`** then the user will **see** the **About page**.&#x20;

### Connect Browser's URL to React app

The first step is to **connect** the **browser's URL** to the **react app**. This is **done by** using the **`BrowserRouter` component** provided by `react-router-dom`. We **wrap the entire app** **with this** component.&#x20;

* The **`index.js`** **uses** the **App** component and the **App** component **contains** the actual **app**.&#x20;
* In `index.js` import `BrowserRouter` from `react-router-dom`.&#x20;

```jsx
import {BrowserRouter} from 'react-router-dom';
```

* Now wrap the `App` component with BrowserRouter

{% code title="index.js" %}
```jsx
import ReactDOM from "react-dom/client";
import App from "./App";
import { BrowserRouter } from "react-router-dom"; // import this 
import React from "react";

ReactDOM.render(
  <React.StrictMode>
    <BrowserRouter> // wrapping app with BrowserRouter
      <App />
    </BrowserRouter>
  </React.StrictMode>,
  document.getElementById("root")
);
```
{% endcode %}

