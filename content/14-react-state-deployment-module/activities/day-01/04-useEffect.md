+++
title = "04. useEffect 👩‍🎓👨‍🎓"
weight = 4
tags = ["react"] 
+++

In this activity, we will practice using the useState and useEffect Hooks in React by transforming a stateful class component into a functional component with React Hooks.

# Instructions

* Replace your React application's src folder with [starter/src](starter/src).

* If you created a new React app, you will need to install Axios and React Router.

* Start the application in dev mode by running `npm start` in your terminal.

* Open your browser to [localhost:3000](http://localhost:3000) and study the rendered application.

* Update this application to accomplish the following:

* In `pages/Search/index.js`, create a functional component in place of the class component.

* Replace `this.state` and all instances of `this.setState` using the `useState` Hook.

* Replace all component lifecycle methods with their Hook counterparts.

* Remove the search button and utilize the `useEffect` Hook to query every time the user inputs anything into the search bar. 

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
  document.title = "Wikipedia Searcher";
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
# API.js
```js
import axios from "axios";

// Export an object containing methods we'll use for accessing the GitHub Jobs API

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

### Search.js
```js
import React, { useState, useEffect } from "react";
import API from "../../utils/API";
import Container from "../../components/Container";
import SearchForm from "../../components/SearchForm";
import SearchResults from "../../components/SearchResults";
import Alert from "../../components/Alert";

function Search() {
  const [search, setSearch] = useState("Wikipedia");
  const [title, setTitle] = useState("");
  const [url, setUrl] = useState("");
  const [error, setError] = useState("");

  useEffect(() => {
    if (!search) {
      return;
    }

    API.searchTerms(search)
      .then(res => {
        if (res.data.length === 0) {
          throw new Error("No results found.");
        }
        if (res.data.status === "error") {
          throw new Error(res.data.message);
        }
        setTitle(res.data[1][0]);
        setUrl(res.data[3][0]);
      })
      .catch(err => setError(err));
  }, [search]);

  const handleInputChange = event => {
    setSearch(event.target.value);
  };

  return (
    <div>
      <Container style={{ minHeight: "100vh" }}>
        <h1 className="text-center">Search For Anything on Wikipedia</h1>
        <Alert type="danger" style={{ opacity: error ? 1 : 0, marginBottom: 10 }}>
          {error}
        </Alert>
        <SearchForm
          handleInputChange={handleInputChange}
          results={search}
        />
        <SearchResults title={title} url={url} />
      </Container>
    </div>
  );
}

export default Search;
```

### Signup.js
```js
import React, { useState } from "react";
import Container from "../../components/Container";
import Col from "../../components/Col";
import Row from "../../components/Row";

const Signup = () => {
  const [username, setUsername] = useState();
  const [password, setPassword] = useState();

  const handleSubmit = e => {
    e.preventDefault();
    console.log("username is " + username);
    console.log("password is " + password);
  };

  return (
    <div>
      <div className="mt-4">
        <h2>Welcome to Wikipedia Searcher!</h2>
      </div>
      <form onSubmit={handleSubmit}>
        <Container className="mt-3 px-5">
          <Row className="form-group">
            <Col size="12">
              <input
                className="form-control"
                type="text"
                placeholder="Username"
                name="username"
                onChange={e => setUsername(e.target.value)}
              />
            </Col>
          </Row>
          <Row className="form-group">
            <Col size="12">
              <input
                className="form-control"
                type="password"
                placeholder="Password"
                name="password"
                onChange={e => setPassword(e.target.value)}
              />
            </Col>
          </Row>
          <button className="btn btn-success" type="submit">
            Submit
          </button>
        </Container>
        <Container className="mt-4">
          <h3>Hello {username}!</h3>
          <p>I probably shouldn't tell you this, but your password is {password}!</p>
        </Container>
      </form>
    </div>
  );
};

export default Signup;
```

{{% /expand%}}