# RestAPI

<figure><img src="../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

## Creating a basic API&#x20;

This example builds an API for Goals

First [set up a basic express server](https://abhyas-kanaujia.gitbook.io/core/web/express#backend-files-and-folders) and start the server using nodemon.&#x20;

Launch Postman to test and document the API.&#x20;

In the `backend` folder create a folder called `routes`

Create a file called `goalRoutes.js`. Each resource in the API will have a `Routes` file.&#x20;

Create an express router in `goalRoutes.js` and export it as a default. Add a get method to get goals. Set the status and send a dummy message for now.&#x20;

{% code title="goalRoutes.js" %}
```javascript
const express = require('express');
const router = express.Router();

router.get('/', (req, res) => {
    res.status(200).json({message: 'Get goals'});
});

module.exports = router;
```
{% endcode %}

Modify `App.js` to use this router. After creating `app`, make `app` use this router.

{% code title="App.js" %}
```javascript
...
const app = express();
// all requests to /api/goals to be handed by this router
app.use('/api/goals', require('./routes/goalRoutes'));
...
```
{% endcode %}

Duplicate the `get` route in `goalRoutes.js` 3 more times to create more routes for `post`, `put` and `delete` methods. Notice how `put` and `delete` methods take and utilize an `id`.

{% code title="goalRoutes.js" %}
```javascript
const express = require("express");
const router = express.Router();

router.get("/", (req, res) => {
  res.status(200).json({ message: "Get goals" });
});

router.post("/", (req, res) => {
  res.status(200).json({ message: "Set goal" });
});

router.put("/:id", (req, res) => {
  res.status(200).json({ message: `Update goal ${req.params.id}` });
});

router.delete("/:id", (req, res) => {
  res.status(200).json({ message: `Delete goal ${req.params.id}` });
});

module.exports = router;
```
{% endcode %}

At this point, the API doesn't actually return or perform anything useful but the routes are in place. It's completely fine to replace these messages with the actual functionality, but it is better to **create a separate file called** `controller`**.**

Create a folder called `controllers` in the `backend` folder. Create a file called `goalControllers.js` inside `controllers`. Each resource in the API will have a `Controllers` file.&#x20;

Add the functionalities in the `goalControllers.js` file. Add annotations about the controller.&#x20;

{% code title="goalControllers.js" %}
```javascript
// @ desc   Get goals
// @ route  GET /api/goals
// @ access Private
const getGoals = (req, res) => {
  res.status(200).json({ message: "Get goals" });
};

module.exports = {
  getGoals,
};

const getGoals = (req, res) => {
  res.status(200).json({ message: "Get goals" });
};

module.exports = {
  getGoals,
};
```
{% endcode %}

Bring this controller for `get` request from `goalControllers.js` into the `goalRoutes.js`. Replace the handler function.&#x20;

{% code title="goalRoutes.js" %}
```javascript
const { getGoals } = require("../controllers/goalControllers");

router.get("/", getGoals);
```
{% endcode %}

Duplicate the `getGoals` controller 3 more times to create more controllers for creating, updating and deleting goals.&#x20;

