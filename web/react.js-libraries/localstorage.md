# Using LocalStorage

For this particular project, I need to use localStorage, but I don't know how to use it. So I'll just see some tutorials. There's [an article from freecodecamp](https://www.freecodecamp.org/news/how-to-use-localstorage-with-react-hooks-to-set-and-get-items/), I'll follow this. I'll also see [the documentation on the Mozilla's site](https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage) to get an in-depth, formal and accurate information.&#x20;

## Definition

> The **`localStorage`** read-only property of the [`window`](https://developer.mozilla.org/en-US/docs/Web/API/Window) interface allows you to access a [`Storage`](https://developer.mozilla.org/en-US/docs/Web/API/Storage) object for the [`Document`](https://developer.mozilla.org/en-US/docs/Web/API/Document)'s [origin](https://developer.mozilla.org/en-US/docs/Glossary/Origin); the stored data is saved across browser sessions.
>
> `localStorage` is similar to [`sessionStorage`](https://developer.mozilla.org/en-US/docs/Web/API/Window/sessionStorage), except that while `localStorage` data has no expiration time, `sessionStorage` data gets cleared when the page session ends — that is, when the page is closed. (`localStorage` data for a document loaded in a "private browsing" or "incognito" session is cleared when the last "private" tab is closed.)
>
> _-_ [_MDN Docs_](https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage)__

### Advantages

* Even if the browser window is closed, the data doesn't get deleted.&#x20;
* No need for external database
* No need for a backend (or at least dependency, an app with backend might use local storage as well.)
* There's a React hook for this. So it's going to be easy to use it in React.&#x20;

## Usage

I'll need to use `useState()` and `useEffect()` hooks along with the hook for the localStorage.&#x20;

### Methods for working with localStorage

| Method         | Usage                                                                                                    |
| -------------- | -------------------------------------------------------------------------------------------------------- |
| `setItem()`    | Add a key and a value to localStorage.                                                                   |
| `getItem()`    | Get an item from localStorage using the key.                                                             |
| `removeItem()` | <p>Delete an item from localStorage based on <br>its key.</p>                                            |
| `clear()`      | Delete all instances of localStorage.                                                                    |
| `key()`        | Not clear, but the page says “When you supply a number, it aids in the retrieval of a localStorage key.” |

According to the freecodecamp article, the most important ones are the first two. So I'll learn only those two first.&#x20;

### Using setItem()

* Anything can be stored in the `localStorage`, text, arrays, objects etc.
* Before storing anything, I need to stringify it by passing it through `JSON.stringify()`

Syntax for setting items into the `localStorage` as soon as its state changes in the app:

```javascript
const [items, setItems] = useState([]);

useEffect(() => {
  localStorage.setItem('items', JSON.stringify(items));
}, [items]);
```

### Using getItem()

Syntax for getting items and storing into a state:

```javascript
const [items, setItems] = useState([]);

useEffect(() => {
  const items = JSON.parse(localStorage.getItem('items'));
  if (items) {
   setItems(items);
  }
}, []);
```

### Using removeItem()

From [an answer from Stack Overflow](https://stackoverflow.com/a/50664919/5864207):

```javascript
removeItem = () => localStorage.removeItem("name")
```

\
