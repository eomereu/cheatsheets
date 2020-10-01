## [jQuery](https://jquery.com/)
jQuery is simply a DOM manipulation library.  
**Contents:**
1. [Why use jQuery](https://github.com/eomereu/cheatsheets/blob/master/jQuery.md#why-use-jquery)  
1. [Why not use jQuery](https://github.com/eomereu/cheatsheets/blob/master/jQuery.md#why-not-use-jquery)
1. [Adding jQuery](https://github.com/eomereu/cheatsheets/blob/master/jQuery.md#adding-jquery)
1. [jQuery Selectors](https://github.com/eomereu/cheatsheets/blob/master/jQuery.md#jquery-selectors)
   - *Select Self & Parent*
1. [Manipulating Style](https://github.com/eomereu/cheatsheets/blob/master/jQuery.md#manipulating-style)
1. [Common jQuery Methods](https://github.com/eomereu/cheatsheets/blob/master/jQuery.md#common-jquery-methods)
1. [jQuery Events](https://github.com/eomereu/cheatsheets/blob/master/jQuery.md#jquery-events)
   - *Bubbling Up*
1. [jQuery Effects](https://github.com/eomereu/cheatsheets/blob/master/jQuery.md#jquery-effects)
***
***

### [Why use jQuery](http://youmightnotneedjquery.com/)
1. Fixes "broken" DOM API
1. Brevity and Clarity
1. Ease of use
1. Cross-Browser Support
1. AJAX
1. Lots of people use jQuery!
***

### [Why not use jQuery](http://youmightnotneedjquery.com/)
1. The DOM API is no longer "broken"
1. It doesn't do anything you can't do on your own
1. It's an unnecessary dependency
1. Performance
1. Lots of people are moving away from jQuery!
***

### Adding jQuery
First way is downloading jQuery and liking to it locally:
```javascript
<script type="text/javascript" src="jquery.js"></script>
```
Or linking to a [CDN(a hosted copy)](https://code.jquery.com/) directly:
```javascript
<script type="text/javascript" src="https://code.jquery.com/jquery-3.5.1.min.js"></script>
```
>We must include jQuery at the heading and our js file at the end of the body!

>To check simply if the jQuery is added correctly, on the console on the page we can type `jQuery` and hit enter. It must return sth like `function (a,b){return new n.fn.init(a,b)}` if correctly included...

Meanings of different versions are like the following:

- ***uncompressed:*** The version that generally for developers with a proper coding and explaining comments inside but with more than 9k lines. Takes a longer time to load compared to minified (compressed) version.
- ***minified:*** The compressed (minified) version of the original one. All blank spaces, line breaks and comments are gone, variable names are reduced to single character and thus 9k lines are reduced to a couple of lines which provides us a faster loading time
- ***slim:*** The version that just contains some main features
- ***slim minified:*** The compressed (minified) version of the ***slim*** one.
***

### jQuery Selectors
&nbsp;-&nbsp;Selecting with jQuery is like ***querySelectorAll***, in that we provide a CSS style selector and jQuery will return all matching elements:
```javascript
$("selectorGoesHere");
// to select all img tags,
$("img");
// to select all elements with class 'sale',
$(".sale");
// to select element with id "bonus",
$("#bonus");
// to select all a tags inside of li's,
$("li a");
```
**Select Self & Parent**  
In order to select self and the parent of a current element:
```javascript
// to select the current element in an event function,
$(this);
// to select the parent element of the current element,
$(this).parent();
```
***

### Manipulating Style
&nbsp;-&nbsp;`.css(prop)` - `css(prop, val)` - `css(prop, obj)` method is jQuery's interface to styling.  
Passing in just property will return us its value,
```javascript
> $("img").css("width");
"1533px"
```
Passing in both *property* and *value* will either apply or set/change the property to given value:
```javascript
// select element with id "special" and give it a border,
$("selector").css(property, value); //or,
$("selector").css(styleObject);
// i.e.:
$("#special").css("border", "2px solid red");
```
Passing in an object with styles in it allows us to manipulate multiple properties in one go:
```javascript
var styles = {
  backgroundColor: "pink",
  fontWeight: "bold"
};
$("#special").css(styles);
```
We can select and manipulate all elements of a kind in one line,
```javascript
$("li").css("color", "purple");

$("p").css({
  fontSize: "10px",
  textTransform: "uppercase",
  background: "#232323",
  color: "white"
});
```
To select only all the divs with specified class,
```javascript
$("div.highlight");
```
To select the first element of a group,
```javascript
$("div").first();
```
To select the last element we can use `.last()` method:
```javascript
$("div").last();
```
Here inside inside this *styling object* or *property* we must use the properties that contains a *dash (-)* with removing the dash and converting the first letter of the following word to uppercase as seen above with *fontSize* and *textTransform* properties. Otherwise we get an error!
***

### [Common jQuery Methods](https://api.jquery.com/)
- [`text()` - `text(val)`](https://api.jquery.com/text/)  
  Actually does the same thing as `.textContent`. It retrieves just the strings inside of an element and if we pass a value it will modify the content with it. This method is called as *HTML safe* and actually provides us a safe way while getting **input** from user!
  ```javascript
  //<h1>Grüß dich!</h1>
  > $("h1").text();
  "Grüß dich!"
  > $("h1").text("Servus!");
  > $("h1").text();
  "Servus!"
  ```

- [`html()` - `html(val)`](https://api.jquery.com/html/)
  Works in the same way with `.innerHTML` from DOM. It retrieves the content with HTML stuff included and again if we pass a value with HTML stuff it modifies the content accordingly:
  ```javascript
  //<h1>... <strong>keiner</strong> meiner Freunde ...</h1>
  > $("h1").html();
  "... <strong>keiner</strong> meiner Freunde ..."
  > $("h1").html("... keiner <em>meiner</em> Freunde ...");
  > $("h1").html();
  "... keiner <em>meiner</em> Freunde ..."
  ```

- [`attr(atr)` - `attr(atr, val)`](https://api.jquery.com/attr/)  
  Gets the value of the specified attribute of the selected element if *atr* is given as only parameter:
  ```javascript
  // <a href="https://www.google.com">Take me to Google!</a>
  > $("a").attr("href");
  "https://www.google.com"
  ```
  If both *atr* and *val* parameters are given, it sets that *atr* to that *val*. More than one atr can be changed via giving an object:
  ```javascript
  //<img id="inn" src="inn.jpg" alt="Inn">Grüß dich!
  > $("#inn").attr("alt", "Inn Fluss");
  //<img id="inn" src="inn.jpg" alt="Inn Fluss">Grüß dich!
  > $("#inn").attr({
    alt: "Wundervoller Inn Fluss",
    title: "Hans Krille"
  });
  > $("h1").text();
  "Servus!"
  ```
  We can even manipulate type of *input boxes* as its feature depends on its *value*:
  ```javascript
  // <input type="text" placeholder="input">
  $("input").attr("type", "color");
  $("input").attr("type", "number");
  $("input").attr("type", "checkbox");
  ```

- [`val()` - `val(val)`](https://api.jquery.com/val/)  
  Actually it's the wrapper for `.value()` in DOM. Thus it helps us extract the value from an input. On the other hand it is of course working with anything that has *value* attribute like dropdown menus etc.  
  If we don't put in an argument it returns us the value of the input we select:
  ```javascript
  // Our input box: (<input type="text" placeholder="inp">)
  // ---------------
  // |inp          |
  // ---------------
  > $("input").val();
  ""
  ```
  If we pass in a value, it will set the value of that input to that value. This is used especially when the value of the input box is wanted to be cleared, *i.e. after typing a value to be added to a list and hit Enter*
  ```javascript
  > $("input").val("Eigentlich");
  // ---------------
  // |Eigentlich   |
  // ---------------
  > $("input").val(""); //clears the box
  ```
  On dropdown menus:
  ```javascript
  $("select").val(); //returns the current value (selection)
  ```
  > For selects, checkboxes and radio buttons, you can use `:checked` to select the right elements. For example:
  ```javascript
  // <select id="foo">...</select>
  // Get the value from the selected option in a dropdown
  $("select#foo option:checked").val();
  
  // Get the value from a dropdown select directly
  $("select#foo").val();
  
  // Get the value from a checked checkbox
  $("input[type=checkbox][name=bar]:checked").val();
  
  // Get the value from a set of radio buttons
  $("input[type=radio][name=baz]:checked").val();
  ```

- [`addClass()`](https://api.jquery.com/addClass/)   
  Equals to `.classList.add()` in DOM. Simpley adds class/classes to the selected object/objects:
  ```javascript
  $("li").addClass("style:hover darkened");
  ```
- [`removeClass()`](https://api.jquery.com/removeClass/)  
  Equals to `.classList.remove()` in DOM. Simpley removes class/classes from the selected object/objects:
  ```javascript
  $("li").removeClass("light");
  ```
- [`toggleClass()`] (https://api.jquery.com/toggleClass/)  
  Equals to `.classList.toggle()` in DOM. Simpley toggles class/classes of the selected object/objects:
  ```javascript
  $("li").toggleClass("selected");
  ```
***

### [jQuery Events](https://api.jquery.com/category/events/)
- [`.click()`](https://api.jquery.com/click/)  
  Does the same thing as `.addEventListener("click", func)` in DOM to an or a set of elements:
  ```javascript
  $("#submit").click(function(){
    console.log("Submitted");
  });
  $("button").click(function(){
    console.log("Clicked");
  });
  ```
  > While jQuery-specified methods is going to be used like `.css()` method, in case we want to refer to the object that we are adding an event (just like above) then we need to use `$(this)` keyword instead of alone `this` in DOM!
  ```javascript
  $("button").click(function(){
    $(this).css("background", "green");
    console.log("You clicked on: " + $(this).text());
  });
  ```
- [`.keypress()`](https://api.jquery.com/keypress/) - [`.keydown()`](https://api.jquery.com/keydown/) - [`.keyup()`](https://api.jquery.com/keyup/)  
  `keydown()` is immediately triggered whenever any key is pressed `keyup()` will similarly be triggered when any key is released. But differently `keypress()` will not be triggered when any key is just simply pressed down and released; instead it will be triggered whenever a character is inputted.
  > For example when we want to give input as ***'Shift + a'*** to make an uppercase ***a***, if we use `keydown()` and `keyup()` they will both be trigerred when we press and release ***Shift*** button. However if we use `keypress()` it will only be triggered as the uppercase ***a*** is inputted.  
  
  > So briefly when to work with non-character keys like ***arrow keys*** etc. we definetly want to use `keydown()` and `keyup()` but in other scenarios it's better to prefer `keypress()`
  ```javascript
  $("input").keypress(function(){
    console.log("A key pressed!");
  });
  ```
  With the help of an object to be passed to the function inside the **keypress** *(actually it's always passed but at this point we ought to use it explicity, generally given as 'e' or 'event')* we can detect the pressed key and use it for our benefit like automatically getting the input and clearing the box content as the user press **Enter**:
  ```javascript
  $("input").keypress(function(event){
    console.log(event);
  });
  ```
  Here inside *event* object there are three attributes referring to the code of the entered character: ***charCode***, ***keyCode*** and ***which***. Ignoring their slight differences *(maybe to be mentioned later)* they most of the time show us the code of the entered character.
  > Here is a great website to show the code of the key we press interactively:  
  [Javascript Char Codes (Key Codes)](https://www.cambiaresearch.com/articles/15/javascript-char-codes-key-codes)  
  
  By making use of the website we can detect when user hits Enter and behave accordingly:
  ```javascript
  $("input").keypress(function(e){
    if(e.which === 13){
      alert("\'Enter\' is pressed!");
    }
  });
  ```
- [`.on()`](https://api.jquery.com/on/)  
  Works in the same way as `addEventListener` in DOM. It lets us specify the type of event to listen for. 
  > This is the method used 99% of the time!
  ```javascript
  $("#submit").on("click", function(){
    console.log("Another click!");
  });
  $("button").on("dbclick", function(){
    console.log("Button double clicked!");
  });

  // hover: mouseenter + mouseleave
  $("button").on("mouseenter", function(){
    console.log("Mouse has once moved over button!");
  });
  $("button").on("mouseleave", function(){
    console.log("Mouse left button!");
  });

  $("button").on("dragstart", function(){
    console.log("Drag started!");
  });
  $("input[type='text']").on("keypress", function(){
    console.log("Key press in an input!");
  });
  ```
  > **`on()`** allows us to add listeners for all potential future elements on the contrary of `click()` which only adds listeners for existing elements when the page loads. That's why we will broadly use **`on("click", func)`** instead of `click()`!  

**Bubbling Up**  
When we for example click on a `span` in an `li` actually we are clicking on: `span - li - ul - div - body` respectively which called as ***bubbling up***. This may cause unwanted things to be triggered if not handled, so to handle this issue:
```javascript
$("span").click(function(e){
  e.stopPropagation();
});
```
***

### [jQuery Effects](https://api.jquery.com/category/effects/)
- [`.fadeOut()`](https://api.jquery.com/fadeOut/)  
  The `.fadeOut()` method animates the opacity of the matched elements.
  
  > Once the opacity reaches 0, the `display` style property is set to `none`, so the element no longer affects the layout of the page! On the other hand we may not to keep those deleted elements on the page, in that case we can do the following:

  > To completely remove the element(s) we can use `$(this).remove()` within the callback function of fadeOut! PS: If we use it directly insted using within the callback function, it will immediately disappear since it won't be waiting for that fadeOut to end.

  Durations are given in milliseconds; higher values indicate slower animations, not faster ones. The strings *fast* and *slow* can be supplied to indicate durations of 200 and 600 milliseconds, respectively. If any other string is supplied, or if the duration parameter is omitted, the default duration of 400 milliseconds is used.
  ```javascript
  $("button").on("click", function(){
    $("#myDiv1").fadeOut();
    $("#myDiv2").fadeOut(1000);
    $("#myDiv3").fadeOut("slow");
    $("#myDiv4").fadeOut("fast");
    $("#myDiv5").fadeOut(200, function(){
      console.log("fade out completed");
    });
    $("#myDiv6").fadeOut(600, function(){
      console.log("fade out completed");
      $(this).remove();
    });
  });
  ```
- [`.fadeIn()`](https://api.jquery.com/fadeIn/)  
  The `.fadeIn()` method animates the opacity of the matched elements. It is similar to the `.fadeTo()` method but that method does not unhide the element and can specify the final opacity level.

  > As expected, the `display` property of the elements to be affected is supposed to be set to `none`!

  Same duration rules apply as in `.fadeOut()`
  ```javascript
  $("button").on("click", function(){
    $("#myDiv1").fadeIn();
    $("#myDiv2").fadeIn(1000);
    $("#myDiv3").fadeIn("slow");
    $("#myDiv4").fadeIn("fast");
    $("#myDiv5").fadeIn(200, function(){
      console.log("fade in completed");
    });
  });
  ```
- [`.fadeToggle()`](https://api.jquery.com/fadeToggle/)  
  Knows wheteher to fade the element(s) in or out based on their current value of `display` property.
  ```javascript
  $("button").on("click", function(){
    $("#myDiv1").fadeToggle();
    $("#myDiv2").fadeToggle(1000);
    $("#myDiv3").fadeToggle("slow");
    $("#myDiv4").fadeToggle("fast");
    $("#myDiv5").fadeToggle(200, function(){
      console.log("fade completed");
    });
  });
  ```
- [`.slideUp()`](https://api.jquery.com/slideUp/)
  Actually it's the sliding *(rather than fading)* version of `.fadeOut()`. So it slides up (wipes out) the selected element(s).
  ```javascript
  $("button").on("click", function(){
    $("#myDiv1").slideUp();
    $("#myDiv2").slideUp(1000);
    $("#myDiv3").slideUp("slow");
    $("#myDiv4").slideUp("fast");
    $("#myDiv5").slideUp(200, function(){
      console.log("slide up completed");
      $(this).remove();
    });
  });
  ```
- [`.slideDown()`](https://api.jquery.com/slideDown/)  
  Similarly it's the sliding *(rather than fading)* version of `.fadeIn()`. So it slides down (brings in) the selected element(s). Again as expected the `display` propoerty of the matched elements is supposed to be `none`.
  ```javascript
  $("button").on("click", function(){
    $("#myDiv1").slideDown();
    $("#myDiv2").slideDown(1000);
    $("#myDiv3").slideDown("slow");
    $("#myDiv4").slideDown("fast");
    $("#myDiv5").slideDown(200, function(){
      console.log("slide down completed");
    });
  });
  ```
- [`.slideToggle()`](https://api.jquery.com/slideToggle/)
  Works with the same logic as all toggle classes and similarly to `.fadeToggle()`. So it again decides whether to slide down or up based on the `display` property.
  ```javascript
  $("button").on("click", function(){
    $("#myDiv1").slideToggle();
    $("#myDiv2").slideToggle(1000);
    $("#myDiv3").slideToggle("slow");
    $("#myDiv4").slideToggle("fast");
    $("#myDiv5").slideToggle(200, function(){
      console.log("slide completed");
    });
  });
  ```