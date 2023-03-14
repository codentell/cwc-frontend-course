+++
title = "07. Third Party Hook 👩‍🎓👨‍🎓"
weight = 7
tags = ["react"] 
+++

# Third-Party Hooks

In this activity, we will practice using third-party Hooks. Specifically, we will be creating a survey form using the `react-hanger` package on npm.

## Instructions

* Replace your React application's src folder with [starter/src](starter/src).

* Install react-hanger by running `npm install react-hanger` in your terminal.

* This activity uses Bootstrap, so make sure that you `import 'bootstrap/dist/css/bootstrap.min.css';` in `index.js`.

* **Recommended:** Add the Font Awesome CDNs to your application's `index.html` file:

  ```html
  <link href="https://maxcdn.bootstrapcdn.com/font-awesome/4.7.0/css/font-awesome.min.css" rel="stylesheet" />
  ```

* Start the application in dev mode by running `npm start` in your terminal.

* Open your browser to [localhost:3000](http://localhost:3000) and study the rendered application.

  * There are a few fields in our survey form. Before writing any code, try thinking about how you would manage the state of this form. 

* Navigate to the [react-hanger docs](https://github.com/kitze/react-hanger) and familiarize yourself with the `useInput`, `useBoolean`, and `useNumber` Hooks.

* Update this application to accomplish the following:

  * Each user input should be handled using the `react-hanger` Hooks.

  * When the user clicks an emoji, indicate which type of response they selected by displaying the text `You responded that you feel FEELING`. `FEELING` should be replaced with the value of the emoji that they clicked.

  * Make your survey form a little more dynamic by displaying a field for additional comments when the user clicks on an emoji.

  * When the form is submitted, `console.log` an object containing all of the values from the form.

### Hint

* There are many ways to satisfy the requirements of this application. It is recommended that you attempt the most straightforward solution first, then refactor your working app.

---
## ✅ Solutions 
{{%expand "Solutions Click Here" %}}

### App.js

```js
import React from "react";
import Survey from "./pages/Survey";
import "./App.css";

function App() {
  return (
      <div>
          <Survey />
      </div>
  );
}

export default App;
```

### Survey.js
```js
import React from "react";
import {
  useInput,
  useBoolean,
  useNumber,
} from "react-hanger";

function Survey() {
  const favoriteThing = useInput("");
  const showComment = useBoolean(false);
  const comment = useInput("");
  const feeling = useInput("");
  const rating = useNumber(0)

  const handleSubmit = () => {
    const form = {
      favoriteThing: favoriteThing.value,
      comment: comment.value,
      feeling: feeling.value,
      rating: rating.value
    }
    console.log(form)
  }

  return (
    <div className="container">
      <h1>Use this form to provide feedback for our product!</h1>
      
      <h4>What was your favorite thing about our product?</h4>
      <textarea {...favoriteThing.eventBind} />

      <h4>How would you rate our product?</h4>
      <div className="form-group" >
        <input type="radio" name="rating-1" onChange={() => rating.setValue(1)} />1
        <input type="radio" name="rating-1" onChange={() => rating.setValue(2)} />2
        <input type="radio" name="rating-1" onChange={() => rating.setValue(3)} />3
        <input type="radio" name="rating-1" onChange={() => rating.setValue(4)} />4
        <input type="radio" name="rating-1" onChange={() => rating.setValue(5)} />5
      </div>
      
      <h4>How did our product make you feel?</h4>
      <div className="form-group emoji" >
        <span role="img" aria-label="angry" 
          onClick={() => {showComment.toggle(); feeling.setValue("angry")} }>
            😠
        </span>
        <span role="img" aria-label="indifferent"
          onClick={() => {showComment.toggle(); feeling.setValue("indifferent")}}>
            😒
        </span>
        <span role="img" aria-label="happy"
          onClick={() => {showComment.toggle(); feeling.setValue("happy")}}>
            😄
        </span>
        <div className="response">
        {showComment.value ? (
          <textarea {...comment.eventBind} placeholder="Please add any additional comments" />
        ): null}
        </div>
        <div>
      {showComment.value ? (
          <span>You've responded that you feel {feeling.value}</span>
        ): null}
      </div>
      </div>
      <button onClick={handleSubmit}>Submit</button>
    </div>
  );
};

export default Survey;
```

{{% /expand%}}