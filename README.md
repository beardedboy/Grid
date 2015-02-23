# Grid
A lightweight CSS responsive grid

A flexible responsive yet grid system build in SCSS, compiled to CSS and designed to be a solid starting point to creating a grid system for your next web project.

##Basic Usage

###Container
All of the main content should be wrapped in a div with the 'container' class. The width of the container can be altered in a SCSS variable and all child elements ( mostly likely the rows declared within the container ) max-widths are governed by this.

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

I have decided not to declare any padding to the columns themselves as this has caused issues with uneven width when nesting columns ( more on nesting below ).  Instead each column needs to include a div with a 'col-content' class.


<hr>
