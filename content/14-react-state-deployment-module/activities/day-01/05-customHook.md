+++
title = "05. customHook 👩‍🏫🧑‍🏫"
weight = 5
tags = ["react"] 
+++

### App.js
 ```js
import React, { useState, useEffect } from "react";
import "./App.css";
//Importing the custom hook from the utils folder.
import useUserStatus from "./utils/useUserStatus";

function App() {
  const [developerState, setDeveloperState] = useState({
    excitementLevel: 1000,
    lifeLongLearner: true,
    name: "Riley",
  });

  // Destructing the state and method from the custom hook.
  const { statusState, status } = useUserStatus();

  useEffect(() => {
    //Display the value in the console. Initially it is empty.
    console.log(statusState);
    //useEffect will trigger when the state changes.
  }, [statusState]);

  return (
    <div className="card">
      <div>Name: {developerState.name}</div>
      {/* JSX below to display the statusState from the hook. */}
      <div>Status: {statusState}</div>
      <div>Lifelong learner: {developerState.lifeLongLearner.toString()}</div>
      <div>Excitement Level: {developerState.excitementLevel}</div>
      <div className="btn-group">
        <form className="form-group">
          <label htmlFor="status">Enter your Status: </label>
          <input
            className="form-control mb-4"
            id="status"
            // Using JSX destructing on the status property from the custom hook will insert
            // the value attribute and the onChange event handler.
            {...status}
          />
        </form>
        <button
          onClick={() =>
            setDeveloperState({
              ...developerState,
              excitementLevel: developerState.excitementLevel + 1000,
            })
          }
          className="btn btn-success"
        >
          Increase Excitement Level
        </button>
        <button
          onClick={() =>
            setDeveloperState({
              ...developerState,
              excitementLevel: developerState.excitementLevel - 1000,
            })
          }
          className="btn btn-success"
        >
          Decrease Excitement Level
        </button>
      </div>
    </div>
  );
}

export default App;

 ```

 ### API.js
 ```js
 // This code is meant to serve as a mock fetch from an API.
export const getDeveloper = new Promise(function(resolve) {
  setTimeout(() => {
    resolve({
      excitementLevel: 10000,
      lifeLongLearner: true,
      mood: "excited",
      name: "Alec"
    });
  }, 1000);
});
```

### useUserStatus.js
```js
import { useState } from "react";

const useUserStatus = () => {
  // useState using statusState to represent state, and setStatusState to set that specific state
  const [statusState, setStatus] = useState("");

  // returning the state and the status object which will be used the capture the value from the form.
  return {
    statusState,
    status: {
      value: statusState,
      onChange: (e) => setStatus(e.target.value),
    },
  };
};
export default useUserStatus;
```