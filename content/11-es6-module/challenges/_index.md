+++
title = "Module 11 Challenge ⭐"
weight = 1
tags = ["es6"] 
+++

### Download your starter code for module 11 challenge 


For this Challenge please unzip the zip file.

{{%attachments style="green" /%}}

In this Challenge, you'll build a command-line application that dynamically generates a professional `README.md` file from a user's input.

### Working with ES6 & Node.js: Professional README Generator
When creating an open source project on GitHub, it's important to have a high-quality README for the app. This should include the app's purpose, how to use the app, how to install it, how to report issues, and how to make contributions. This last part increases the likelihood that other developers will contribute to the success of the project.

You can quickly and easily create a README file by using a command-line application to generate one. This allows the project creator to devote more time to working on the project.

Your task is to create a command-line application that dynamically generates a professional README.md file from a user's input using the [Inquirer package](https://www.npmjs.com/package/inquirer) Review the Professional [README Guide](https://coding-boot-camp.github.io/full-stack/github/professional-readme-guide) as a reminder of everything that a high-quality, professional README should contain.

The application will be invoked by using the following command:

```js
node index.js
```
Because this application won't be deployed, you'll also need to provide a link to a walkthrough video that demonstrates its functionality. Review the Video Submission Guide Links to an external site.before you get started. You'll need to submit a link to the video and add it to the README of your project.

Before you begin, download your starter code Links to an external site.for this Challenge and unzip the zip file.

User Story
AS A developer
I WANT a README generator
SO THAT I can quickly create a professional README for a new project
Acceptance Criteria
Create a command-line application that accepts user input.

When a user is prompted for information about the application repository, a high-quality, professional README.md is generated with:

The title of my project

Sections entitled:

Description

Table of Contents

Installation

Usage

License

Contributing

Tests

Questions

When a user enters the project title, it's displayed as the title of the README.

When a user enters a description, installation instructions, usage information, contribution guidelines, and test instructions, this information is added to the sections of the README entitled Description, Installation, Usage, Contributing, and Tests.

When a user chooses a license for their application from a list of options, a badge for that license is added near the top of the README and a notice is added to the section of the README entitled License that explains which license the application is covered under.

When a user enters their GitHub username, it's added to the section of the README entitled Questions, with a link to their GitHub profile.

When a user enters their email address, it's added to the section of the README entitled Questions, with instructions on how to reach them with additional questions.

When a user clicks on the links in the Table of Contents, they are taken to the corresponding section of the README.

Getting Started
Here are some guidelines to help you get started:

Create a .gitignore file and include node_modules/ and .DS_Store/ so that your node_modules directory isn't tracked or uploaded to GitHub. Be sure to create your .gitignore file before installing any npm dependencies.

Make sure that your repo includes a package.json with the required dependencies. You can create one by running npm init when you first set up the project, before installing any dependencies.