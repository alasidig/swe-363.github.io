---
title: "HTML Advanced"
date: 2022-01-12T09:36:41+03:00
draft: false
summary: Some advanced tags in HTML like forms and tables.
weight: 4
tags: [html, front-end, form-fields]
toc: true  # Show table of contents? true/false
type: docs  # Do not modify.
menu:
  swe363:
    html:
      name: HTML Advanced 
      weight: 3
---
## Objectives:
How we can write an HTML form and what is the rule of HTML forms
## Introduction
Forms provide the user with a way to interact with a web server. An interactive website allows users to input data using forms. Forms are frontend to backend data transformers.

 For example, if we are going to design a website for fast food. The front end should show some images of the meals. And also the user should be able to click somewhere on the page to add to the shopping cart. And when checking out, he should be able to set his address to deliver the food in a form. So all that should be done on the front end. But we also need to pass data from the front end to the back end so that the admin of this restaurant to be able to serve this customer. The admin will have another view which talks to the database and tell the admin that some person here is ordering a meal and he would like to get it in that address.

![Form sent to the server](https://www.javascript-coder.com/html-form/images/server-side-script-part.png "The frontend enables the user to enter the data and submit it to the backend")
Forms usually include a series of HTML `<input>` tags. There are many other tags, but input is the most used. Before HTML 5 there was a limited number of data entry controls that are available. In HTML  5 there are controls for entering text, choosing from a list of buttons and checkboxes, radio buttons ..etc.  HTML 5 also added more new controls that we can use to customize options for existing controls.

## Worked Example
Let's create a simple form that asks the user for a feedback. The required fields includes his name, phone, and a message.
{{< gdocs src="https://replit.com/@alasidig/forms?lite=true" >}}  
The form starts from line 10 where we added the `<form>` tag. Then followed by an `<input>` tag for the user name, then another one for the phone, and finally a `<textarea>` to hold the message. The `<ul>` and `<li>` tags are used to format the fields to show in a vertical column because the `<input>` and `<textarea>` are `inline` elements. Click on the green button to see the output.
### The `<input>` field
```html
        <input type="text" name="user" placeholder="Enter your name" required>
```
- It is a self closing tag
- The `type` attribute can have many values like number, email, password, ...etc. It is helpful for simple validation and will render a sutable keyboard on the smartphones.
- The `placeholder` attribute is used to display a helping string to the the user what should he input in this field. 
- The `required` attribute is used to force the user to fill the field before submission.
- The `name` attribute is used to communicate the entered values to the server. When submitting this form, a dictionary of keys and values will be created. The keys are what is being assigned to the `name` attribute. And the values are the user response for each field. Try to change the `name` attribute for the first `<input>` to user2 and see the result.
- Setting the `type` to submit will create a button to submit the form and enable submitting the form by just pressing the enter key on the keyboard.
- There are many other attributes not added here such as `value`, `onkeyup`, ...

### The `<textarea>` field
- It is used to enable the user to enter more than one line of text.
- There are some other attributes not added here such as `rows`, `cols`,...
### The `<form>` tag
```html
<form action="result.html" method="get">
  ```
  - It wraps the input fields.
  - The `action` attribute tels where to submit the form. It accept the URL of the server that will process the form data. Since we are only discussing the frontend now, the server side script will not be discussed.
  - There are many other attributes not added here such as `onsubmit`, `enctype`, ... 
  - The `method` attribute determines  how to submit the form. It can be set to `get` or `post`. There are some differences between the two methods as shown in the following video
  {{< youtube Vk2Rm6tthz8 >}}
  ## Exercises
  ### Company hiring form
  {{< detailsumary title="Expand" >}}
Create a web page for a company of your choice it should contain some description, products, images, and a large title: **We are hiring join us by filling this application.** the title should link to a page that contains the following form:
![job_form.png](../jop_form.png)

  {{< /detailsumary >}}

  ### Restaurant Table Reservation
  {{< detailsumary title="Expand" >}}
create a web page for a restaurant. it should contain an image and a list of meals with some description. it should contain a link to another page that contains a form to reserve a table like the following.


![table_form.gif](../table_form.gif)
  {{< /detailsumary  >}} 
## More Resources

- {{< staticref "https://developer.mozilla.org/en-US/docs/Learn/Forms/Your_first_form" "newtab" >}}
Your first form
{{< /staticref >}}
- {{< staticref "https://developer.mozilla.org/en-US/docs/Learn/Forms/Basic_native_form_controls" "newtab" >}}
Basic native form controls
{{< /staticref >}}
- {{< staticref "https://developer.mozilla.org/en-US/docs/Learn/Forms/HTML5_input_types" "newtab" >}}
The HTML5 input types
{{< /staticref >}}
- {{< staticref "https://webaim.org/techniques/forms/controls" "newtab" >}}
Creating Accessible Forms
{{< /staticref >}}


