# Grid
A lightweight CSS responsive grid

A flexible and responsive 12 column grid system build in SCSS, compiled to CSS and designed to be a solid starting point to creating a grid system for your next web project.

##Basic Anatomy

###Container
All of the main content should be wrapped in a div with the 'container' class. The width of the container can be altered in a SCSS variable and all child elements ( mostly likely the rows declared within the container ) max-widths are restrained by this.

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
`<div class = "col-2-12"></div>`<br>

I have decided not to declare any padding to the columns themselves as this has caused issues with uneven widths when nesting columns ( more on nesting later ).  Instead each column needs to include a div with a 'col-content' class.  The actual columns content will be placed within this div.


######Example

`<div class = "col-6-12"><div class = "col-content">content goes here</div></div>`


####Layout Columns

Layout columns widths are defined as x columns out of 12.  Ranging from 1 column out of 12 occupying just 1/12th of the width of a row upto 12 columns out of 12 occupying 100% the width of a row.

######Example

`<div class = "col-6-12"></div>`<br>
`<div class = "col-4-12"></div>`<br>
`<div class = "col-2-12"></div>`<br>


####Content Columns

Content columns are divided equally by 100% and are represented by an appropriate fraction.  Splitting the total width equally ranging from two halves ( 50 / 50) and labelling the classe as 'col-1-2' to signify 1/2 ( One half ) through to splitting it into twelve equal parts and labelling the class 'col-1-12'.

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


####Ratio Columns

Using the ratio variable specified in the SCSS, a set of columns are constructed based on this ratio that can used.  Using the golden ratio (1.618) for example will result in two columns being create that are split according to this ratio ( 61.8 / 38.2 split). 

Columns spacing are based on the input ratio value as well to keep the layout to the same scale.

######Example

`<div class = "col-ratio-2-3"></div>`<br>
`<div class = "col-ratio-1-3"></div>`<br>

<hr>

###Offsetting

Additional classes can be added to a column to allow that column to be offset from the left of the screen by the specified increment.

In the example below, a col-6-12 would extend to 50% the width of the row it's in and would usually begin on the left side of its container. However an offset class of 3-12 has been added, effectively shifting the columns right by 25%, resulting in a centrally positioned column.

######Example

`<div class = "col-6-12 offset-3-12"></div>`

<hr>

###Nesting

Grids can be nested within others and in conjuction with offsetting can allow more complicated grid systems to be constructed.

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

Grids can be nested within others and in conjuction with offsetting can allow more complicated grid systems to be constructed.

Each new set of nested columns should be nested within a 'row' classed container.


######Example

<hr>

##Responsive

By default all columns begin at 100% width and stack one on top the other until they hit a media query with a breakpoint of 50em( initally set within a SCSS variable) at which point all columns are floated left and their appropriate widths are applied.

A set of four media queries have been added to get you going but their contents have been left empty on purpose to allow you to alter the widths of the responsive grid on a per project basis.

<hr>

##Issues to fix

The current list of ongoing issues to fix are:

*Set up offset classes using a SCSS loop so that they can factor in the $columns variable ( Currently offset classes are declared manually with CSS ) to adapt to changes in column amounts.