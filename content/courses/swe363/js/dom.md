---
title: "DOM Manipulation"
date: 2022-02-20T16:35:53+03:00
draft: false
summary: Manipulating the Document Object Model in JavaScript.
weight: 7
tags: [JS, JS DOM, JS Events, front-end]
toc: true  # Show table of contents? true/false
type: docs  # Do not modify.
menu:
  swe363:
    js:
      name: JS Events 
      weight: 3

---

## Objectives
Learn the basics of using JavaScript for modifying the HTML and CSS and responding to different events that may happen on a web page.
## Introduction
JavaScript describes the HTML structure in a tree-like object called the Document Object Model. It provides many functions to: select element\s on the HTML, create new element\s, style elements, ... etc. 
## Worked Example
In this handout, we will use JavaScript to create a quiz-taking webapp. The final behavior looks as follows. 
{{< youtube FzsKSFoMZ3M >}}
1. The user clicks on the `Start` button to see the questions
2. Show a random question.
3. Change the background to reflect the correctness then disable the choices buttons.
4. Show the `Next` button if there are more questions else show the score.

### HTML Code
 {{< detailsumary title="Quiz App HTML" >}}
 ```html {linenos=table,hl_lines=[8,"15-17", 20],linenostart=1}
 <!DOCTYPE html>
 <html lang="en">
 
 <head>
     <meta charset="UTF-8">
     <meta name="viewport" content="width=device-width, initial-scale=1.0">
     <title>Exploring Dom</title>
     <link rel="stylesheet" href="style.css">
 </head>
 
 <body>
     <div class="container">
         <h1 name="scoreMessage"></h1>
         <div class="question-card hide">
             <h1 id="question">What is 5+2</h1>
             <div id="answers">
                 <div>
                     <button class="btn ">10</button>
                     <button class="btn">12</button>
                     <button data-correct="true" class="btn">7</button>
                     <button class="btn">6</button>
                 </div>
             </div>
         </div>
         <button id="start" onclick="start()" class="btn">Start</button>
         <button id="next" class="btn hide" onclick="goNext()">Next</button>
     </div>
     <script src="app.js"></script>
 </body>
 
 </html>
 ```
  {{< /detailsumary >}}
