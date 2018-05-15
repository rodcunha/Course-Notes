# CSS Grid Notes

## What is CSS Grid

CSS grid is a relatively new CSS layout technique that allows us to define columns and rows directly in the CSS without the use of an external framework.

## How to use CSS grid

### Defining the Grid

In order to define a container as a grid, you will need to use:

```css
.container {
  display: grid;
}
```

The above command will display the container as a grid. In order to add columns or rows we will need to define them. By default the browser will interpret the grid as being one column.

### Defining the columns

```css
.container {
  display: grid;
  grid-template-columns: 100px 100px 100px;
}
```

In the example above we define a grid element with 3 columns. We can use any valid CSS units to define the column length but a good practice in responsive design is to use fraction units `fr` to define the length.

We can also use `auto` sizing, meaning that the content of the element will defacto determine the size of the grid element (and subsequent elements in that column/row).

#### Using repeat()

We can define columns by giving them their individual values like so:

```css
.container {
  display: grid;
  grid-template-columns: 100px 100px 100px;
}
```
But what if we want to define say 10 columns, this quickly becomes tedious. Fortunately, the nice people that created this, gave us an option to quickly add columns. Queue in the repeat function.

To achieve the same layout as above we would then write:

```css
.container {
  display: grid;
  grid-template-columns: repeat(3, 100px);
}
```
You can also use repeat with more than one value, for instance: `grid-template-columns: repeat(6, 1fr 2fr);`. This will alternate columns between 1 fraction and 2 fractions of the available space in the container 6 times.

We can use the repeat function anywhere in the declaration it doesn't need to be standalone for example this is a valid CSS statement:

```css
.container {
  display: grid;
  grid-template-columns: 100px repeat(3, 100px) 200px 1fr 2rem;
}
```

### Sizing 

### span

We can define the width of a column by using the `span` directive on an item. Let's imagine we have a series of `div` elements and we want one of them to be twice the width of the rest. We could achieve that by:

```css
.item2 {
  grid-column: span 2;
}
``` 
This would make the item with `class="item2"` to span the width of 2 columns. We can add more width by increasing the number and make it span more columns.

In order to span rows, we could use the `grid-row: span 2;` css directive.

**Note: ** if the width of the column is greater than the width available the item will wrap onto the next row and leave a gap unless the dense option is used.


### Adding space between grid elements

In order to add space between grid element we will need to use `grid-gap` as such:

```css
.container {
  grid-gap: 10px;
}
```

This will add a `10px` spacing between the grid elements, both columns and rows. In order to define the gaps just for columns or rows, we can use `grid-column-gap` or `grid-row-gap` instead.

