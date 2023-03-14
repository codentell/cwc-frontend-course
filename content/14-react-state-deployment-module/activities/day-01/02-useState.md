+++
title = "02. useState 👩‍🎓👨‍🎓"
weight = 2
tags = ["react"] 
+++

# useState

In this activity, we will practice using the useState Hook in React.

## Instructions

- Replace your React application's src folder with [starter/src](starter/src).

- If you created a new React app, you will need to install Bootstrap by running `npm install --save bootstrap` and adding `import 'bootstrap/dist/css/bootstrap.min.css';` in `index.js`.

- Start the application in dev mode by running `npm start` in your terminal.

- Open your browser to [localhost:3000](http://localhost:3000) and study the rendered application.

- Update this application to accomplish the following:

- In `pages/Signup/index.js`, replace `NAME_HERE` and `PASSWORD_HERE` with code that will display both the name and password.

- The state of the Signup component should be handled by the useState Hook.

- When the value of an input field changes, the state should update, causing the component to render.

- Upon form submission, the `handleSubmit` method should `console.log` the username and password.

---

## ✅ Solutions 
{{%expand "Solutions Click Here" %}}
### App.js
```js
import React from "react";
import Signup from "./pages/Signup";
import "./App.css";

function App() {
  return (
    <div className="App">
      <Signup />
    </div>
  );
}

export default App;

```


### Signup.js
```js
import React, { useState } from "react";
import Container from "../../components/Container";
import Col from "../../components/Col";
import Row from "../../components/Row";

function Signup() {
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
        <h2>Sign Up</h2>
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
}

export default Signup;
```
{{% /expand%}}