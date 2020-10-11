## CSS (Cascading Style Sheets)
They are actually seperate files that we include into our HTML files.
***

### General Stuff
- The general rule that every line we write will follow:
  ```css
  selector {
    property: value;
    anotherProperty: value;
  }
  ```

- *Inline styling* is not a good idea because it doesn't seperate HTML and CSS files. Furthermore it's a lot of work to form lots of things all one at a time and especially when we want to make some changes to multiple elements,
  ```html
  <h3 style="color: pink;">My Heading</h3>
  ```

- *Style Tag* is also a bad idea, -on the other hand generally used for quick demonstrations and checks- coz it's also included in the HTML file but as a seperate part on top in 'head' part; which is mainly allows us to write some CSS code inside this tag,
  ```html
  <style type="text/css">
    .
    .
    .
  </style>
  ```

- `/* Comment in CSS */`

- So finally to write our CSS in a different file, we use <link> tag inside the HTML file. Hitting tab after typing 'link' will create a nicely prepared tag for us.,
  ```html
  <link rel="stylesheet" type="text/css" href="CSSFileName.css">
  ```
  > It must be included in the 'head' section! 


### Color System
There are three types of color system:
1. Hexadecimal
1. RGB
1. RGBA  

Actually the former two refer to the same thing but have differences in both syntax and base selection.

- Hexadecimal colours contain six digits following a `#`. It's using base 16.  
	`#_ _ _ _ _ _ `: First 2 represents how much red is the colour and the others green, blue respectively.  
  ```css
  #FFFFFF : White  
  #000000 : Black
  ```

- RGB colours have slight different showing style. It's using base 10, the values show red, green, blue
  ```css
  rgb(_, _, _)
  /*  r  g  b  */
  rgb(255,255,255): White
  rgb(0,0,0): Black
  ```

- RGBA system adds a fourth field as transparency value whose range is between 0 and 1, (A stands for Alpha)
  ```css
  rgba(_, _, _, ._)
  /*   r 	g  b   t   */
  rgba(100,82,12,1): No transparency
  rgba(100,82,12,0): Fully transparent (nothing shows up)
  rgba(100,82,12,.6): Little transparency (as getting closer to 1)
  rgba(100,82,12,.3): More transparency (as getting closer to 0)
  ```
***

