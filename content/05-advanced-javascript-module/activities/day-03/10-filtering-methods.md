+++
title = "10. Filtering Methods 👩‍🎓👨‍🎓"
weight = 10
tags = ["advanced javascript"] 
+++

# 📖 Filtering Methods

* As a developer, I want to search through an array of accounts and find or filter users based on criteria.

## Instructions

* Create an array of account objects that have a `firstName`, `lastName`, and a `balance`

* Use the find method to search through the array and print the first account with a balance equal to $250,000, and print it to the console.

* Use the filter method to create a new array of only Users with a last name that begins with the same letter, and print it to the console.

---


## ✅ Solutions 
{{%expand "Solutions Click Here" %}}
### script.js
```js
var accounts = [
  {
    firstName: 'John',
    lastName: 'Doe',
    balance: 25000
  },
  {
    firstName: 'Jane',
    lastName: 'Doe',
    balance: 100000
  },
  {
    firstName: 'Bill',
    lastName: 'Smith',
    balance: 65000
  },
  {
    firstName: 'Lily',
    lastName: 'Potter',
    balance: 250000
  },
  {
    firstName: 'Killian',
    lastName: 'Trystvale',
    balance: 500
  }
]

console.log('Account with $250,000 belongs to: ', accounts.find(function(i) {
  if (i.balance === 250000) {
    return (i.firstName.toString() + i.lastName.toString())
  }
}))

console.log('All acounts with last names that begin with D: ', accounts.filter(function(i) {
  return i.lastName.charAt(0) === 'D'
}))
```
{{% /expand%}}