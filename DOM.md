## DOM (Document Object Model)
### General
***Note by the Lecturer,***  
Also, as you begin working with the DOM you'll be writing some JavaScript code that selects HTML elements from the page and manipulates them.  

When doing this, be sure to include your JavaScript code at the bottom of the HTML document, right before the closing `</body>` tag.

The HTML will need to have loaded before the JavaScript is run, otherwise the JavaScript will throw an error because the HTML that it is trying to select and manipulate doesn't exist (yet).

See example below:
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Test</title>
</head>
<body>
    <h1>Some HTML Code Here</h1>

    <script src="scriptfile.js"></script>
</body>
</html>
```

- Here finally JS meets HTML+CSS

- The webiste https://www.patatap.com/ actually sums up this interaction. It changes the HTML and CSS as we push buttons in other word every time we interact with the page, JS adds or removes HTML/CSS to/from the page.

- DOM stands for *Document Object Model*. It is the interface between our JavaScript and HTML+CSS. So it is basically JS objects, JS methods that we can use to interact with our HTML & CSS.

- The browser turns every HTML tag into a JavaScript object that we can manipulate. Each object models one of the elements on the page like body, head, title etc. And all these objects are created under the `document`.

- When we type `document` to the console, it doesn't give us the objects as we explained above. To get them as we mentioned, we can type,
  ```bash
  console.dir(document)
  ```
  So actually this will show things to us like the code we used while handling objects...

- We can summarize the process with two keywords: ***SELECT*** and ***MANIPULATE***,  
  The following code changes the `h1` on the page to pink,
  ```javascript
  // Select the 'h1' on the page and save it to a variable 
  var h1 = document.querySelector("h1");
  // Then change it to color pink
  h1.style.color = "pink";
  ```
  The following code blinks the body between blue and white every second,
  ```javascript
  var body = document.querySelector("body"); //SELECT
  var isBlue = false;
  setInterval(function(){ //MANIPULATE
    if(isBlue){
      body.style.background = "white";
    } else {
      else body.style.background = "blue";
    }
    isBlue = !isBlue;
  }, 1000);
  ```
***

### Important DOM Selectors
1. `document.URL`  
  returns the URL of the page
1. `document.links`  
  returns all the links (all the anchor 'a href...' tags) that exist on the page
1. `document.body`  
  returns all the body
1. `document.head`  
  returns the head
***

### Methods
The document comes with a bunch of methods for selecting elements. Here are 5 of them,
```html
<body>
  <h1>Hello</h1>
  <h1>Goodbye</h1>
  <ul>
    <li id="highlight">List Item 1</li>
    <li class="bolded">List Item 2</li>
    <li class="bolded">List Item 3</li>
  </ul>
</body>
```
1. `document.getElementById("idOfTheElement")`  
    returns/Selects the specified element,
    ```javascript
    var tag = document.getElementById("idOfTheElement")
    tag //<li id="highlight">List Item 1</li>
    ```

1. `document.getElementsByClassName("className")`  
    returns/Selects all the elements with the given class name as a 'node list' which technically seems like an array. Even if there is a single element matching the tag name it will go into a node list,
    ```javascript
    var tags = document.getElementsByClassName("className")
    tags //[<li class="bolded">List Item 2</li>, <li class="bolded">List Item 3</li>]
    ```
    Regarding the differences between this (node list) and an array, we can use accessing (`tags[2]`) or length (`tags.length`) properties with both of'em but we cannot use `.forEach()` loop on a node list.

1. `document.getElementsByTagName("tagName")`  
    returns/Selects the items by the given tag name. Even if there is a single element matching the tag name it will go into a node list,
    ```javascript
    var tags = document.getElementsByTagName("h1")
    tags //[<h1>Hello</h1>, <h1>Goodbye</h1>]
    ```

1. `document.querySelector("key")`  
    returns the element that is specified by the selecting keyword. This method makes our work easier and lets us to select different things by just using a single method (itself). It is actually a CSS selector and works that way. On the other hand, if there is more than one element matching the class or tag key, it always just selects and returns the very first one as a single item!  
    If we specify it with a `#` then we mean the id,
    ```javascript
    var el = document.querySelector("#highlight")
    el //<li id="highlight">List Item 1</li>
    ```
    If we specify it with a '.' then we mean the class, and it selects the very first item of that class,
    ```javascript
    var el = document.querySelector(".bolded")
    el //<li class="bolded">List Item 2</li>
    ```
    If we don't specify the key, we mean the tag,
    ```javascript
    var el = document.querySelector("h1")
    el //<h1>Hello</h1>
    ```
    Furthermore, I can specify more complex key,
    ```javascript
    var el = document.querySelector("li a.special")
    ```

