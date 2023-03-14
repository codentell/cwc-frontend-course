+++
title = "06. customHook 👩‍🎓👨‍🎓"
weight = 6
tags = ["react"] 
+++

In this activity, we will practice using custom Hooks by creating a `useDebounce` Hook that will delay the invoking of a function for a given number of milliseconds.

  # Instructions

  * Replace your React application's src folder with [starter/src](starter/src).

  * Start the application in dev mode by running `npm start` in your terminal.

  * Open your browser to [localhost:3000](http://localhost:3000) and study the rendered application.

  * Update this application to accomplish the following:

  * Create a new custom Hook called `useDebounce` that takes in the two parameters `value` and `delay`.

  * Use `setTimeout` to handle the value of the debouncer.

  * Update the `Search` page so that the `useEffect` Hook is listening for the value returned from the `useDebounce` Hook. Pass in a `delay` value of 500.

  * The finished application should only search for a new article if there has been a period of 500 milliseconds without any user input.

---

## ✅ Solutions 
{{%expand "Solutions Click Here" %}}

### App.js
```js
import React from "react";
import { BrowserRouter as Router, Route } from "react-router-dom";
import Signup from "./pages/Signup";
import Search from "./pages/Search";
import Navbar from "./components/Navbar";
import Footer from "./components/Footer";
import Wrapper from "./components/Wrapper";
import "./App.css";

function App() {
  return (
    <Router>
      <div>
        <Navbar />
        <Wrapper>
          <Route exact path="/" component={Search} />
          <Route exact path="/signup" component={Signup} />
          <Route exact path="/search" component={Search} />
        </Wrapper>
        <Footer />
      </div>
    </Router>
  );
}

export default App;


```

### API.js
```js
import axios from "axios";

// Export an object containing methods we'll use for accessing the Wikipedia API

export default {
  searchTerms: function(query) {
    return axios.get(
      "https://en.wikipedia.org/w/api.php?action=opensearch&search=" +
        query +
        "&limit=1&format=json&origin=*"
    );
  }
};

```

### debounceHook
```js
import { useEffect, useState } from "react";

const useDebounce = (value, delay) => {
  const [debouncedValue, setDebouncedValue] = useState(value);
  useEffect(
    () => {
      const handler = setTimeout(() => {
        setDebouncedValue(value);
      }, delay);
      // Cancel the timeout if value or delay changes
      return () => {
        clearTimeout(handler);
      };
    },
    // Only call the effect if value or delay changes.
    [value, delay]
  );

  return debouncedValue;
};

export default useDebounce;

```

{{% /expand%}}