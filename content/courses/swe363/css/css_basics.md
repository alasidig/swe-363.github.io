---
title: "CSS Basics"
date: 2022-02-10T09:36:41+03:00
draft: false
summary: The basic CSS.
weight: 5
tags: [css, front-end]
toc: true  # Show table of contents? true/false
type: docs  # Do not modify.
menu:
  swe363:
    html:
      name: CSS Basics 
      weight: 3

---

## Objectives
Learn the basics of using CSS for styling websites.
## Introduction
In web development the rule of Cascade Style Sheets is to control how the contents are presented to the user. It is used to decide on the site layout, colors, fonts, animations, ... etc.

## Worked Example:
In this handout, we will create an interactive smiley face. The final output looks as follows. 
![The smiley face](../smileCrop.gif)
It is recommended that you write the code your self before expanding the given solution. Try to avoid coping and pasting.  

### HTML code
In the HTML body, we would like to start drawing this 😀.  We can have a `<div>` with the `class` `smiley`.
 And inside this div, we would like to have two other divs, one for each eye, and one for the mouth.
 Still, we can't see anything on the browser because these divs by default don't have any size unless you give them some content inside.

  {{< detailsumary title="Index.html" >}}

```html
 
<head>
    <link rel="stylesheet" href="style2.css">
    <title>Smile Please</title>
</head>
<body>
    <h1>Hover Over Me to Smile!!</h1>
    <div class="smiley">
        <div class="eyes" id="leftEye"></div>
        <div class="eyes" id="rightEye"></div>
        <!-- for entertainment add cheeks -->
        <div class="cheeks"></div>
        <div class="cheeks"></div>
        <div class="mouth"></div>
    </div>
</body>
```
  {{< /detailsumary >}}
### CSS Styling
 Now let's start the styling.  We would like firstly to style the smiley class. Firstly, to show it on the screen, we need to give it `height` and `width` since we don't have any content in this div. By default, it's going to take the full widht of the screen because it is a block element. Then, change the `background-color` to gold.
#### Styling the face

  {{< detailsumary title="smiley class CSS rules" >}}

```css
.smiley{
   
    height: 200px;
    width: 200px;
    /* let us give it some background-color: ; */
    background-color: gold; 
}

```
  {{< /detailsumary >}}
We would like to give it some space around it and move it away from the edge.
 To do that, we can use the `margin` property.
 The `margin` is the space around the element outside the `border` while the `padding` is space around the content. 

  {{< detailsumary title="smiley class CSS rules" >}}

```css
.smiley{
   
    height: 200px;
    width: 200px;
    /* let us give it some background-color: ; */
    background-color: gold;
    /* let us move it away from the edges */
    margin: 25%; 
}

```
  {{< /detailsumary >}}
We can also, add a `border` around the face. For the `border` property, you choose the color, style, and thickness. So let's add a `black` `solid` `2px` thick border.  but we are not limited to these named colors. Hovering over the word `‘black’` in VSCode will popup the color chooser utility to select any color. The color can be represented as a blend of red, green, and blue with different ratios. 
  {{< detailsumary title="smiley class CSS rules" >}}

```css
.smiley{
   
    height: 200px;
    width: 200px;
    /* let us give it some background-color: ; */
    background-color: gold;
    /* let us move it away from the edges */
    margin: 25%; 
    /* let us add border to the face. now let us use a different way to add colors border*/
    border: black solid 5px;
}

```
  {{< /detailsumary >}}
![vscode color chooser](../color_chooser.jpg)
So we gave it now a border, but the face doesn't look square right? So to change that we can use the `border-radius`.  The `border-radius` specifies how rounded the corner should be. we would like the face to be completely round. This means the border-radius should be at least half of the width `100px`. we can use relative units (`50%`) and let CSS handle the calculation

  {{< detailsumary title="smiley class CSS rules" >}}
```css
.smiley{
   
    height: 200px;
    width: 200px;
    /* let us give it some background-color: ; */
    background-color: gold;
    /* let us move it away from the edges */
    margin: 25%; 
    /* let us add border to the face. now let us use a different way to add colors border*/
    border: rgb(45, 45, 45) solid 5px;
    /* but the face shouldn't be a square */
    border-radius: 50%;
}

```
  {{< /detailsumary >}}

#### Styling the mouth
So inside the 😀 we are having eyes and a mouth. The mouth needs size and background color to show up. Let us add `height` and `width` and a black 10px thick `border`. 
  {{< detailsumary title="mouth class CSS rules" >}}
```css
.mouth{
    height: 50px;
    width: 75px;
    border-bottom: #2d2d2d solid 10px;
}

```
  {{< /detailsumary >}}
