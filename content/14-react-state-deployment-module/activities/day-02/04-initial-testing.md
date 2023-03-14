+++
title = "04. initial testing 👩‍🏫🧑‍🏫"
weight = 4
tags = ["react"] 
+++

how to write failing Enzyme tests for React components.

## Instructions
Inside of `src/App.test.js`, write a failing test for the following requirements:

* Test 1:
  * **Name:** `App Component Renders Without Error`
  * **Test case:** Write a test that checks to see if our `App` component renders without throwing an error.
* Test 2:
  * **Name:** `App Component Renders a Button`
  * **Test case:** Write a test that checks if the button within the `App` component renders properly.
* Test 3:
  * **Name:** `Counter Starts at 0`
  * **Test case:** Write a test that checks if the counter starts at 0.
* Test 4:
  * **Name:** `Clicking Increment Button Increases Counter Display`
  * **Test case:** Write a test that checks if the increment button increases the count.

---

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
```
