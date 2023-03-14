+++
title = "03. Configure Enzyme 👩‍🎓👨‍🎓"
weight = 3
tags = ["react"] 
+++

# Configuring Enzyme with a React Project

During this activity, we will configure `Enzyme` within our React project. By default, CRA creates a file called `setupTest.js`. This file allows us to provide a reference to the adapter package that we installed in [02-We-CRA16](#). The configuration makes `enzyme` and `enzyme-adapter-react-16` available to our entire React project so that we are able to utilize it in every test file we create.

## Instructions

Perform the following actions inside of the `src/setupTest.js` file:
1. Import the `configure` method from the `enzyme` package.
2. Import the `Adapter` class from `enzyme-adapter-react-16`.
3. Configure the `enzyme` adapter to be the default adapter in our project.
   1. Invoke the `configure` method.
   2. Pass it an object with a **key** of `adapter`, and its **value** should be a new instantiated instance of the `Adapter` class that was imported earlier.

---

```json
{
  "name": "click-counter-testing",
  "version": "0.1.0",
  "private": true,
  "dependencies": {
    "@testing-library/jest-dom": "^5.11.9",
    "@testing-library/react": "^11.2.5",
    "@testing-library/user-event": "^12.7.1",
    "enzyme": "^3.11.0",
    "enzyme-adapter-react-16": "^1.15.6",
    "react": "^16.14.0",
    "react-dom": "^16.14.0",
    "react-scripts": "4.0.2",
    "web-vitals": "^1.1.0"
  },
  "scripts": {
    "start": "react-scripts start",
    "build": "react-scripts build",
    "test": "react-scripts test",
    "eject": "react-scripts eject"
  },
  "eslintConfig": {
    "extends": [
      "react-app",
      "react-app/jest"
    ]
  },
  "browserslist": {
    "production": [
      ">0.2%",
      "not dead",
      "not op_mini all"
    ],
    "development": [
      "last 1 chrome version",
      "last 1 firefox version",
      "last 1 safari version"
    ]
  }
}

```