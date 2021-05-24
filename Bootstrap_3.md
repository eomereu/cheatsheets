## Bootstrap 3
### General
Bootstrap is a really useful CSS and JavaScript library. It is a single CSS file and a single JavaScript file. Inside the CSS file there is a bunch of staff that we get for free.  
Components are the bigger pieces.  
We can either download it to our machine and work/load locally (just use link tag for this after moving the 'bootstrap.css' file to the work area) or we can include it online by using,
```html
<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css" integrity="sha384-BVYiiSIFeK1dGmJRAkycuHAHRg32OmUcww7on3RYdg4Va+PmSTsz/K68vbdEjh4u" crossorigin="anonymous">
```	

- We can find any info and any choice of any element on the getbootstrap.com:  
	https://getbootstrap.com/docs/3.3/css/  
	https://getbootstrap.com/docs/3.3/components/

- Following code creates a number only input box,
    ```html
    <input type="number" min="1" max="99"
    ```

- The `type="button"` ATR prevents button to refresh the page onclick,
    ```html
    <button type="button">Player Two</button>
    ```
***

### [Jumbotron](https://getbootstrap.com/docs/3.3/components/#jumbotron)
Jumbotron is the big header like thing with an explanation and a button. It takes the 100% of the contain that it is inside of.  
***

### Grid System
To handle the kinda problematic thing above in other words to put some things to the center of the webpage or make it just 1/3 of the page etc. we normally use *Grid System*. But for a basic solution we can also use the following `container` class to handle it.
***

### Container
A container is a predefined class in Bootstrap that used with `div` tags. It automatically creates a container with predefined useful margines and width etc.
***

### [Forms](https://getbootstrap.com/docs/3.3/css/#forms)
The advancedly modified version of the form we have seen back in ChapterOne
	
- **.form-group** | `<div class="form-group">`  
	A label-input pair is better used within "form-group" class to group'em together and add some spacing from the rest.
	
-	**.form-control** | `<input type="email" class="form-control" id="InputEmai" placeholder="email">`  
	Specifies the style of the input box and its effect when selected.
	
-	**.form-inline** | `<form class="form-inline">`  
		The class that used with the 'form' tag in order to make the form inline.

-	**.checkbox** | `<div class="checkbox">`  
	When we put label-input(checkbox) pair together inside this div class, the label there turns into a clickable text which is awesome
***

### [Nav Bars](https://getbootstrap.com/docs/3.3/components/#navbar)

