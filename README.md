# Grid
A CSS responsive grid

A flexible and responsive X column grid system build in SCSS, compiled to CSS and designed to be a solid starting point to creating a grid system for your next web project.

<strong>Supported:</strong> IE9+, Chrome, Firefox, Safari

<strong>To support IE8:</strong> add https://github.com/scottjehl/Respond to your project ( adds support for media queries).

##Basic Anatomy


###Container
All of the main content should be wrapped in a div with the 'container' class. The width of the container can be altered in a SCSS global variable and all child elements ( mostly likely the rows declared within the container ) are restrained to this max-width.

The 'container-full' class will set the elements width to 100% and should be used if you want the grid to stretch the full width of the screen.

######Example

`<div class = "container"></div>`

`<div class = "container-full"></div>`


<hr>

###Rows
Rows are used to organise groups of columns vertically. The 'row' class contains the clearfix hack (credit: http://nicolasgallagher.com/micro-clearfix-hack/ ) to clear all columns within it, which are floated left.

######Example

`<div class = "grid_row"></div>`<br>
`<div class = "grid_row"></div>`<br>
`<div class = "grid_row"></div>`<br>


<hr>

###Columns
Columns are used to split content horizontally. Column widths are set in percentages and any number can be used as long as their total widths add up to 100%.

Calculating the widths of the columns are based on the number set in the SCSS global variable $columns.

All columns by default are 100% in width and stack one on top of the other, making their layout mobile first.




######Example

( For the rest of the examples in the document we will assume that 12 columns have been set. )

`<div class = "grid_col_exsm_6-12"></div>`<br>
`<div class = "grid_col_exsm_col_4-12 grid_col_lg_col_3-12"></div>`<br>
`<div class = "grid_col_exsm_col_2-12 grid_col_lg_col_3-12"></div>`<br>.




####Layout Columns

Layout columns widths are defined as x columns out of x.  Ranging from 1 column out of 12 occupying just 1/12th of the width of a row upto 12 columns out of 12 occupying 100% the width of a row.

######Example

`<div class = "col-6-12"></div>`<br>
`<div class = "col-4-12"></div>`<br>
`<div class = "col-2-12"></div>`<br>


####Content Columns

Content columns are divided equally by 100% and are represented by an appropriate fraction.  Splitting the total width equally ranging from two halves ( 50 / 50) and labelling the classes as 'col-1-2' to signify 1/2 ( One half ) through to splitting it into twelve equal parts and labelling the class 'col-1-12'.

######Example

`<div class = "col-1-3"></div>`<br>
`<div class = "col-1-3"></div>`<br>
`<div class = "col-1-3"></div>`<br>

or

`<div class = "col-1-5"></div>`<br>
`<div class = "col-1-5"></div>`<br>
`<div class = "col-1-5"></div>`<br>
`<div class = "col-1-5"></div>`<br>
`<div class = "col-1-5"></div>`<br>

Credit goes to http://thisisdallas.github.io/Simple-Grid/ for the idea of defining the columns in two sets, layout and content.


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
	the max-width specified in the SCSS variable $row-fixed-width instead and center it's contents.</li>
	<li><strong>.float-left, .float-right</strong> - Easy one really, they both respectively float the container they're attached too either left or right.  These have been added to show their functionality with the example grid, however these helper classes would probably be added to your css code at an earlier stage and removed from here.</li>
	<li><strong>.full-width</strong>- Applied to a column it will not apply any margins either side, stretching out 100% of the available space.</li>
</ul>

<hr>

##Responsive

By default all columns begin at 100% width and stack one on top the other until they hit a media query with a breakpoint of 50em( initally set within a SCSS variable) at which point all columns are floated left and their appropriate widths are applied.

A set of four media queries have been added to get you going but their contents have been left empty on purpose to allow you to alter the widths of the responsive grid on a per project basis.

<hr>

##Features / Issues to fix

The current list of ongoing issues to fix or new features to add are:

<ul><li>Set up offset classes using a SCSS loop so that they can factor in the $columns variable ( Currently offset classes are declared manually with CSS ) to adapt to changes in column amounts.</li>
</ul>