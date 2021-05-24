## Bootstrap 4
### Install
To include Bootstrap 4,
```html
<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.0/css/bootstrap.min.css" integrity="sha384-9aIt2nRpC12Uk9gS9baDl411NQApFmC26EwAOH8WgZl5MYYxFfc+NcPb1dKGj7Sk" crossorigin="anonymous">
```
***

### Releases
1. 'Alpha Release' is the first release and it basically tells that the current suftware is potentially very buggy and very likely to change mostly.
1. 'Beta Release' is a more stable version and likely to be changed again with breaking changes just like in Alpha.
1. 'Stable Release' is the done enough and ready to publish version.
***

### General
- We can find any info and any choice of any element on getbootstrap.com:  
https://getbootstrap.com/docs/4.5/getting-started/introduction/  
https://getbootstrap.com/docs/4.5/components/  
https://getbootstrap.com/docs/4.5/components/jumbotron/
https://getbootstrap.com/docs/4.5/components/navbar/
https://getbootstrap.com/docs/4.5/layout/grid/

- Following code creates a number only input box,
    ```html
    <input type="number" min="1" max="99"
    ```

- The `type="button"` ATR prevents button to refresh the page onclick,
    ```html
    <button type="button">Player Two</button>
    ```
***

### Changes from Bootstrap 3 to 4
- No Glyphicons in Bootstrap 4,

