---
title: "JS Events"
date: 2022-02-20T09:13:09+03:00
draft: false
summary: Listening and responding to events in JavaScript.
weight: 6
tags: [JS, JS Events, front-end]
toc: true  # Show table of contents? true/false
type: docs  # Do not modify.
menu:
  swe363:
    js:
      name: JS Events 
      weight: 3

---

## Objectives
Learn the basics of using JavaScript for listening and responding to different events that may happen in a web page.
## Introduction
In a web page, many events can occur. When the page loads, when clicking on a button, when changing a selection of choices, when pressing a key on the keyboard editing some input, and many others. JavaScript can listen for these events and execute some code to customize the behaviour in response the their occurrence.
## Worked Example
In this handout, we will use JavaScript to listen and handle different events. The final behaviour looks as follows. 
{{< youtube AYqYlJEppq4 >}}
1. After two seconds from loading the page, the form disappears.
1. Clicking on the button reveals the form and disappears.
1. Capitalize the first name as the user types
1. Validate that the email is filled before submitting the form
1. Validate that the username only contains alphanumeric characters and underscores
1. Remind the user to receive our promotion and respect his decision  

It is recommended that you write the code your self before expanding the given solution. Try to avoid coping and pasting.  

### HTML code

In the HTML body, we would like to  have a form to demonstrate different events and how to handle them.
 {{< detailsumary title="Index.html" >}}
```html {linenos=table,hl_lines=["12-14", 21],linenostart=1}
<!DOCTYPE html>
 <html lang="en">
 <head>
     <meta charset="UTF-8">
     <meta http-equiv="X-UA-Compatible" content="IE=edge">
     <meta name="viewport" content="width=device-width, initial-scale=1.0">
     <title>JS Demo</title>
     <link rel="stylesheet" href="style.css">
 </head>
 
 <body>
     <button onclick="showForm(this)">click to register</button>
     <form onsubmit="return validate()" action="" name="register" method="GET" class="form" autocomplete="off">
         <input onkeyup="capitalize(this)" type="text" name="firstname" placeholder="first name">
         <input type="email" name="email" placeholder="email">
         <input type="text" name="username" placeholder="username">
         <input type="checkbox" name="promo" id="promo">
         <label for="promo">Send me Promotions</label>
         <input type="submit" value="Submit">
     </form>
     <script src="index.js"></script>
 </body>
 </html>
 ```
{{< /detailsumary >}}
As shown in line 8 and 21 we are linking external CSS and JS files.

### Simple Style
 {{< detailsumary title="Simple CSS rules" >}}
 ```css {linenos=table,linenostart=1}
 body{
     background-color: antiquewhite;
 }
 .form input{
     display: block;
     margin-top: 1rem;
     padding: .75rem;
 }
 button{
     padding: 1em;
     font-size: 1.2rem;
 }
 ```
  {{< /detailsumary >}}
### 1. JS Listening and responding to page `load`
Page loading is one of the `window` related events. 
It is fired when the browser completes loading the page components (HTML,CSS,JS).  
To target this event, we provide a handler to be called when the event fires. In this example, we would like to wait for 2 seconds then hide the form. This can be done using `setTimeout`.

As shown in the video, the form slides out of the screen. This can be done by changing its CSS `margin-left` to a negative value.
To get a reference to the form we can use the `DOM` to find an HTML element named `register`. 
To change the CSS style of an element we can set the desired property on `element.style`. The name of the property (`margin-left` in our case) will be the same except it is camelCased (ie `marginLeft`). 
 {{< detailsumary title="Hide the form" >}}
```js {linenos=table,hl_lines=[1, 4],linenostart=1}
document.onload = setTimeout(hideForm, 2000);
const form = document.register;
function hideForm() {
    form.style.marginLeft = "-300px";
}
```
 {{< /detailsumary >}}

### 2. Reshowing the form `onclick`
The first element in the HTML body is a button. As on line 12, we added `onclick` attribute to the button. This is the second way to listen and respond to events.
When the user clicks on this button the function named `showForm` will be called.
To show the form we can reverse the way it was hidden by resetting the `left-margin` to 0.
The parameter `this` is a reference to the clicked button. We can use this reference to hide the button. It will be assigned to the `eventSource` parameter.
 {{< detailsumary title="Reshow the form" >}}
