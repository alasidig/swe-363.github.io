---
title: "HTML Basics"
date: 2022-01-12T09:36:41+03:00
draft: false
summary: The basic tags in HTML.
weight: 3
tags: [html, front-end, semantic-tags]
toc: true  # Show table of contents? true/false
type: docs  # Do not modify.
menu:
  swe363:
    html:
      name: HTML Basics 
      weight: 3

---

## HTML 5 Semantic Tags
### Objective
 To learn the page structure  element elements in HTML5 and also to learn HTML5 Forms. 
### Some HTML 5 Semantic Tags

![HTML 5 semantic tags](https://www.codeproject.com/KB/HTML/semanticHtml5PageLayout/html5pagelayout.png)
These are some semantic structure elements. If you are viewing this page on laptop or any device with a biger screen, you can name these tags. 



 The `<header>` may be used at the top of the page. Then after that, you may have navigation ( `<nav>`)to the right and sometimes also the navigation is moved below the header. And at the bottom, we will have a `<footer>`. Which is going to list some links like contacts or useful links or sitemap. 
 
The `<main>` section holds the main content of the page. And it can be divided into `<sections>`. Each section will have its `<header>`, which contains a title for that section, and may have an `<article>` that contains the content of this section, and it also may have a `<footer>` to conclude this section. And then after that, you can have another `<section>` or so on. 

Before every HTML5, these tags were not there, and people were only using the `<div>` tag. then they either give it an `id` equal to main or they give it a `class` named main or something like that to distinguish from others. 

Alright, so now whenever we design our webpage, would like to have these tags. These tags will help the search engines to index our page well. When it finds something in the main it would say that this is the main topic of the page. And when it finds something in a section it's going to say that this section is about this topic.

### Semantic Tags in Action
The following video shows the usage of semantic tags in twitter website.
{{< youtube KSwtTPAyiu4 >}}

## Exercises
### Debug HTML
This simple web page has some issues which are preventing the content from being displayed correctly. Identify and fix the issues. This practice is also called "debugging" your code.
```html
<!DOCTYPE html>
  <html>
       <head>
       </head>
       <body>
             <p>This sentence should be on its own    So should this one.</p>
             <p. Whats wrong with this sentence? <p>   
        </body>  
  </html>
```
### Create a webpage
Given the following text:
```
My Hobbies
Soccer
5 years
Soccer is an awesome sport because you get to play on a team with all your friends. I love the challenge of learning new skills like headers and corner kicks.

Baking
10 years
I love baking because you put together all these things that look simple and boring on their own to make something magical and delicious. I also love how baked things make people happy. Sharing things I bake might be the best part of it!

Drawing
2 years
On the weekend sometimes I go outside and try to draw what I see. My favorite things to draw are buildings.
```


try to use your HTML skills to create a page that looks like the following
![html mini challenge](../html-mini-challenge01.png)

## More Resources
 - [ Document and website structure](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Document_and_website_structure)
 - [ Stop using so many divs! An intro to semantic HTML](https://dev.to/kenbellows/stop-using-so-many-divs-an-intro-to-semantic-html-3i9i)
