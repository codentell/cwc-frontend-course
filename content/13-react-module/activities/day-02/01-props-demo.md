+++
title = "01. Props"
weight = 1
tags = ["react"] 
+++

### Alert.js
```js
import React from "react";

function Alert(props) {
  console.log(props);

  return (
    <div className={`alert alert-${props.type || "success"}`} role="alert">
      {props.children}
    </div>
  );
}

export default Alert;
```

### App.js
```js
import React from "react";
import Alert from "./components/Alert";

function App() {
  return <Alert type="danger">Invalid user id or password</Alert>;
}

export default App;
```