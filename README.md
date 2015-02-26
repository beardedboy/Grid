# Grid
A lightweight CSS responsive grid

A flexible and responsive 12 column grid system build in SCSS, compiled to CSS and designed to be a solid starting point to creating a grid system for your next web project.

Supported: IE9+, Chrome, Firefox, Safari

To support IE6-8: add http://selectivizr.com/ (due to the use of :last-child ) and https://github.com/scottjehl/Respond to your project (due to media queries).

##Basic Anatomy

###Container
All of the main content should be wrapped in a div with the 'container' class. The width of the container can be altered in a SCSS variable and all child elements ( mostly likely the rows declared within the container ) max-widths are restrained to this.

######Example

`<div class = "container"></div>`


<hr>

###Rows
Rows are used to organise groups of columns vertically. The 'row' class contains the clearfix hack (credit: http://nicolasgallagher.com/micro-clearfix-hack/ ) to clear all columns within it, which are floated left.

######Example

`<div class = "row"></div>`<br>
`<div class = "row"></div>`<br>
`<div class = "row"></div>`<br>


<hr>

###Columns
Columns are used to split content horizontally. Column widths are set in percentages and any number can be used as long as their total widths add upto 100%.


######Example

`<div class = "col-6-12"></div>`<br>
`<div class = "col-4-12"></div>`<br>
`<div class = "col-2-12 col-last"></div>`<br>

I have decided not to declare any padding to the columns themselves as this has caused issues with uneven widths when nesting columns ( more on nesting later ).  Instead each column needs to include a div with a 'col-content' class.  The actual columns content will be placed within this container.

The last column in each row needs the '.col-last' class applied to allow columns to display correctly in IE7-8.

######Example

`<div class = "col-6-12"><div class = "col-content">content goes here</div></div>`


####Layout Columns

Layout columns widths are defined as x columns out of 12.  Ranging from 1 column out of 12 occupying just 1/12th of the width of a row upto 12 columns out of 12 occupying 100% the width of a row.

######Example

`<div class = "col-6-12"></div>`<br>
`<div class = "col-4-12"></div>`<br>
`<div class = "col-2-12 col-last"></div>`<br>


####Content Columns

Content columns are divided equally by 100% and are represented by an appropriate fraction.  Splitting the total width equally ranging from two halves ( 50 / 50) and labelling the classes as 'col-1-2' to signify 1/2 ( One half ) through to splitting it into twelve equal parts and labelling the class 'col-1-12'.

######Example

`<div class = "col-1-3"></div>`<br>
`<div class = "col-1-3"></div>`<br>
`<div class = "col-1-3 col-last"></div>`<br>

or

`<div class = "col-1-5"></div>`<br>
`<div class = "col-1-5"></div>`<br>
`<div class = "col-1-5"></div>`<br>
`<div class = "col-1-5"></div>`<br>
`<div class = "col-1-5 col-last"></div>`<br>

Credit goes to http://thisisdallas.github.io/Simple-Grid/ for the idea of defining the columns in two sets, layout and content.


####Ratio Columns

Using the ratio variable specified in the SCSS, a set of columns are constructed based on this ratio that can be used.  Using the golden ratio (1.618) for example will result in two columns being create that are split according to this ratio ( 61.8 / 38.2 split). 

Columns spacing are based on the ratio value as well to keep the layout to the same scale.

######Example

`<div class = "col-ratio-2-3"></div>`<br>
`<div class = "col-ratio-1-3"></div>`<br>

<hr>

###Offsetting

Additional classes can be added to a column to allow that column to be offset from the left of its container by the specified increment.

In the example below, a col-6-12 would extend to 50% the width of the container it's in and would usually begin on the left most side of its parent. However an offset class of 3-12 has been added, effectively shifting the columns right by 25% ( which is applied as a 'margin-left' value in the CSS ), resulting in a centrally positioned column.

######Example

`<div class = "col-6-12 offset-3-12"></div>`

<hr>

###Nesting

Grids can be nested within others, and in conjuction with offsetting can allow more complicated grid systems to be constructed.

Each new set of nested columns should be nested within a 'row' classed container.


######Example

`<div class = "col-6-12"></div>`<br>
`<div class = "col-6-12">`<br>
`<div class = "row">`<br>
`<div class = "col-1-3"></div>`<br>
`<div class = "col-1-3"></div>`<br>
`<div class = "col-1-3"></div>`<br>
`</div>`<br>
`</div>`<br>

<hr>

###Additional Classes

<ul>
	<li><del>.row-fixed - If you set the container width to 100% any row class directly inside it will fill to 100% as well.  If you add this class to your row it will take on
	the max-width specified in the SCSS variable $row-fixed-width instead and center it's contents.</del></li>
	<li>.float-left, .float-right - Easy one really, they both respectively float the container they're attached too either left or right.  These have been added to show their functionality with the example grid, however these helper classes would probably be added to your css code at an earlier stage and removed from here.</li>
	<li>.full-width - Applied to a column it will not apply any margins either side, stretching out 100% of the available space.</li>
</ul>

<hr>

##Responsive

By default all columns begin at 100% width and stack one on top the other until they hit a media query with a breakpoint of 50em( initally set within a SCSS variable) at which point all columns are floated left and their appropriate widths are applied.

A set of four media queries have been added to get you going but their contents have been left empty on purpose to allow you to alter the widths of the responsive grid on a per project basis.

<hr>

##Features / Issues to fix

The current list of ongoing issues to fix or new features to add are:

<ul><li>Set up offset classes using a SCSS loop so that they can factor in the $columns variable ( Currently offset classes are declared manually with CSS ) to adapt to changes in column amounts.</li>
<li>Create IE targeted CSS to account for lack of IE6-8 support so user can then decide either to use a css only method or JS method ( Using Selectivizr or equivalent ) to add support</li></ul>