```js {linenos=table,linenostart=6}
function showForm(eventSource) {
    form.style.marginLeft = "0px";
    eventSource.style.display = "none";
}
```
 {{< /detailsumary >}}
 ### 3. Capitalize the first name as the user types
 To change the case as the user types, we target the `onkeyup` keyboard event on the first-name field as in line 14.
 This event will be fired after each keyboard keypress. When it occurs, the `value` attribute holds the current entered text. We replace it with the capital version using the `toUpperCase` string function.
  {{< detailsumary title="Capitalize text" >}}
  ```js {linenos=table,linenostart=10}
  function capitalize(inputField) {
      inputField.value = inputField.value.toUpperCase();
  }
  ```
   {{< /detailsumary >}} 
### 4. Validate that the email is filled before submitting the form
So far we targeted individual inputs and handled events on them. But now we are interested in validating the form before we send it to the server.
There are different levels of validating the form. The first, using HTML 5 tags: by setting the type to `email`, the browsers will validate that it at least contains `@` symbol.
The second level, using client-side javascript: by handling the `onsubmit` form event and check the inputs before submitting.
The third level using server-side scripting when receiving the form data.

In this step, we do the second level of validation. As shown in line 13 of the HTML, the    `<form>` tag sets the `onsubmit` handler to the return of `validate()`. 
 This means if this function returns `true`, the form is valid and can be sent to the server. Otherwise, it is not valid and we should not send it. For the email field w'd like to make sure it is filled before submitting the form.
 We need a reference to the email field to check the length of its `value`. If it is zero, this means the user didn't provide the email and shouldn't submit this form.      
  {{< detailsumary title="Form Validation: Required Email" >}}
  ```js {linenos=table,linenostart=13}
function validate() {
// validate the email    
let email = document.register.email.value; // find the value of the email
    if (email.length == 0) {
        alert("invalid email");
        return false;
    }

  // validate the user name

// validate the promotion

  return true; // all validations passed successfully
}
  ```
   {{< /detailsumary >}} 
 ###  5. Validate that the username only contains alphanumeric characters and underscores
Following the same steps of validating the email, we can check the validity of the username. The problem here is to make sure
that only alphanumeric and underscores are used. Since the username can be in any form of combination of these characters,
this means using `regural expression` is one of the best ways to validate it. The following regular expression can be used to check for that `^[a-zA-Z0-9_]+$`. 
Following is the explanation of this regex:
- `^` asserts position at start of a line
- Match a single character present in the list below [a-zA-Z0-9_]
- `+` matches the previous token between **one** and **unlimited** times, as many times as possible, 
-  `a-z` matches a single character in the range between a (index 97) and z (index 122) (case sensitive)
-  `A-Z` matches a single character in the range between A (index 65) and Z (index 90) (case sensitive)
-  `0-9` matches a single character in the range between 0 (index 48) and 9 (index 57) (case sensitive)
-  `_` matches the character _ with index 95  literally (case sensitive)
-  `$` asserts position at the end of a line.

The `test` function checks if the string (`username.value` ) satisfies all of above conditions 
 {{< detailsumary title="function validate() continuation: username" >}}
 ```js {linenos=table,linenostart=21}
//validate the user name
     let username = document.register.username;
     let regex = /^[a-zA-Z0-9_]+$/;
     if (!regex.test(username.value)) {
         alert("invalid username");
         username.focus();
         return false;
     }

 ```
  {{< /detailsumary >}}
  
### 6. Remind the user to receive our promotion and respect his decision  
This is a soft validation, if the user choose not receive promotions, we remind him before submitting. If he accepts after the reminder we submit the form showing that he accepted.
And if he declines after the reminder we submit the form respecting his choice.
The `confirm` function presents the user the prompt. It returns `true` if the user clicks on `Ok` and `false` when he clicks on `Cancel` 

 {{< detailsumary title="function validate() continuation: promotion" >}}
 ```js {linenos=table,linenostart=30}
 // validate the promotion
let promoCheck = document.querySelector("#promo");
    if (!promoCheck.checked) {
        promoCheck.checked = confirm("If you don't want miss our promotion click ok");
    }
 ```
  {{< /detailsumary >}} 

## Exercises
### Suggested changes on the example
- Add regex validation for the email.
- Replace the `alert` calls by placing the error message beside the input field.
- Add a reset button and clear all the input fields when clicked.
### Validate the company hiring form
 {{< detailsumary title="Expand" >}}
 Validate the form give in [This Exercise](http://localhost:1313/swe-363.github.io/courses/swe363/html/advanced/#company-hiring-form).
 - All fields labeled with red star are required.
 - The date for **When can you start?** must be after the date of filling the form.
 - A maximum 200 characters comment. 
  {{< /detailsumary >}}