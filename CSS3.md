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
**background**
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

**border**  
Normally we use border with 3 must-have properties:
1. width
1. style
1. color

So the original code looks like this:
```css
border-width: 3px;
border-style: solid;
border-color: white;
But we use the following in terms of being practical:
border: 3px solid white; /* widht style color respectively */
```

**text-transform**  
Transforms the selected text into wanted style:
```css
label {
	text-transform: uppercase;
}
/* some other options: lowercase, capitalize...*/
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
li {

}

li a {

}

h4 + ul {

}
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