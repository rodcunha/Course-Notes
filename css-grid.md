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

### Adding space between grid elements

In order to add space between grid element we will need to use `grid-gap` as such:

```css
.container {
  grid-gap: 10px;
}

This will add a `10px` spacing between the grid elements, both columns and rows. In order to define the gaps just for columns or rows, we can use `grid-column-gap` or `grid-row-gap` instead.