1. `document.querySelectorAll("key")`  
    works with the same principle as `querySelector()` but the very only different is this method selects all the elements matching the key and stores in a node list,
    ```javascript
    var tags = document.querySelectorAll(".bolded")
    tags //[<li class="bolded">List Item 2</li>, <li class="bolded">List Item 3</li>]
    ```
    If there is a single element matching the key it will again store it in a node list,
    ```javascript
    var tags = document.querySelectorAll("#highlight")
    tags //[<li id="highlight">List Item 1</li>]
    ```

> ***PS:** We can print the selected objects with the console method
  `console.dir(obj)`*
***

### Manipulating
1. `style`  
    The style property is one way to manipulate an element's style. The right side has to be a string, within the quotes,
    ```javascript
    var tag = document.getElementById("highlight");
    tag.style.color = "blue";
    tag.style.border = "10px solid red";
    tag.style.fontSize = "70px";
    tag.style.background = "yellow";
    tag.style.marginTop = "200px";
    ```

    If we try to change lots of properties for an object like above, we have to kepp the following concept called as ***Seperation of Concepts*** into consideration. It is recommended for styles to be defined in a seperate file or files. So it's better we use the style property for quick styling and testing purposes,
    ```
    -----------------
    |               |
    | structure  ---|---------------
    |   (html)   |  |              |
    |  ----------|--|--- behavior  |
    |  |         |  |  |   (js)    |
    |  |         ---|--|------------
    ---|-------------  |
       | presentation  |
       |     (css)     |
       -----------------
    ```

    So in terms of the schema above, instead of changing CSS elements by JS every time, we can turn them on and off inside of a CSS file which prevents us from *DRY-Coding* and preserves the principle schema above. We can create a class in the CSS file and then just changes the class of the wanted object to that class with JS and all the styling is again done but by preserving the principles and keeping the code clean,
    ```javascript
    // Selecting the element,
    var tag = document.getElementById("highlight");
    // Defining the class seperately in the CSS file,
    .some-class {
      tag.style.color = "blue";
      tag.style.border = "10px solid red";
      tag.style.fontSize = "70px";
      tag.style.background = "yellow";
      tag.style.marginTop = "200px";
    }
    // Add the new class to the selected element,
    tag.classList.add("some-class");
    ```

2. `classList`  
    A list that contains the classes for a given element. It is not an array,
    ```javascript
    var tag = document.querySelector("h1");
    tag.classList //returns the list of classes of the object
    // Add a class to the selected element,
    tag.classList.add("another-class");
    // Remove a class,
    tag.classList.remove("another-class");
    // Toggle a class,
    tag.classList.toggle("another-class");
    ```

    `toggle` adds the class to the object and returns `true` if it doesn't have it. Or it deletes it and returns `false` if it has that class. It is a very useful method,
    ```javascript
    tag.classList.toggle("another-class"); //true or false
    ```

3. `textContent`  
  We can show/change the content of a text with textContent, but it's a little bit dangerous in terms of keeping the 'strong' or 'em' or any tags inside of an element because it just returns the pure text inside of an element and directly overwrites what we type and it treats our input as a pure text even we include some tags. So if there is any tag inside of an element we don't want to directly overwrite its content... Here we have the following tag on number 4 which keeps those inner tags!
    ```html
    <h1>My World</h1>
    <p>This is an <strong>awesome</strong> paragraph.</p>
    ```
    ```bash
    My World
    This is an awesome paragraph.
    ```
    ```javascript
    var tag = document.querySelector("p");
    // Retrieve the text content,
    tag.textContent //"This is an awesome paragraph"
    // Alter the text content,
    tag.textContent = "New <em>content</em>...";
    // Following style is widely used,
    document.querySelector("h1").textContent = "My World, My Rules";
    ```
    ```html
    My World, My Rules
    New <em>content</em>...
    ```
    ```javascript
    // Following selection selects all the strings on a webpage,
    document.querySelector("body").textContent;
    ```

4. `innerHTML`  
  This is the property preserves the inner tags while showing and manipulating the content. So if we include some tags in our input it will render them (treat them as tags) and will manipulate accordingly,
    ```html
    <ul>
      <li>Cat</li>
      <li>Dog</li>
    </ul>
    ```
    ```html
      .Cat
      .Dog
    ```
    ```javascript
    var ul = document.getElementsByTagName("ul")[0];
    // Retrieve the all content,
    ul.innerHTML //"<li>Cat</li> <li>Dog</li>"
    // Alter the content with tags,
    ul.innerHTML //"<li>Bird</li> <li>Bear</li>"
    ```
    ```html
      .Bird
      .Bear
    ```

