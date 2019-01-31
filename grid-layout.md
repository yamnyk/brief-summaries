## READ THIS TEXT FIRST

All of the information below is **only my personal opinion** that exist for quick access restore knowledge's about Grid Layout. 

## GRID LAYOUT
#### Grid container properties
`display: grid` - initialize Grid Layout in this particular element;

###### grid-template-columns 
Responsible for columns. All grid items will be located according this template

*Example:*

`grid-template-columns: 1fr 1fr 3fr` - means that it will be a three columns in grid, **first and second** will take **1fr** plce and **third** will take **2fr** place 

`grid-template-columns: repeat(6, 1fr)` - means that it will be **6 columns**, each of them **1fr width**

###### grid-template-rows
Responsible for rows. All grid items will be located according this template.
**All syntax is just like in `grid-template-columns`**

###### grid-template-areas
You can create column and row templates, then add a named area to each item. 

```css
.container {
  display: grid;    /*initialize grid*/
  grid-template-columns: repeat(4,1fr);     /*create column template with 4 columns 1fr width*/
  grid-template-rows: auto;  /*leave rows height by content*/
  grid-template-areas: 
    "header header header header"   /*item-a will place the whole row*/
    "main main . sidebar"   /*item-b will place 1 and 2 grid columns, 3 grid column will be empty, sidebar will place 4 grid column*/
    "footer footer footer footer"; /*item-d will place the whole row*/
}

.item-a {
  grid-area: header;    /*stick "header" area to this element*/
}
.item-b {
  grid-area: main   /*stick "main" area to this element*/;
}
.item-c {
  grid-area: sidebar;
}
.item-d {
  grid-area: footer;
}
```
###### grid-template
This is cinda shorthand for `grid-areas` + `grid-template-columns` + `grid-teplate-rows` properties.

*Example for same grid items as above*
```css
.container {
  display: grid; /*initialize grid*/
  grid-gap: 10px; /*space between cols and rows*/
  grid-template: 
    "header header main" auto /*auto - is part of grid-template-rows property*/
    "header header sidebar" 10% /*10% - is part of grid-template-rows property*/
    "header header sidebar" 10em /*10em - is part of grid-template-rows property*/
    ". footer footer" auto / 50% 1fr 2fr /*all writes after '/' is value of grid-template-columns property*/;
}

```

###### grid-gap, grid-column-gap, grid-row-gap
`grid-column-gap` - response for space between each column

`grid-row-gap` - response for space between each row

`grid-gap` - is a shorthand for this two properties and its value will applied to both of them

###### justify-items
`justify-items: start | end | center | stretch` - align grid items along row axis (horizontally) in each grid cell

`stretch` - fills the whole width of the cell.

*Example*
```css
.container {
    justify-items: center; /*means that each grid item will be placed in the center of the each grid cell*/
}
```

###### align-items
Doing same job as `justify items`, but in opposite axis - **vertically**.

*Example*
```css
.container {
    align-items: end; /*means that each grid item will be placed in the center of the each grid cell*/
}
```

###### place-items
`place-items` sets both the `align-items` and `justify-items` properties in a single declaration.

###### justify-content
`justify-content: start | end | center | stretch | space-around | space-between | space-evenly;`
response for **placement of grid cells** relative to grid container **horisontally**

###### align-content
`align-content: start | end | center | stretch | space-around | space-between | space-evenly;`
response for **placement of grid cells** relative to grid container **vertically**

###### place-content
`place-content` sets both the `align-content` and `justify-content` properties in a single declaration.

###### grid-auto-columns, grid-auto-rows, grid-auto-flow
`grid-auto-columns: <length> | <percentage> | fr | max-content | min-content | minmax(min, max) | fit-content(value) | auto | <multiple track-size values>` - response for width of implicit grid. **Implicit grid** - grid for elements who didn't fit in define template. [Click to read more. This article has perfect description (RUS)](https://abraxabra.ru/blog/css/css-grid-a-detailed-guide-with-examples-gridam/)

Same thing with `grid-auto-rows` property but it works in **vertical** direction.

*Example:*

```css
.container {
    grid-auto-columns: fit-content(200px) 20% 1fr; 
}
```

```css
.container {
    display: grid;
    grid-auto-columns: fit-content(200px); 
}

.item-a {
    grid-column: 1;
}

.item-b {
    grid-column: 2;
}

.item-c {
    grid-column: 3;
}
```

`fit-content(value)` - means that content size inside grid item will fit specified width

`grid-auto-flow: row | column | row dense | column dense` - cinda `flex-direction`... response how the grid will be filled with items. Keyword `dense` - means fill free grid space with grid items --> it can cause an issues with order of elements

###### grid

A shorthand for setting all of the following properties in a single declaration: grid-template-rows, grid-template-columns, grid-template-areas, grid-auto-rows, grid-auto-columns, and grid-auto-flow

```css
.container {
    grid: auto-flow dense 100px / 1fr 2fr;
}
/**** S A M E  A S *****/  
.container {
    grid-auto-flow: row dense;
    grid-auto-rows: 100px;
    grid-template-columns: 1fr 2fr;
}


.container {
    grid: 100px 300px / auto-flow 200px;
}
/**** S A M E  A S *****/  
.container {
    grid-template-rows: 100px 300px;
    grid-auto-flow: column;
    grid-auto-columns: 200px;
}
```