In line 15 the `<h1>` is used to display the question text. And the answers are wrapped in a `div` inside the one with id=answers.
The `data-correct` attribute is added to the button that holds the correct answer.
### CSS Style
 {{< detailsumary title="Quiz App CSS rules" >}}
 ```css {linenos=table,hl_lines=[31,59,62],linenostart=1}
 body{
     margin: 0;
     padding: 0%;
     height: 100vh;
     background:rgb(17, 17, 53) linear-gradient(to bottom right,rgb(17, 17, 53),rgb(67, 189, 67));
     display: flex;
     justify-content: center;
     align-items: center;
     font-size: 62.5%;
     box-sizing: border-box;
 }
 .container{
     display: flex;
     background-color: white;
     padding: 2rem;
     border-radius: 1rem;
     flex-direction: column;
     align-items: center;
     justify-content: center;
     justify-items: center;
    
 }
 .question-card{
     display: flex;
     flex-direction: column;
     box-shadow: 0 0 1rem .5rem ;
     padding: 2rem;
     border-radius: 1rem;
     margin-bottom: 1rem;
 }
 .hide{
     display: none;
 }
 
 .btn{
     font-size: 2rem;
     border-radius: 1rem;
     color: white;
     border: transparent;
     background-color: rgb(197, 168, 1);
     padding: .5rem;
     margin: .2rem;
     cursor: pointer;
 }
 .btn:hover{
     transform: scaleX(1.2);
     box-shadow: 0 0 .5rem .25rem;
 }
 h1{
     font-size: 2.5rem;
 }
 #answers div{
     display: flex;
     flex-direction: column;
     justify-content: space-between;
 
 }
 
 .correct{
     background-color: rgb(27, 133, 141);
 }
 .incorrect{
     background-color: rgb(197, 74, 74);
 }
 ```
  {{< /detailsumary >}}
  The class `.hide` is used to hide the elements. It will be added and removed using Javascript to hide the `next` button until the user chooses an answer.
  The classes `.correct and .incorrect` are used to reflect the correctness of the chosen answer. 
  ### JavaScript Skeleton
   {{< detailsumary title="The JavaScript Skeleton" >}}
   ```js {linenos=table,linenostart=1}
   /* find the elements  */
   
   /* start button*/
   // const startBtn =
   /* the element that has the question-card class*/
   // const cardEle =
   
   /* the question title*/
   // const qTitleEle =
   /* the element with the id of answers*/
   // const choicesEle =
   /* the next button*/
   // const nextBtn =
   
   let currentQuestion, qIndex, score = 0, points = 10, maxPoints;
   
   /* function called when clicking on the start button*/
   function start() {
       /* show the questions card cardEle*/
   
       /* hide the start button*/
   
       /* set the maximum points a user can get for solving all the questions*/
       // maxPoints =
       console.log('start function called');
       createQuestion();
   }
   
   function createQuestion() {
       console.log('Creating question');
       /* randomly select a question from the questions array*/
       /* qIndex is the index of the question in the array*/
       // qIndex =
       // currentQuestion = questions[qIndex]
   
       // qTitleEle  /* fill the question title */
   
       /* remove the div that wraps all the answer buttons*/
       // choicesEle 
   
       /* create a new div to wrap the choices*/
       // let wrapper =
       /* add all the choices to this wrapper*/
       // currentQuestion.choices.forEach(choice => {
       //     wrapper.appendChild(createChoice(choice))
       // });
       /* add the wrapper to the choicesEle*/
       // choicesEle
       /* remove the selected question from the questions array so that it will not be shown again*/
       // questions
   }
   
   /* function to create a button for each choice*/
   function createChoice(choice) {
       console.log('creating choice', choice);
       /* create a button element*/
       // let element =
       // element.classList.add("btn")
       // element.innerText = choice.choice;
       /* create a data-correct attribute for the correct answer button*/
       // if (choice.correct) {
       //     element.dataset["correct"] = true
       // }
       /* add click event handler.*/
       // element.addEventListener('click', answer)
       // return element;
   }
   /* function to handle the click on an answer button*/
   function answer(event) {
       const src = event.srcElement
       console.log('user choose ', src);
       if (src.dataset["correct"]) {
           /* add the 'correct' CSS class to both the button and the cardEle*/
           // src
           // cardEle
           /* update the user score*/
           // score
       } else {
           /* add the 'incorrect' CSS class to both the button and the cardEle*/
   
           // src
           // cardEle
       }
       proceed();
   }
   /* function called after the click of an answer button*/
   function proceed() {
       /* disable the buttons so the user can't change his answer*/
       disableChoices();
       /* then show the next button to move to next question*/
       setTimeout(showNext, 1000);
   }
   
   /* function to disable the choices buttons*/
   function disableChoices() {
       console.log('disabling the choices');
       /* find all choices buttons*/
       const choicesBtns = document.querySelectorAll("button:not(.hide)");
       choicesBtns.forEach(btn => {
           /* remove the click event handler so the button does nothing when clicked*/
           // btn
       });
   }
   
   /* function to show the next button*/
   function showNext() {
       console.log('Show next button');
       /* remove the 'correct' and the 'incorrect' classes from the cardEle*/
       // cardEle
       // cardEle
       if (questions.length > 0) {
           /* remove the hide class from the nextBtn*/
           // nextBtn
       }
       else {
           /* show the score*/
           //  = `Done! your score is ${score} / ${maxPoints}`
       }
   }
   
   /* function called when clicking on next button*/
   function goNext() {
       /* hide the next button*/
       nextBtn.classList.add("hide")
       /* create a new question*/
       createQuestion();
   }
   const questions = [
       {
           text: "What is 2 + 2",
           choices: [
               {
                   choice: 4, correct: true
               },
               {
                   choice: 3
               },
               {
                   choice: 0
               },
   
           ]
       },
       {
           text: "What is 2 x 2",
           choices: [
               {
                   choice: 4, correct: true
               },
   
               {
                   choice: 6
               },
               {
                   choice: 3
               },
               {
                   choice: 0
               },
   
           ]
       },
       {
           text: "What is 2 - 2",
           choices: [
               {
                   choice: 0, correct: true
               },
   
               {
                   choice: 6
               },
               {
                   choice: 3
               },
               {
                   choice: 4
               },
   
           ]
       },
   ]
   ```
    {{< /detailsumary >}}
   The file contains two types of comments: the `/* */` comment for the step to be done, and the `//` for partially complete code for us to complete.
    For example, in line 3 `/* start button*/` asking us to find a reference to the start button, while on line 4 `// const startBtn =` we should uncomment it to complete the task.
    
   ### Finding the HTML elements in JS
   To find the different required elements, we can use any of the DOM query methods. The query is based on the attributes of those HTML elements like `id, class`. 
   For demonstration, we will use different DOM query methods.
{{< detailsumary title="Querying the DOM" >}}
   ```js {linenos=table,linenostart=1}
    /* find the elements */
    
    /* start button*/
    const startBtn = document.getElementById("start");
    /* the element that has the question-card class*/
    const cardEle = document.getElementsByClassName("question-card")[0]
    
    /* the question title*/
    const qTitleEle = document.getElementById("question")
    /* the element with the id of answers*/
    const choicesEle = document.querySelector("#answers")
    /* the next button*/
    const nextBtn = document.querySelector("#next")
    
    let currentQuestion, qIndex, score = 0, points = 10, maxPoints;

   ```
{{< /detailsumary >}} 
### Implementing the `start` function