- Also a nice alternative, for both 3 and 4: [Font Awesome](https://fontawesome.com/)

- The documentation that cover all the changes from Bootstrap 3 to 4:
		https://getbootstrap.com/docs/4.5/migration/

- Main changes:
	1. Flexbox is added and on by default,
	1. As primary unit 'rem' is selected over 'px'
	1. Global size is switched from 14px to 16px
	1. In the grid system '-xl' option is added
	1. 'Panels, thumbnails & wells' are changed with 'cards'
	1. No more 'Glyphicons' insted we can use 'Fontawesome'
	And more more changes... 

- While including scripts: It is essential to put them in the following order at the end of the body:
  1. jQuery
  1. Popper.js
  1. Bootstrap JS

- The pre-prepared [Starter-Template](https://getbootstrap.com/docs/4.5/getting-started/introduction/#starter-template
)
		
- Colors,  
	- https://getbootstrap.com/docs/4.5/getting-started/theming/#color  
	- https://getbootstrap.com/docs/4.5/getting-started/theming/#theme-colors  
	- https://getbootstrap.com/docs/4.5/utilities/colors/#background-color  

- Text Colors,  
	- https://getbootstrap.com/docs/4.5/utilities/colors/  
	Colors are brighter now in Bootstrap 4 than 3 and also it has bg-color, bg-light etc.
***

### [Typography between Bootstrap 3 and 4](https://getbootstrap.com/docs/4.5/content/typography/)
- At this point there is a class type for heading called as '[display heading](https://getbootstrap.com/docs/4.5/content/typography/#display-headings)',
- [Blockquotes](https://getbootstrap.com/docs/4.5/content/typography/#blockquotes),
  ```html
  <blockquote class="blockquote">
    <p class="mb-0">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer posuere erat a ante.</p>
  </blockquote>
  ```
	If we don't want the styling here we simply don't include the `class="quote"` part. Here `class="mb-0"` just sets the margin bottom of the paragraph to 0. And if we want the blockquote to be aligned right, we can add class `"text-right"` to the blockquote. But back in Bootstrap 3 there was a class called as `"blockquote-reverse"` for this mission,
			<blockquote class="blockquote text-right">
- Citation
  ```html
  <blockquote class="blockquote">
    <p class="mb-0">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer posuere erat a ante.</p>
    <footer class="blockquote-footer">Someone famous in <cite title="Source Title">Source Title</cite></footer>
  </blockquote>
  ```
	title attribute usually refers to the title of a work you are citing not the author

- It is now enough to change the default font size to make every text on the page to change dynamically. That's because they set the main unit size as rems not as pxs like back in Bootstrap 3.
***

### Bootstrap 4 Exclusive Features
#### [Borders](https://getbootstrap.com/docs/4.5/utilities/borders/) *(Bordered, Rounded, Left Blank, Color)*
border | rounded | rounded-top | border-left-0 | border-success

#### [Spacing](https://getbootstrap.com/docs/4.5/utilities/spacing/) *(m & p   t/b/l/r/x/y - 0/1/2/3/4/5/auto)*
- `p-x-3`  
make padding size-3 from both sides
  
#### Responsive Breakpoints
Responsive version of spacing for devices  
- `p-md-5`  
start making padding 5 starting from size m up to xl
  
> PS: We don't specify the xs size explicitly, we use default to specify that size and we use the other sizes to move on like by specifying sm and furthermore...

  https://getbootstrap.com/docs/4.5/utilities/spacing/#notation

- [Breakpoints](https://getbootstrap.com/docs/4.5/layout/overview/#responsive-breakpoints)
  - xs - Portrait Mode Smartphones
  - sm - Landcape Mode Smartphones
  - md - Tablets
  - lg - Laptop Computers
  - xl - Desktop Computers
***

### [Navbars](https://getbootstrap.com/docs/4.5/components/navbar/)
- We now have to specify the time of collapse of the menu (hamburger menu) in terms of breakpoints (sm-md...)
- Also the `".bg-*"` class is required in Bootstrap 4
- `"navbar-default"` is changed to either `"navbar-light"` or `"navbar-dark"`
- If we just change the navbar to `"navbar dark"`, just the text will be changed to white, in order to do it in real means, we also need to change the background to `"bg-dark"` Here we have the built-in options that we used before both at `"text"` and `"btn"` which are `"info-warning-success-primary-secondary-danger"`
- `"navbar-expand-{breakpoint}"` specifies the size that the navbar will be extended

- When we type i.e. `"Lorem60"` and hit Tab, it will give us 60 words long paragraph.
***

### [Display](https://getbootstrap.com/docs/4.5/utilities/display/)
- Instead of `"visible"` and `"hidden"` in Bootstrap 3, we now have `".d"` class:
  - `d-{value}` *for xs*
  - `d-{breakpoint}-{value}`
- `<h1 class="d-none d-lg-block d-xl-none">Always hidden except LG</h1>`   
means, display none starting -including- from the breakpoint `"xs"` -not explicit because we don't use the breakpoint name explicitly when it's xs- and when came to XL then display as block.

- Typing,
  ```css
  button.btn.btn-info.btn-lg
  ```
  creates the following,
  ```html
  <button class="btn btn-info btn-lg"></button>
  ```

  But if we don't specify which tag it's gonna be like by not writing `"button"` at the beginning, then it will create a `"div"` tag no matter what the classes are. i.e.  
  ```css
  .border.border-dark
  ```
  creates,
  ```html
  <div class="border border-dark"></div>
  ```
***

### [Flexbox](https://getbootstrap.com/docs/4.5/utilities/flex/)
Flexbox includes a bunch of CSS properties to move things around the position elements inside of a container/page. Lots of Bootstrap 4 utilities have a usage with "flex". But actually flex is a world that exists outside of Bootstrap, by itself.

There are two directions in the Flexbox that we need to know about. The first, by default our "main axis" of our content, is from left to right as from "start" to "end". And also the "cross axis" is from top to bottom as from "start" to "end", by default.

There is a property in Bootstrap that lets us change how items are distributed accross the main axis. Also we can also change the direction of our flexbox which means letting it go from right to left or bottom to top where things go a bit crazy.

>So by default, "Flex direction is left to right & top to bottom."

- `"justify-content"` property is the one that allows us to move the items and the default value is, - `"justify-content-start"` which -by default again- puts everything to the left. In this case if I say,

- `"justify-content-end"`  
it will push the elements to the right. Furthermore,

- `"justify-content-center"`  
centers the elements

- `"justify-content-between"`  
distributes all the elements evenly spaced accross the flexbox by sticking the edge elements to left and right. But,

- `"justify-content-around"`  
will distribute the elements evenly spaced again but this time also making a space at the edges.

By default elements inside the flexbox are stretched from top to bottom. This happens because by default it is `"align-items-stretch"`. But we can use following ones to change it and align items vertically:

- `"align-items-start"`

- `"align-items-center"`

- `"align-items-end"`

- `"align-items-baseline"`

Above we could also add Breakpoints -in other words, we can use them responsively-. Like:
  - `justify-content-{breakpoint}-around`
  - `align-items-{breakpoint}-center`
***

### [Flex Direction](https://getbootstrap.com/docs/4.5/utilities/flex/#direction):
- By default the direction ATR is "flex-row" which makes the direction left-to-right; if we change it to,
  "flex-row-reverse" the direction will be changed to, right-to-left.

- If we add `"flex-column"` ATR; things will go from top to bottom as accepting the y-axis as the main axis. So if I use `"justify-content"` ATR with this ATR added, it will change the placement not on x-axis but on y-axis, which means vertically. One more thing; now `"align-items"` is effecting not the y-axis but x-axis as expected because with the `"flex-column"` ATR added we have changed the main-axis to y; and cross-axis to x so `"align-items"` will now be effecting our latest cross-axis which is x. Same rules apply to `"flex-column-reverse"` by the way.

- We can use direction with breakpoints:  
  - `"flex-md-column"`
  - `"flex-lg-row"`
***

### [Navs](https://getbootstrap.com/docs/4.5/components/navs/)
- `"ul > li > a"` structure is not enforced anymore. `"nav > a"` is enough 

- Navs are rewritten in Bootstrap 4 with Flex which means `"d-flex"` is included implicitly by default at the class at the beginning (rather `"ul"` or `"nav"`). So I can manipulate things by using Flex ATRs above.
***

### [The Grid System](https://getbootstrap.com/docs/4.5/layout/grid/)
Flex is enabled! There are slight differences/similarities from/as the one back in Bootstrap 3:

1. Sizes are shifted back for 1 field which means xs went from ~768 to ~576 and the other shifted one back and now we have "xl" as an addititon
1. Of course we don't write "xs" here also explicitly (we had to back in BS3)
1. It must be in a "container" or a "conatiner-fluid" (which goes all the way on the screen), then we have "row" divs and under those we have "col" elements (divs,h1s etc.) as many as we wish.
1. Still 12 units
1. If I make it responsive (breakpoint based) things will be stacked at each other's top vertically at xs (!May need to be verified!)
1. If I don't specify the unit along the elements they will automatically share the space evenly. If I just give one a specific size so the rest will share the remaining space (units).

- `background: url("imgs/header.jpeg") center center / cover no-repeat`  
the line above, is a short version of those long ATRs, it centers the image and makes it cover and sets to no repeat.
***

### [Cards](https://getbootstrap.com/docs/4.5/components/card/)
- Flex is included

- `section > container > row > col > card`

- `"btn-outline"`  
is a nice looking button (like button etc.)

- If we want specific items to be aligned specifically within a flexbox, we can use,
  ```css
  "align-self-{start/end/center}"
  ```
  Also we can use it with breakpoints,
  ```css
  "align-self-{breakpoint}-{start/end/center}"
  ```

- `"navbar-expand-md"`  
extends the Navbar at MD, so at XS and SM it is collapsed

- `"fixed-top"`  
fixes the navbar to the top as the page is scrolled

- `"img-fluid"`  
makes the image responsive and dynamic especially when using it in a grid

- `"@media (max-width: 1050px) {}"`  
changes the things inside of it at a specific size. Called as "Media Query"

- `class="order-{breakpoint}-1"`  
gives that specific element an order, `"class="order-md-2"`

- `"transition: background 500ms;"`  
  when the background is changed, specifies its duration to change.

- `<input type="number" min="1" max="99"`  
  creates a number only input box

- `<button type="button">Player Two</button>`  
  the 'type="button"' ATR prevents button to refresh the page onclick