+++
title = "05.  Initial Testing 👩‍🎓👨‍🎓"
weight = 5
tags = ["react"] 
+++

In this activity, you reinforce and build upon the testing skills you have learned so far by writing a test for your `click-counter-testing` React application.

## Instructions
Inside of `src/App.test.js`, continue where we left off and write a failing test for the following requirements:

* Test 5:
  * **Name:** `App Component Renders the Counter Display`
  * **Test case:** Write a test that checks to see if the counter display renders properly.
* Test 6:
  * **Name:** `App Component Renders a Decrement Button`
  * **Test case:** Write a test for a decrement button.
* Test 7:
  * **Name:** `Count Is Unable to Go Below Zero and Throws Error`
  * **Test case:** Write a test that will not allow the counter to go below 0 and display an error message.
* Test 8:
  * **Name:** `Decrement Error Message Clears When Count Increment Higher Than 0`
  * **Test case:** Clear the error message on increment and counter increases.

---

## ✅ Solutions 
{{%expand "Solutions Click Here" %}}
### initial testing
```js
import App from './App'
import { shallow } from 'enzyme'

// Test 1: Write a test that checks to see if our `App` component renders without throwing an error.
it('App Component Renders Without Error', () => {
  const wrapper = shallow(<App />)
})

// Test 2: Write a test that checks if the button within the `App` component renders properly.
it("App Component Renders a Button", () => {
  const wrapper = shallow(<App />)
  const button = wrapper.find('[data-test="increment-button"]')

  expect(button.length).toBe(1)
})

// Test 3: Write a test which checks if the counter starts at 0.
it("Counter Starts At 0", () => {
  const wrapper = shallow(<App />)
  const count = wrapper.find('[data-test="count"]').text()

  expect(count).toBe("0")
})

// Test 4: Write a test which checks if the increment button increase the count.
it("Clicking Increment Button Increases Counter Display", () => {
  const wrapper = shallow(<App />)
  const button = wrapper.find('[data-test="increment-button"]')

  button.simulate('click')

  const count = wrapper.find('[data-test="count"]').text()

  expect(count).toBe('1')
})

// Test 5: Write a test which checks to see if the counter display renders properly.
it("App Component Renders the Counter Display", () => {
  const wrapper = shallow(<App />)
  const counterDisplay = wrapper.find('[data-test="counter-display"]')

  expect(counterDisplay.length).toBe(1)
})

// Test 6: Write a test for a decrement button
it('App Component Renders a Decrement Button', () => {
  const wrapper = shallow(<App />)

  const button = wrapper.find('[data-test="decrement-button"]')

  button.simulate('click')

  const count = wrapper.find('[data-test="count"]').text()

  expect(count).toBe('0')
})

// Test 7: Write a test which will not allow the counter to go below 0 and display an error message
it('Count is Unable to go Below Zero and Throws Error', () => {
  const wrapper = shallow(<App />)
  const button = wrapper.find('[data-test="decrement-button"]')
  const errorMessage = wrapper.find('[data-test="error-message"]').text()

  button.simulate('click')

  expect(errorMessage).toEqual('The counter can not go below zero')
})

// Test 8: Clear the error message on Increment
it("Decrement Error Message Clears When Count Increment Higher than 0", () => {
  const wrapper = shallow(<App />)
  const errorMessage = wrapper.find('[data-test="error-message"]').text()
  const button = wrapper.find('[data-test="increment-button"]')

  button.simulate('click')
  expect(errorMessage).toEqual('')
})
```
{{% /expand%}}