When the user clicks on the start button, The question's card should be shown and the start button should be hidden.
 {{< detailsumary title="start() function" >}}
 ```js {linenos=table,linenostart=17}
 /* function called when clicking on the start button*/
 function start() {
     /* show the questions card cardEle*/
     cardEle.classList.remove('hide')
     /* hide the start button*/
     startBtn.classList.add("hide")
     /* set the maximum points a user can get for solving all the questions*/
     maxPoints = points * questions.length
     console.log('start function called');
     createQuestion();
 }
 ```
  {{< /detailsumary >}}
 To hide an element we just add the `hide` class to that element. This is done by calling the `add` method on the `classList` property of the element.
### Implementing `createQuestion` function
  {{< detailsumary title="createQuestion function" >}}
  ```js {linenos=table,hl_lines=["16-18"],linenostart=29}
  function createQuestion() {
      console.log('Creating question');
      /* randomly select a question from the questions array*/
      /* qIndex is the index of the question in the array*/
      qIndex = Math.floor(Math.random() * questions.length)
      currentQuestion = questions[qIndex]
  
      qTitleEle.innerText = currentQuestion.text  /* fill the question title*/
  
      /* remove the div that wraps all the answer buttons*/
      // choicesEle 
      choicesEle.removeChild(choicesEle.firstElementChild);
      /* create a new div to wrap the choices*/
      let wrapper = document.createElement("div")
      /* add all the choices to this wrapper*/
      currentQuestion.choices.forEach(choice => {
          wrapper.appendChild(createChoice(choice))
      });
      /* add the wrapper to the choicesEle*/
      choicesEle.appendChild(wrapper);
      /* remove the selected question from the questions array so that it will not be shown again*/
      questions.splice(qIndex, 1)
  }
  ```
   {{< /detailsumary >}}
   1. The function starts by finding a random index of a question from the `questions` array. `Math.random` 