### Face Layout
OK, but this is not where the mouth should be. To move it to the right location, we can think of the face as a 5x5 `grid`. The mouth should be in the forth row and spanning three columns as in this figure:
![face grid](../face_grid.jpg)
The line marks the starting of the column or a row. to do that we can change the `display` property of the `.smiley` to `grid` and set the templates for rows and columns.
  {{< detailsumary title="smiley class CSS rules" >}}
```css
.smiley{
   
    height: 200px;
    width: 200px;
    /* let us give it some background-color: ; */
    background-color: gold;
    /* let us move it away from the edges */
    margin: 25%; 
    /* let us add border to the face. now let us use a different way to add colors border*/
    border: black solid 5px;

    display: grid;
    grid-template-columns: repeat(5,1fr);
    grid-template-rows: repeat(5,40px);
    place-items: center;
}

```
  {{< /detailsumary >}}

Whit that done, now we can style the mouth and move it to the correct place.
  {{< detailsumary title="mouth class CSS rules" >}}
```css
.mouth{
    height: 50px;
    width: 75px;
    border-bottom: #2d2d2d solid 10px;

    grid-row: 4;
    grid-column: 2/5;
}

```
  {{< /detailsumary >}}

  #### Styling the eyes
  Similarly, we can style the eyes. Since the two eyes share common style, we can add the common CSS properties to the `eyes` class and use the ids for the distinct styles
  {{< detailsumary title="eyes class CSS rules" >}}
```css
.eyes{
    width: 25px;
    height: 45px;
    background-color: #2d2d2d;
    /* make them oval */
    border-radius: 50%; 
}

```
  {{< /detailsumary >}}

  {{< detailsumary title="Right and left eye CSS rules" >}}
```css
#leftEye{
    grid-column: 2;
    grid-row: 2;
}
#rightEye{
    grid-column: 4;
    grid-row: 2;
}

```
  {{< /detailsumary >}}
#### Adding the cheeks
The cheeks style is similar ot the eyes. The differences are the color and the position. For the color, instead of a single solid color, a fancy gradient color is used. 
 {{< detailsumary title="cheeks class CSS rules" >}}
```css
.cheeks{
    width: 35px;
    height: 45px;
    background:radial-gradient(circle,red,pink);
    border-radius: 50%;
    opacity: 35%;
    grid-row: 3;
}

```
  {{< /detailsumary >}}
To move the right cheek to the right, we can select it using the pseudo class `nth-of-type`
  {{< detailsumary title="Right cheek CSS rules" >}}
```css
div.cheeks:nth-of-type(2n){
    grid-column: 5;
}
```
  {{< /detailsumary >}}
 
 ### Animation
 Let us now finally smile 😊. For this we use `hover` pseudo class. For the eyes, we would like to change their `width` and `height`.

 
  {{< detailsumary title="Smiling eyes CSS rules" >}}
```css
.smiley:hover .eyes{
    width: 45px;
    height: 25px;
}

```
  {{< /detailsumary >}}
  For the mouth, we would like to change the `width`, `height`, and `border-radius`.

 
  {{< detailsumary title="Smiling mouth CSS rules" >}}
```css
/* the mouth should expand and become rounded*/
.smiley:hover .mouth{
    width: 100px;
    height: 50px;
    border-radius: 50%;
}
```
  {{< /detailsumary >}}

The cheeks should be hidden and only be shown on hover. This can be done using the `opacity`. In the `.cheeks` class change the ```css opacity: 35%; ``` to ```css opacity: 0; ``` to hide the cheeks. 

  {{< detailsumary title="Smiling cheeks CSS rules" >}}
```css
.smiley:hover .cheeks{
    opacity: 35%;
}
```
  {{< /detailsumary >}}

Finally to have a smooth transition we can set the duration of state-change to 1 second. To do that, use the `transition` property. This should be added to eyes, cheeks, and mouth. Instead of repeating the same rule in different places, we can use the `*` selector to select all the children of `.smiley` div.   
  {{< detailsumary title="Smooth animation" >}}
```css
.smiley >*{
    transition: 1s ;
}
```
  {{< /detailsumary >}}
## Exercises
### Suggested changes on the example
- Add different animations like 😂 or 🤣 ro 🤩
- Replace the `grid-template-columns` by `grid-template-areas`
- Replace the `grid` by `flex`
- Re-implement using `position` instead of `grid` 
### Webpages styling

 #### Deserts of the world
  {{< detailsumary title="Expand" >}}
Fork the repl on the following link [https://replit.com/@alasidig/cssimages#index.html](https://replit.com/@alasidig/cssimages#index.html) then follow the comments on the style.css to make the page looks like the following image


![table_form.gif](../output.png)
  {{< /detailsumary  >}} 

 #### URL Shortener
  {{< detailsumary title="Expand" >}}
Fork the following repository [https://github.com/alasidig/url-shortener](https://github.com/alasidig/url-shortener) then following the style guide in style-guide.md, start styling the page until it looks like the image in the design/desktop-active-states.jpg.

  {{< /detailsumary  >}} 
