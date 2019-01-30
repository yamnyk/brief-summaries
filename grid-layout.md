##READ THIS TEXT FIRST

All of the information below is **only my personal opinion** that exist for quick access restore knowledge's about Grid Layout. 

##GRID LAYOUT
####Grid container properties
`display: grid` - initialize Grid Layout in this particular element;

######grid-template-columns 
Responsible for columns. All grid items will be located according this template

*Example:*

`grid-template-columns: 1fr 1fr 3fr` - means that it will be a three columns in grid, **first and second** will take **1fr** plce and **third** will take **2fr** place 

`grid-template-columns: repeat(6, 1fr)` - means that it will be **6 columns**, each of them **1fr width**

######grid-template-rows
Responsible for rows. All grid items will be located according this template.
**All syntax is just like in `grid-template-columns`**

######grid-template-areas
You can create column and row templates, then add a named area to each item. 

```css
.container {
  grid-template-columns: repeat(4,1fr); /*create column template with 4 columns 1fr width*/
  grid-template-rows: auto; /*leave rows height by content*/
  grid-template-areas: 
    "header header header header" /*item-a will place the whole row*/
    "main main . sidebar" /*item-b will place 1 and 2 grid columns, 3 grid column will be empty, sidebar will place 4 grid column*/
    "footer footer footer footer"; /**item-d will place the whole row/
}

.item-a {
  grid-area: header; /*stick "header" area to this element*/
}
.item-b {
  grid-area: main /*stick "main" area to this element*/;
}
.item-c {
  grid-area: sidebar;
}
.item-d {
  grid-area: footer;
}

```