generates a random number in the range `[0-1)`.
   To convert this number to the range `[0~length-1]`, multiply it by the length of the array.
   1. Then set the question title element (`h1`) content to the text of the random question.
   1. Then it removes the old questions choices by deleting the `div` that wraps them. And recreate a wrapper `div` to hold the new question choices.
   1. Then it iterates over the new question choices to create a button for each choice and add it to the wrapper. 
   The code now is broken because we didn't implement the `createChoce` function.
   1. Then add the wrapper to the DOM to replace the old one.
   1. Finally, to remove the randomly chosen question from the array, it uses `splice(startIndex, count)` array function. This means each time this function is called, the array length is decremented.
   When it becomes empty the application should stop.
 ### Implementing `createChoice` function
  {{< detailsumary title="createChoice function" >}}
   ```js {linenos=table,linenostart=53}
    /* function to create a button for each choice*/
    function createChoice(choice) {
        console.log('creating choice', choice);
        /* create a button element*/
        let element = document.createElement("button");
        element.classList.add("btn")
        element.innerText = choice.choice;
        /* create a data-correct attribute for the correct answer button*/
        if (choice.correct) {
            element.dataset["correct"] = true
        }
        /* add click event handler.*/
        element.addEventListener('click', answer)
        return element;
    }
   ```
   {{< /detailsumary >}}
 1. The function creates a button and sets its content to the choice text value. 
 1. Then conditionally add the `data-correct` attribute to the button if it is the correct answer.
 1. Then it sets the click event handler to be the `answer` function. And returns the button to `createQuestion`
 
 ### Implementing the `answer` function
 {{< detailsumary title="answer function" >}}
  ```js {linenos=table,linenostart=68}
  /* function to handle the click on an answer button*/
  function answer(event) {
      const src = event.target
      console.log('user choose ', src);
      if (src.dataset["correct"]) {
          /* add the 'correct' CSS class to both the button and the cardEle*/
          src.classList.add("correct")
          cardEle.classList.add("correct")
          /* update the user score*/
          score += points;
      } else {
          /* add the 'incorrect' css class to both the button and the cardEle*/
  
          src.classList.add("incorrect")
          cardEle.classList.add("incorrect")
      }
      proceed();
  }

  ```
 {{< /detailsumary >}}
 1. The function finds which button did the user choose by finding the `target` property of the event.
 1. Then it either adds `correct` or `incorrect` class to both the button and the question card. If the event source contains `data-correct` attribute, it means the user chooses the correct answer.
 1. It also updates the user score by adding the points for a correct answer.
 1. Then it calls `proceed` function which calls `disableChoices` to prevent the user from changing his answer and `showNex` function to show the `Next` button.
 
 ### Implementing `disableChoces` function
  {{< detailsumary title="disableChoices" >}}
  ```js {linenos=table,linenostart=94}
  /* function to disable the choices buttons*/
  function disableChoices() {
      console.log('disabling the choices');
      /* find all choices buttons*/
      const choicesBtns = document.querySelectorAll("button:not(.hide)");
      choicesBtns.forEach(btn => {
          /* remove the click event handler so the button does nothing when clicked*/
          btn.removeEventListener('click', answer);
      });
  }
  ```
   {{< /detailsumary >}}
 1. The function finds all the buttons except the hidden ones (Start and Next)
 1. Then it loops over these buttons to remove the click event handler. When the user clicks on any of the choices the `answer` function is not called
### Implementing `showNext` function

 {{< detailsumary title="showNext Function" >}}
 ```js {linenos=table,linenostart=105}
 /* function to show the next button*/
 function showNext() {
     console.log('Show next button');
     /* remove the 'correct' and the 'incorrect' classes from the cardEle*/
     cardEle.classList.remove("incorrect")
     cardEle.classList.remove("correct")
     if (questions.length > 0) {
         /* remove the hide class from the nextBtn*/
         nextBtn.classList.remove("hide");
     }
     else {
         /* show the score*/
         document.getElementsByName("scoreMessage")[0].innerText = `Done! your score is ${score} / ${maxPoints}`
     }
 }
 ```
  {{< /detailsumary >}}
  1. The function removes the animation of correct or incorrect answers
  1. Then it checks if there are some questions left in the array. As we show in `createQuestion` the function removes the randomly chosen question.
  1. If there are some questions left, it shows the `Next` button to enable the user to move to the next question.
  1. If there are no questions left, it shows the score message.
  

## Exercises
### Suggested changes on the example
- Randomize the answers
- Add a timer for each question.
- Create different types of questions: multiple answer, fill in the blank use regular expressions to check the user answer.

