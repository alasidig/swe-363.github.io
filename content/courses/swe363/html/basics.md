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
{{< detailsumary title="Expand" >}}
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
{{< /detailsumary  >}}
### Create a webpage
{{< detailsumary title="Expand" >}}
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

{{< /detailsumary >}}

### HTML 5 Webpage
{{< detailsumary title="Expand" >}}
Given the text:


```
Easy 5-Minute Banana Smoothie Easy 5-Minute Banana Smoothie
 PREP 5mins TOTAL 5mins 
 Our banana smoothie is extra creamy and fruity. Depending on how ripe or sweet your banana and orange are, you may need to add a little extra honey, so add based on your taste. There are many additions you can make. 
 For a green smoothie, add 1/2 cup to 1 cup of fresh greens like spinach or kale. 
 You can also add more fruit. Add 1/2 cup of strawberries, mango, frozen berries, pineapple, or other favorite fruit. 
 Makes 2 kid-size smoothies or 1 large You Will Need 1 banana 1/2 orange, peeled and quartered 1/3 cup Greek yogurt 1/4 cup water or milk (dairy or non-dairy) 1 to 2 teaspoons honey, optional Directions Roughly chop the banana and orange quarters, and then add to a blender. 
 Top with yogurt and water (or milk). 
 Turn blender on and blend until creamy and smooth.
 Taste, and then adjust with honey if needed. 
 Adam and Joanne's Tips How to Freeze or Make Ahead: This recipe makes one smoothie or two kid-size smoothies. 
 Enjoy now, or save for later. To save the smoothie for later, pour each serving into a food-safe resealable plastic bag or container and freeze. Then, about an hour before needing the smoothie, take it out from the freezer. 
 Non-Dairy alternatives: If you are looking for a banana smoothie without yogurt, then simply leave the yogurt out of the recipe above and replace it with more banana, a tablespoon or so of nut butter, mango, or a tablespoon of hemp seeds (great protein source). You may need to add additional water or non-dairy milk to thin the smoothie out a little. 
 Nutrition facts: The nutrition facts provided below are estimates.
  We have used the USDA database to calculate approximate values. 
  If you make this recipe, snap a photo and hashtag it #inspiredtaste — We love to see your creations on Instagram and Facebook! Find us: @inspiredtaste 
  NUTRITION PER SERVING: 
  Serving Size 1 kid-size smoothie / Calories 122 / Protein 5 g / Carbohydrate 23 g / Dietary Fiber 3 g / Total Sugars 16 g / Total Fat 2 g / Saturated Fat 1 g / Cholesterol 5 mg 
  AUTHOR: Adam and Joanne Gallagher The full recipe post can be found on Inspired Taste here: https://www.inspiredtaste.net/19907/simple-banana-smoothie-recipe/
```

and the image at 
```
https://www.inspiredtaste.net/wp-content/uploads/2016/06/Banana-Smoothie-Recipe-3-1200.jpg
```

Use your HTML 5 skills to create a page like the following

![recipe minichallenge](../recipe-minichallenge.png)

{{< /detailsumary  >}}


## More Resources
 - [ Document and website structure](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Document_and_website_structure)
 - [ Stop using so many divs! An intro to semantic HTML](https://dev.to/kenbellows/stop-using-so-many-divs-an-intro-to-semantic-html-3i9i)