### Properties
[**background**](https://developer.mozilla.org/en-US/docs/Web/CSS/background)
```css
background: rgb(255,255,255); /* full color */
background: url(https://badasshelmetstore.com/wp-content/uploads/2016/10/avengers-helmets.jpg); /* image */
```
Alone this will replicate the image all along the page so be careful to pick a continous one if using this.

Some background properties
```css
background-repeat: no-repeat; /* If we don't want the image to be repeated as above we use this */
background-size: cover; /* If we don't use this property the page won't cover the page. It won't strecth out or won't fit depending on the resolution; if we don't use this */ 
```

[**border**](https://developer.mozilla.org/en-US/docs/Web/CSS/border)  
Normally we use border with 3 must-have properties:
1. width
1. style
1. color

So the original code looks like this:
```css
border-width: 3px;
border-style: solid;
border-color: white;
```
But we use the following in terms of being practical:
```css
border: 3px solid white; /* widht style color respectively */
```

[**text-transform**](https://developer.mozilla.org/en-US/docs/Web/CSS/text-transform)  
Transforms the selected text into wanted style:
```css
label {
	text-transform: uppercase;
}
/* some other options: lowercase, capitalize...*/
```

[**font-family**](https://developer.mozilla.org/en-US/docs/Web/CSS/font-family)  
Decides the font type. Type name must be between quotes if it starts with numbers.
```css
h1 {
  font-family: Arial;
}
```

[**font-size**](https://developer.mozilla.org/en-US/docs/Web/CSS/font-size)  
Here 'em' is dynamically changing and multiplying the text that it belongs to, according to the one level outer text of the current text
```css
body {
  font-size: 16px;
}

h1 {
  font-size: 2.0em;
}
```

[**font-weight**](https://developer.mozilla.org/en-US/docs/Web/CSS/font-weight)  
Decides how bold/light text will be. Some of the font types let you use it with a range of 100-800 (not every value but every hundred value) other than normal, bold etc.
```css
p {
  font-weight: 800;
}
h2 {
  font-weight: bold;
}
```

[**text-align**](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align)  
Specifies the alignment
```css
h1 {
  text-align: center;
}
```

[**text-decoration**](https://developer.mozilla.org/en-US/docs/Web/SVG/Attribute/text-decoration)  
Used to give text underline effect, linethrough effect etc.
```css
p {
  text-decoration: line-through;
}
```

[**max-width**](https://developer.mozilla.org/en-US/docs/Web/CSS/max-width)  
Specifies the max width to be shown as window shrinkes. It makes sense to use it with a percentage width.
```css
max-width: 800px;
width: 80%;
```

[**transition**](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)  
Following code segment provides a transition effect by any changes on the related element. Last two lines ensure the compatibility with various browsers.
```css
transition: all 0.3s;
-webkit-transition: all 0.3s;
-moz-transition: all 0.3s;
```
If we want the transition effect just for a specific change then we type that attribute instead of 'all' keyword,
```css
transition: background 0.5s;
```

[**letter-spacing**](https://developer.mozilla.org/en-US/docs/Web/SVG/Attribute/letter-spacing)  
Letter spacing -btw- specifies the space between letters
```css
letter-spacing: 0.2rem;
```

[**line-height**](https://developer.mozilla.org/en-US/docs/Web/CSS/line-height)  
Specifies the height of a line.
```css
li {
  height: 40px;
  line-height: 40px;
}
```
Also we can use it by multiplying the default line spacing value which is determined by the font
```css
p {
  line-height: 2;
}
```

[**list-style**](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style)  
Modifies the list specifier (dot as default)
```css
ul {
  list-style: none;
}
```

[**box-shadow**](https://developer.mozilla.org/en-US/docs/Web/CSS/box-shadow)  
Adds shadow to box *(offset-x | offset-y | blur-radius | color)*
```css
#container {
  box-shadow: 0 0 3px rgba(0,0,0, 0.1);
}
```

[**box-sizing**](https://developer.mozilla.org/en-US/docs/Web/CSS/box-sizing)  
Sets how the total width and height of an element is calculated.
```css
input {
  box-sizing: border-box;
}
```

[**border-radius**](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius)  
Rounds the corners of an element's outer border edge. We can set a single radius to make circular corners, or two radii to make elliptical corners.
```css
#square1 {
  border-radius: 30px;
  /* or */
  border-radius: 10%;
  /* or */
  border-radius: 25% 10%; /* rounds corners differently */
}
```

[**outline**](https://developer.mozilla.org/en-US/docs/Web/CSS/outline)  
Sets all the outline properties in a single declaration.
```css
input:focus {
  border: 3px solid #2980b9;
  outline: none;
}
```
***

### CSS Selectors
1. Element
1. ID
1. Class
1. Star
1. Descendat Selector
1. Adjacent Selector
1. Attribute Selector
1. Pseudo Selectors
    1. :nth-of-type
    1. :checked
    1. :hover
    1. :visited
    1. ::first-letter
    1. :focus
 
1.**Element**  
Selects all instances of a given element.
```css
div {
  background: aquamarine;
}
```

2.**ID**  
Selects an element with a given ID. IDs have to be unique! It's not possible to have multiple instances with the same ID! We use hashtag **#** while referring to IDs.
```html
<p id="mytext">Hallo!</p>
```
```css
#mytext {
  background-color: yellow;
}
```

3.**Class**  
Selects all elements with the given class. We use dot **.** while referring to classes.
```html
<p class="important">Achtung!</p>
<p class="important">Das ist verboten!</p>
```
```css
.important {
  color: red;
}
```

4.**Star**  
Selects everything on a page
```css
* {
  border: 1px solid lightgrey;
}
```

5.**Descendant Selector**  
Selects element(s) inside an element(s)
```css
ul li a {
  color: red;
}
```

6.**Adjacent Selector**  
Selects an element after an element.
```css
h4 + ul {
  border: 4px solid red;
}
```

7.**Attribute Selector**  
Selects all of that ATRs
```css
a[href="http://www.google.com"] {
  background: blue;
}
```

8.**Pseudo Selectors**  
8.1.**:nth-of-type**  
Selects nth element of every odd/even number of that element
```css
li:nth-of-type(3){
  background: purple;
}

li:nth-of-type(odd){
  background: purple;
}
```

8.2.**:checked**  
Selects all "checked" checkboxes
```css
input:checked {
	background: green;
}
```

8.3.**:hover**  
Lets us modify the element when it's hovered on
```css
h1:hover {
	color: blue;
}
```

8.4.**:visited**
Lets us modify the element (link) when it's already visited:
```css
a:visited {
	color: gray;
}
/* some other options: link, visited, hover, active...*/
```

8.5.**::first-letter**  
Selects the first letter of the element with id 'special'
```css
#special::first-letter {
	color: green;
	font-size: 36px;
}
```

8.6.**focus**  
Lets us modify the element (input) when it's clicked on (focused)
```css
input:focus {
  background: #fff;
  border: 3px solid #2980b9;
  outline: none;
}
```
***

### Google Chrome Inspect Element
We can right click while on a webpage to inspect element. It will allow us to see both the HTML and the CSS part of it. So we can use this feature both for testing and trying things easily while creating some things and for inspecting stylings of other webpages and replicating them.  

If we right click on a specific element and then click on inspect element it will directly show us that specific element within the opened up code segment.  

Here on the right side, 'Styles' tab will consist the CSS stylings! We can directly on and off things or manipulate things here and watch the changes.  

On the left side we can click on 'Magnifier' icon to go to sources of some things on the page by then clicking on'em. 
***

### Inheritence & Specificity
'Inheritence' is the traditional thing that we know from almost all languages, when we specify,
```css
body {
  color: red;
}
```
Everything on the page, inherits this and turns into blue although we don't mark'em; if we want them to be styled differently we gotta write'em explicitly, like,
```css
body {
  color: red;
}
ul {
  color: blue;
}
li:nth-of-type(3){
  color: green;
}
```
And here 'Specifity' moves in. It is multiple stylings targeting one element; just like above body, ul and li targets the 3rd li(s) on the page. And in this war, the closest one (in terms of containing) -the most specific one in other words- wins this war.

At this point when we inspect element on a page and look at the styles, we will see that those defeated inherited styles are overlined! And these are showed from bottom to top as more general to more specific one.

### Specificity Order
From least to most specific:  
1. Type Selectors
    ```css
    li {}
    li a {}
    h4 + ul {}
    ```
2. Class, Attribute & Pseudo-Class Selectors  
    ```css
    .hallo {

    }
    input[type="text"] {

    }
    a[href="http://www.google.com"] {

    }
    a:hover
    input:checked
    ```
3. ID Selectors
    ```css
    #hello {

    }
    ```

### Box Model
In a document, each element is represented as a rectangular box. In CSS, each of these rectangular boxes is described using the standart box model.  
Each box has four edges:
1. **Margin**  
The space outside the box; kinda within the elements.
    ```css
    margin: 20px; /* Same space from all sides */
    margin-top: 40px;
    margin: TOP RIGHT BOTTOM LEFT; /* More specified space from any side */
    margin: 0 auto 0 auto; /* Centers the element from left and right edges */
    margin: 0 auto; /* Specifies top to 0 px & right to auto, so indirectly fully centering from right and left again */
    ```

2. **Border**  
    ```css
    The thickness of the box.
    border: 2px solid blue;
    border-width: 2px;
    border-style: solid;
    border-color: blue;
    ```

3. **Padding**  
The space between border and the content inside of it.
    ```css
    padding: 10px;
    padding-left: 20px;
    ```

4. **Content**  
The text itself (width & hight).
    ```css
    width: 20px;
    width: 60%;
    ```

    The space on the right of the content comes from the number 4, which is content edge -width- but the space on the left comes from number 3, which is padding edge -padding-left-. On the other hand, padding has also right spacing, which means we have two adjustments for the right side of our content.

    We can use a percentage on the width to make the website more dynamic and change itself depending on the body (window) size,
    ```css
    p {
      width: 50%;
    }
    ```
***

### Other Stuff
- [Google Fonts](fonts.google.com)  

- [Font Awesome](https://fontawesome.com/)

- [uiGradients](https://uigradients.com/#FacebookMessenger)

- There are 2 ways of ordering CSS styling within the CSS file:
  1. Ordering based on the element order on the page from top to bottom...
  1. Ordering based on the specificity from the least to the most... ***(more popular)***

- An element can have multiple classes at once,
	<td class="vertical horizontal"></td>
	So this td is in also vertical class and also horizontal class.

- Normally each div and div-like elements go on different lines, that's because what's defined as default as float property. If we change it as the following, all divs will float from left to right to bottom:
	div {
		float: left
	}
	When we don't modify float property, by default HTML has one space between adjacent images; but when we modify it, that's gone.

- It may be more beneficial to have just one h1 -which is the main and the only one- on the page and having the other headings -which are multiple- as h2.

- 'rem' adjusts the text size not according to the size of the parent element like 'em' but according to the root element; which means we don't have to worry about one changing the other,
  ```css
    letter-spacing: 0.2rem;
  ```

- To make *placeholders* in inputs italic, simplty add the following code to CSS file:
  ```css
  ::-webkit-input-placeholder {
    font-style: italic;
  }
  :-moz-placeholder {
    font-style: italic;  
  }
  ::-moz-placeholder {
    font-style: italic;  
  }
  :-ms-input-placeholder {  
    font-style: italic; 
  }
  ```

### Some Useful Stylings
```css
font-weight: normal;
font-weight: 700;
text-transform: uppercase;
line-height: 1.1;
letter-spacing: 1px;
height: 100%;

.button {
  border: none; /*cancels the borders (of a button)*/
  outline: none; /*deactivates the outline effect when clicked on a button*/
  background: none; /*deactivates the built-in white background of buttons*/
  font-size: inherit; /*inherits the font-size from its surrounding element*/
}

button:hover {
  color: white;
  background: steelblue;
}

.square {
  border-radius: 10%; /*rounds a square's corners of a square*/
  float: left; /*allows to place realted divs next to each other rather than one at a line*/
  width: 30%; /*sets an exact width to the element*/
}

#message {
  display: inline-block;
  width: 20%;
}

body {
  background-image: url();
  background-size: cover;
  background-position: center;
}

/*In order to make the background image cover all the file:*/
html {
  height: 100%;
}

/*An awesome shadow that contributes depth to the texts on the page,*/
text-shadow: 0px 4px 3px rgba(0,0,0,0.4),
              0px 8px 13px rgba(0,0,0,0.1),
              0px 18px 23px rgba(0,0,0,0.1);
text-shadow: offset-x offset-y radius color;
/*https://developer.mozilla.org/en-US/docs/Web/CSS/text-shadow*/

/*To fix the appearance of the `<hr>` on mobile devices, add `max-width: 90%;` to the `hr` selector,*/
hr {
  width: 400px;
  max-width: 99%;
}

/* To solve the white space bug along the image places. This bug can be fixed by adding a class to the div with class of row, name it flex, then make a css rule like so:*/
.flex {
  display: flex;
  flex-wrap: wrap;
}

/* To push an icon to the right: */
.fa-plus-circle {
  float: right;
}

```