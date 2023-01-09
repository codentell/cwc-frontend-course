+++
title = "02. Window Object 👩‍🎓👨‍🎓"
weight = 2
tags = ["web apis"] 
+++

# 📐 Add Comments to Implementation of Window Object

Work with a partner to add comments describing the functionality of the code found in [Starter Window Object Activity Files](./02-Stu-Window-Object/starter/script.js).

## 📝 Notes

Refer to the documentation: 

[MDN Web Docs on Window](https://developer.mozilla.org/en-US/docs/Web/API/Window)

[MDN Web Docs on Document](https://developer.mozilla.org/en-US/docs/Web/API/Document)

---

## 🏆 Bonus

If you have completed this activity, work through the following challenge with your partner to further your knowledge:

* How would you log the `length` property of the `window` object?  

Use [Google](https://www.google.com) or another search engine to research this.

---

```js
// TODO: What will the following line of code log?
console.log(window);

// TODO: What will the following line of code log?
console.log(window.document);

// TODO: What will the following line of code log?
console.log(document.documentElement);

// TODO: What will the following line of code log?
console.log(document.head);
```

## ✅ Solutions 
{{%expand "Solutions Click Here" %}}
### script.js
```js
// Logs window object
console.log(window);

// Logs reference to the document in the window object
console.log(window.document);

// Logs root element of document.
console.log(document.documentElement);

// Returns head element of current document
console.log(document.head);
```
{{% /expand%}}