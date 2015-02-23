# Grid
A lightweight CSS responsive grid

A flexible and responsive 12 column grid system build in SCSS, compiled to CSS and designed to be a solid starting point to creating a grid system for your next web project.

##Basic Anatomy

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


####Offsetting



######Example

`<div class = "col-6-12 offset-3-12"></div>`

<hr>
