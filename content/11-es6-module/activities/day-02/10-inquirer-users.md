+++
title = "10. Inquirer Users 👩‍🎓👨‍🎓"
weight = 10
tags = ["es6"] 
+++

# 🏗️ Build CLI App with inquirer

Work with a partner to implement the following user story:

* As a developer, I want to create a command-line application that takes in input from the user and does something with it.

## Acceptance Criteria

* It's done when I have initialized my repository with a `package.json` file by running `npm init -y`.

* It's done when I have installed inquirer and added it to my list of dependencies by running `npm i inquirer --save`.

* It's done when the application asks the user, "What is your name?"
  
* It's done when the application asks the user, "What languages do you know?"

* It's done when the application asks the user, “What is your preferred method of communication?"

* It's done after I have written those responses to a file.

## 💡 Hint

Why do we need to use `JSON.stringify`? How can we use the npm page for `inquirer` to see how to use checkboxes and lists? 

## 🏆 BONUS

If you have completed this activity, work through the following challenge with your partner to further your knowledge:

* How would you format your JSON? Can you generate the name of your user file from the user input?

Use [Google](https://www.google.com) or another search engine to research this.

---

## ✅ Solutions 
{{%expand "Solutions Click Here" %}}
### package.json
```json
{
  "name": "Solved",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "dependencies": {
    "inquirer": "^6.5.0"
  }
}
```

### index.js
```js
const inquirer = require('inquirer');
const fs = require('fs');

inquirer
  .prompt([
    {
      type: 'input',
      name: 'name',
      message: 'What is your name?',
    },
    {
      type: 'checkbox',
      message: 'What languages do you know?',
      name: 'stack',
      choices: ['HTML', 'CSS', 'JavaScript', 'MySQL'],
    },
    {
      type: 'list',
      message: 'What is your preferred method of communication?',
      name: 'contact',
      choices: ['email', 'phone', 'telekinesis'],
    },
  ])
  .then((data) => {
    const filename = `${data.name.toLowerCase().split(' ').join('')}.json`;

    fs.writeFile(filename, JSON.stringify(data, null, '\t'), (err) =>
      err ? console.log(err) : console.log('Success!')
    );
  });
```

{{% /expand%}}