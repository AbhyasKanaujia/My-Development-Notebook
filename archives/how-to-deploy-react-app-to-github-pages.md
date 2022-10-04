# How to Deploy React App to GitHub Pages

{% embed url="https://github.com/gitname/react-gh-pages" %}

OK, so GitHub pages is a good option to host my react only app. GitHub pages is a good choice for ems as:&#x20;

* My app doesn't have a backend.&#x20;
* I need something simple.&#x20;
* I would like to use as few apps as possible.&#x20;

## Steps

1. Create a React app using `create-react-app`
2. Create GitHub Repo
3. Publish the Repo publicly
4. Install `gh-pages` as a dev dependency
5. Use `npm install gh-pages --save-dev` in the root of the React app,
6. Add a `homepage` property to the `package.json` file
   *   Add a `homepage` property in this format: `https://{username}.github.io/{repo-name`

       ```
       {
         "name": "my-app",
         "version": "0.1.0",
       + "homepage": "https://gitname.github.io/react-gh-pages",
         "private": true,
       ```
7.  Add a `predeploy` property and a `deploy` property to the `scripts` object:

    ```
    "scripts": {
    +   "predeploy": "npm run build",
    +   "deploy": "gh-pages -d build",
        "start": "react-scripts start",
        "build": "react-scripts build",
    ```
8. Push the changes
9.  Deploy using

    > ```bash
    > $ npm run deploy -- -m "Deploy React app to GitHub Pages"
    > ```
