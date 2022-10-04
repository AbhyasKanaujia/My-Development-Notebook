# Creating a basic express server

### Backend files and folders

First, create a folder for the project `mkdir myapp.` This is the root of the project. This is where we install all the backend dependencies inside a folder called `node_modules`.

```bash
mkdir myapp
```

Create a folder called `backend` inside `myapp`. This is where all the routes, models and controllers for the API live.

```bash
cd myapp
mkdir backend
```

Create a file called `server.js` in `backend.` This is the entry point to the server.

Initialize the project at the root of the project by using `npm init`. Set `server.js` as the entry point. This will create a `package.json` in the root.&#x20;

```bash
cd .. # to reach the root of the project
npm init
```

Create a `.gitignore` file in the root of the project with the following content

{% code title=".gitignore" %}
```
node_modules
.env
```
{% endcode %}

This will save us from uploading the node\_modules and settings file to GitHub.

Install the dependencies into the root of the project.

### Install dependencies and add scripts

```bash
npm i express dotenv mongoose colors
```

To save us from constantly restarting the server we can install a dependency called `nodemon` as a&#x20;

development dependency.

```bash
npm i -D nodemon
```

Add scripts to start and to run the server in `package.json`

```json
...
"scripts" : {
    "start": "node backend/server.js",
    "server": "nodemon backend/server.js"
},
...
```

### Git

In the root of the folder initialize a git repository and make an initial commit.

```bash
git init
git add .
git commit -m 'Initial commit'
```

### Basic server setup

Create a file called `.env` in the `root` of the project with the following content

```toml
NODE_ENV = development
PORT = 5000
```

Any change you make to the `.env` file requires a restart of the server.

In `server.js` create a basic server and listen for requests.

{% code overflow="wrap" %}
```javascript
const express = require('express');

cons dotenv = required('dotenv').config();

const PORT = process.env.PORT || 5000;

const app = express();

app.listen(PORT, console.log(`Server started on port ${PORT} in ${process.env.NODE_ENV} mode`));
```
{% endcode %}