In the 'Default Navbar' at first we will realize that the hamburger menu (shows up when we shrink the window) and the 'Dropdown' menus are not working. To make them work we need to include 'JavaScript' bootstrap file,
```html
<script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/js/bootstrap.min.js" integrity="sha384-Tc5IQib027qvyjSMfHjOMaLkfuWVxZxUPnCJA7l2mCWNIpG9mGCD8wGNIcPD7Txa" crossorigin="anonymous"></script>
```
And then also include a [*jquery*](https://code.jquery.com/) script over, by copying the most recent/approppriate version and pasting it like we included the Bootstrap JS file with `<script>` tags,
```html
<script src="https://code.jquery.com/jquery-3.5.1.min.js" integrity="sha256-9/aliU8dGd2tb6OSsuzixeV4y/faTqgFtohetphbbj0=" crossorigin="anonymous"></script>
```

- Tag & classes for creating the navbar,
  ```html
  <nav class="navbar navbar-default"></nav>
	```

- It's better if we put the things in the navbar into a container div!

-	We put the menu buttons inside of the following div in order to push'em into hamburger menu when the window is shrinked,  
    ```html
    <div class="collapse navbar-collapse" id="my-menus">
      <ul class="nav navbar-nav">
        <li><a href="#">About</a></li>
        <li><a href="#">Contact</a></li>
      </ul>
      <ul class="nav navbar-nav navbar-right">
        <li><a href="#">Sign Up</a></li>
        <li><a href="#">Login</a></li>
      </ul>
    </div>
    ```

- The hamburger button,
  ```html
  <button type="button" class="navbar-toggle collapsed" data-toggle="collapse" data-target="#my-menus" aria-expanded="false">
    <span class="sr-only">Toggle navigation</span>
    <span class="icon-bar"></span>
    <span class="icon-bar"></span>
    <span class="icon-bar"></span>
  </button>
  ```

  > In the Hamburger button, *data-target* ATR must match the *id* ATR in the *collapse div* above!

- The header section of the navbar. Brand and Hamburger menu button are placed inside of this header part,
  ```html
  <div class="navbar-header"></div>
  ```	

- The left side menu tags of the navbar,
  ```html
  <ul class="nav navbar-nav"></ul>
  ```

- The right side menu tags of the navbar,
  ```html		
  <ul class="nav navbar-nav navbar-right"></ul>
  ```

- `<nav class="navbar navbar-inverse"></nav>`  
	Gives us a reversed navbar (with a deep background and light text by default)

- Classical container strecthes the bar all along the screen but keeps the content in the container,
  ```html
  <nav class="navbar navbar-default">
    <div class="container">
    </div>
  </nav>
  ```
	But div class 'container-fluid' keeps both the content and the bar in the container, which is the default actually,
  ```html
  <nav class="navbar navbar-default">
    <div class="container-fluid">
    </div>
  </nav>
  ```

- To make the ***navbar fixed*** on the top while scrolling down, just add class,  
		`navbar-fixed-top`  
	After making this we will realize that our content stayed behind it which means on the top we need padding, so we will give our body 70px top padding which is the hight of the navbar by default,  
		`padding-top: 70px;`
***

### [The Grid System](https://getbootstrap.com/docs/3.3/css/#grid)
Maybe it's the main reason that people prefer using bootstrap! As we shrink the window, apart from the content being scaled, it adapts into mobile or tablet mode easily and visually looking awesome,	
	
- It scales up to 12 columns. Anytime we use the grid, we must include it into a container! It consists of row and column divs. And so an example usage of grid system is as following,
  ```html
  <div class="container">
    <div class="row">
      <div class="col-lg-6 blue">COL LG 6</div>
      <div class="col-lg-6 blue">COL LG 6</div>
    </div>
  </div>
  ```

- There are 4 sizes to be used in the Grid System:
	1. **xs**: For mobile size
	1. **sm**: For tablet size
	1. **md**: For small screens or windows (laptop,PC)
	1. **lg**: For big screens and windows  
  *We can specify portions for each of these sizes.*

- If we don't specify the lg size explicitly, it will take it form the md element,
  ```html
  <div class="col-md-3 col-sm-6 blue">TOUR DATE!</div>
  <div class="col-md-3 col-sm-6 blue">TOUR DATE!</div>
  <div class="col-md-3 col-sm-6 blue">TOUR DATE!</div>
  <div class="col-md-3 col-sm-6 blue">TOUR DATE!</div>
  ```
	So here when it's *lg* size, 4 of them will be on the same line as in *md*; when it's *sm* size they will get seperated 2 by 2; and finally when it's *xs* they will go 1 by 1 because we didn't specify it and when we don't specify a smaller size or any size, it will take full 12 columns which means 1 element at 1 line.

- Btw above the number coming after the size specifies how many columns the element will be on,
  ```html
  <div class="col-lg-6 blue">COL LG 6</div>
  <div class="col-lg-6 blue">COL LG 6</div>
  ```
	Here it will be on 6 columns, which means there will be 2 of'em on the line when the size is *lg*

- We can make nested grids.
***

### [Glyphicons](https://getbootstrap.com/docs/3.3/components/)
Glyphicons sites:
1. [Glyphicons.com](https://www.glyphicons.com/)
1. [Primer.style](https://primer.style/octicons/)

> Also a nice alternative, for both 3 and 4: [Font Awesome](https://fontawesome.com/)

- Glyphicons has the feature of text in terms of colors; so color ATR will change its color directly and so the font-size will change its size.
***

### Other Stuff
- It is important that we include our own style file after the line we include bootstrap, otherwise we cannot overwrite them!

- When we try to overwrite styles of elements and are not able to do, it is always the best solution to go the page and checking the most specific ATR that effects the element we want to change by 'inspecting element'

- If we want our bootstrap styled website to be responsive on mobile then we should to add the following meta tag to our `<head>` element right above the `<title>` tag:
  ```html
  <meta name="viewport" content="width=device-width, initial-scale=1">
  ```

- `<div class="thumbnail"></div>`  
	Creates a standart box around the element inside of it which is generally an image. If we don't use it around an image even in a grid, image won't fit proplerly and will go as its size!

- If we want to get rid of the changing size images *-especially hight; because when we apply thumbnail width is fixed but hight is not-* then we can see the code on [*CodePen.io*](https://codepen.io/nax3t/pen/MJwpdb)

- To solve the white space bug along the image places. This bug can be fixed by adding a class to the div with class of row, name it flex, then make a css rule like so:
  ```css
  .flex {
    display: flex;
    flex-wrap: wrap;
  }
  ```