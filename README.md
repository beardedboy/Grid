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

All columns have the .grid_col class applied and at their base style are 100% in width and stack one on top of the other, making their layout mobile first.

Different layout widths can then be applied at the various media query breakpoints by applying additional classes in the format '.grid_col_sm-4_12' ( This example would set the column to stretch over 4 of the 12 columns at the small media query breakpoint ).


######Example

( For the rest of the examples in this document we will assume that 12 columns have been set. )

`<div class = "grid_col_exsm-6_12"></div>`<br>
`<div class = "grid_col_exsm-4_12 grid_col_lg-3_12"></div>`<br>
`<div class = "grid_col_exsm-2_12 grid_col_lg-3_12"></div>`<br>.



####Layout Columns

Layout columns widths are defined as x columns out of 12.  Ranging from 1 column out of 12 occupying just 1/12th of the width of a row upto 12 columns out of 12 occupying 100% the width of a row.

######Example

`<div class = "grid_col_sm-6_12"></div>`<br>
`<div class = "grid_col_sm-4_12"></div>`<br>
`<div class = "grid_col_sm-2_12"></div>`<br>


####Content Columns

Content columns are divided equally by 100% and are represented by an appropriate fraction.  Splitting the total width equally ranging from two halves ( 50 / 50) and labelling the classes as 'col-1-2' to signify 1/2 ( One half ) through to splitting it into twelve equal parts and labelling the class 'col-1-12'.

######Example

`<div class = "grid_col_sm-1_3"></div>`<br>
`<div class = "grid_col_sm-1_3"></div>`<br>
`<div class = "grid_col_sm-1_3"></div>`<br>

or

`<div class = "grid_col_sm-1_5"></div>`<br>
`<div class = "grid_col_sm-1_5"></div>`<br>
`<div class = "grid_col_sm-1_5"></div>`<br>
`<div class = "grid_col_sm-1_5"></div>`<br>
`<div class = "grid_col_sm-1_5"></div>`<br>

Credit goes to http://thisisdallas.github.io/Simple-Grid/ for the idea of defining the columns in two sets, layout and content.


<hr>

###Offsetting

Additional classes can be added to a column to allow that column to be offset from the left of its container by the specified increment.

In the example below, a col-6-12 would extend to 50% the width of the container it's in and would usually begin on the left most side of its parent. However an offset class of 3-12 has been added, effectively shifting the columns right by 25% ( which is applied as a 'margin-left' value in the CSS ), resulting in a centrally positioned column.

######Example

`<div class = "grid_col_sm-6_12 grid_offset_sm-3-12"></div>`

<hr>

###Nesting

Grids can be nested within others, and in conjuction with offsetting can allow more complicated grid systems to be constructed.

Each new set of nested columns should be nested within a 'row' classed container.


######Example

`<div class = "grid_col_sm-6_12"></div>`<br>
`<div class = "grid_col_sm-6_12">`<br>
`<div class = "grid_row">`<br>
`<div class = "grid_col_sm-1_3"></div>`<br>
`<div class = "grid_col_sm-1_3"></div>`<br>
`<div class = "grid_col_sm-1-3"></div>`<br>
`</div>`<br>
`</div>`<br>

<hr>

###Float fixing

When you have a row with multiple columns that wrap to other lines at different breakpoints you may find large content in columns overlapping.

In order to preserve the structure of the columns within the row you'll need to apply classes to clear / unclear the floated columns.

######Example


`<div class = "grid_row">`<br>
`<div class = "grid_col_sm-1_2 grid_col_lg-1_4"></div>`<br>
`<div class = "grid_col_sm-1_2 grid_col_lg-1_4"></div>`<br>
`<div class = "grid_col_sm-1_2 grid_col_sm-clear_float grid_col_lg-1-4 grid_col_lg-reset_float"></div>`<br>
`<div class = "grid_col_sm-1_2 grid_col_lg-1-4"></div>`<br>
`</div>`<br>

When at the small breakpoint each column with take up 50% of the total width, meaning that two columns will wrap to the line below.

In order for the columns on the second line to acknowledge the frst line columns content we will apply a clear-float class for that breakpoint to the column that will first appear on the second line.

If, like in this example, we change the layout again at a higher breakpoint and want to return those columns to a single line we need to reverse clear floats class we applied earlier.  This can be achieved using a reset_float class.

<hr>

###Custom Grids

SCSS Mixins are available to allow construction of custom grids in addition to the base grid as describe above.


<hr>

##Responsive

By default all columns begin at 100% width and stack one on top the other until they hit a media query with a specified breakpoint at which point all columns are floated left and their appropriate widths are applied.

A set of four media queries have been added to get you going but the width values for each breakpoint can be changed in the variables scss file to fit your needs.



<hr>

##Features / Issues to fix

The current list of ongoing issues to fix or new features to add are:

<ul><li><del>Set up offset classes using a SCSS loop so that they can factor in the $columns variable ( Currently offset classes are declared manually with CSS ) to adapt to changes in column amounts.</del></li>
<li>Expand documentation on Custom grids with an example</li>
</ul>