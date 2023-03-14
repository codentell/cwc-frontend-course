+++
title = "09.  Custom helper functions 👩‍🎓👨‍🎓"
weight = 7
tags = ["react"] 
+++

# Refactor App.test.js: Create Custom Helper Functions

In this activity, you will reinforce and build upon the testing skills that you have learned so far by refactoring your code to contain the `setup` and `findByTestAttr` function that were demonstrated by the instructor in [08-Ins-CustomHelperFunctions](../08-Ins-CustomHelperFunctions/README.md).

## Instructions

Inside of `src/App.test.js`, create two helper functions:

1. `setup()`: This function should accept no arguments and return a shallow render of the app component each time it is invoked.

2. `findByTestAttr()`: This function should accept two arguments, `wrapper` and `value`, and perform a find lookup within the wrapper based on the `data-test` value provided.
  
  * Wrapper is the component wrapper we want to look within.
  
  * Value is the test attribute value that we are searching for.

---

## ✅ Solutions 
{{%expand "Solutions Click Here" %}}
### App.test.js
```js
import App from './App'
import { shallow } from 'enzyme'


const setup = () => shallow(<App />)

const findByTestAttr = (wrapper, value) => wrapper.find(`[data-test='${value}']`)

// Test 1
it('App Component Renders Without Error', () => {
  const wrapper = shallow(<App />)
})

// Test 2
it("App Component Renders a Button", () => {
  const wrapper = shallow(<App />)
  const button = wrapper.find('[data-test="increment-button"]')

  expect(button.length).toBe(1)
})

// Test 3
it("Counter Starts At 0", () => {
  const wrapper = shallow(<App />)
  const count = wrapper.find('[data-test="count"]').text()

  expect(count).toBe("0")
})

// Test 4
it("Clicking Increment Button Increases Counter Display", () => {
  const wrapper = shallow(<App />)
  const button = wrapper.find('[data-test="increment-button"]')

  button.simulate('click')

  const count = wrapper.find('[data-test="count"]').text()

  expect(count).toBe('1')
})

// Test 5
it("App Component Renders the Counter Display", () => {
  const wrapper = shallow(<App />)
  const counterDisplay = wrapper.find('[data-test="counter-display"]')

  expect(counterDisplay.length).toBe(1)
})

// Test 6
it('App Component Renders a Decrement Button', () => {
  const wrapper = shallow(<App />)

  const button = wrapper.find('[data-test="decrement-button"]')

  button.simulate('click')

  const count = wrapper.find('[data-test="count"]').text()

  expect(count).toBe('0')
})

// Test 7
it('Count is Unable to go Below Zero and Throws Error', () => {
  const wrapper = shallow(<App />)
  const button = wrapper.find('[data-test="decrement-button"]')
  const errorMessage = wrapper.find('[data-test="error-message"]').text()

  button.simulate('click')

  expect(errorMessage).toEqual('The counter can not go below zero')
})

// Test 8
it("Decrement Error Message Clears When Count Increment Higher than 0", () => {
  const wrapper = shallow(<App />)
  const errorMessage = wrapper.find('[data-test="error-message"]').text()
  const button = wrapper.find('[data-test="increment-button"]')

  button.simulate('click')
  expect(errorMessage).toEqual('')
})
```
{{% /expand%}}