5. `getAttribute("atrName") - setAttribute("atrName", "newValue")`  
    We can use these to read or change/write attributes like 'src' or 'href' etc.
    ```html
    <a href="https://www.google.com">I take you to Google</a>
    <img src="logo.png">
    ```
    ```javascript
    var link = document.querySelector("a");
    link.getAttribute("href"); //"https://www.google.com"
    // Change 'href' attribute,
    link.setAttribute("href", "https://www.twitter.com");
    link.textContent = "Now I take you to Twitter";
    var img = document.querySelector("img");
    // Change 'src' attribute
    img.setAttribute("src", "corgi.png");
    ```
    ```html
    <a href="https://www.twitter.com">I take you to Twitter</a>
    <img src="corgi.png">
    ```

6. `value`  
    We use this property to get the value of an input form. It takes it as string,
    ```javascript
    defaultMaxScoreStr = document.querySelector("#score").value;
    ```
    To turn it into number we use `Number()` method,
    ```javascript
    defaultMaxScore = Number(document.querySelector("#score").value);
    ```


- ***Ex:*** **Playing With Google:** Along with manipulating the objects one by one here we will also change them by using loops and iterating over them,
  ```javascript
  // Selecting the Google logo,
  var logo = document.querySelector("#hplogo");
  // Changing the logo by atr 'srcset'
  logo.setAttribute("srcset", "https://brandingbycontext.com/images/nice-logo-portfolio/jack-oneill-logo-designer.jpg")
  // Setting the 'padding-top' atr to zero,
  logo.style = "padding-top: 0px";
  // Setting the height and width to 210px,
  logo.style.height = "190px";
  logo.style.width = "190px";
  // Applying a border,
  logo.style.border = "2px solid red";
  // Selecting all links on the page,
  var links = document.getElementsByTagName("a");
  // Iterating over them and changing some styling,
  for(i = 0; i < links.length; i++){
    links[i].style = "border: 2px dashed blue; color: red";
    links[i].style.background = "yellow";
    links[i].setAttribute("href", "https://www.bing.com")
  }
  ```
  <img src="https://i.ibb.co/xmNtLgm/Google-Manipulated.jpg">

# ADVANCED DOM
- We select an element and then add an event listener,
  - Listen for a click on this `<button>`
  - Listen for a hover event on the `<h1>`
  - Listen for a keypress event on text input

- `element.addEventListener(type, functionToCall);`  
    To add a listener we use the method above,
    ```javascript
    var button = document.querySelector("button");
    var paragrapgh = document.querySelector("p");
    button.addEventListener("click", function(){
      paragraph.textContent("The button is clicked!")
    });
    ```
    All event types can be found at:  
    *https://developer.mozilla.org/en-US/docs/Web/Events*  

  Some of the ***types*** we can use with `eventListener`,  
    1. `click`  
      This event is used when we want to add an event based on clicking,
        ```javascript
        button.addEventListener("click", function(){
          paragraph.textContent("The button is clicked!")
        });
        ```
    1. `change`  
      This event type is used when we want to add an event listener to an input,
        ```javascript
        document.querySelector("#score").addEventListener("change", function(){
          defaultMaxScore = Number(document.querySelector("#score").value);
        });
        ```
    1. `mouseover`  
      This one is triggered when we move mouse on an element
    1. `mouseout`  
      This one is triggered when we move mouse out of an element
    > ***PS:** So by using above events 3 and 4 we can form a mouse hover effect.*

- We can have more than one listener on an element,
    ```javascript
    var h1 = document.getElementsByTagName("h1")[0];
    h1.addEventListener("click", function(){
      h1.style = "background-color: pink;"
    });
    ```

- Inside of a listener, `this` keyword refers to that element that is being listened,
    ```css
    .clicked{
      background-color: green;
    }
    ```
    ```javascript
    var lis = document.querySelectorAll("li");
    for(var i = 0; i < lis.length; i++){
      lis[i].addEventListener("click", function(){
        this.classList.toggle("clicked");
      });
    }
    ```

- We don't have to use anonymous functions, we can also use predefined functions instead,
    ```javascript
    var lis = document.querySelectorAll("li");
    function toggleClassClicked(){
      this.classList.toggle("clicked");
    }
    for(var i = 0; i < lis.length; i++){
      lis[i].addEventListener("click", toggleClassClicked);
    }
    ```

- `document.body` directly selects the body w/o our own assignment.