# Grid

1. Use this [HTML file](grid/grid.html) and this [CSS file](grid/grid-styles.css). Create a stylesheet and link it in.

2. Specify that the `<main>` element should have `display: grid`. Does this affect the display at all?

## Defining the Grid

1. Now to define our grid. To specify the number and widths of columns, use `grid-template-columns`:

        grid-template-columns: 25% 50% 25%;

    Thus creates three columns with the sizes you specified.

2. Sizing with percentages is OK but a little cumbersome. We can use instead the `fr` (fraction) unit type that was created for CSS Grid.

    Change your column definition to this:

        grid-template-columns: 1fr 2fr 1fr;

    This defines each column width as a fraction of the total width available. The left column uses one fractional unit, ie one quarter of the available width.

3. View the page in a browser.

    1. Has the browser created any rows?
    2. What has happened to the content of your page?

## Defining a Column Gap

Having columns butt up close to each other is sometimes needed. In other cases, we may want to specify a gap:

      grid-column-gap: 10px;

## Placing Elements

To place an element on the grid, we just specify its location:

    .box1 {
      grid-column-start: 1;
      grid-column-end: 2;
      grid-row-start: 2;
      grid-row-end: 3;
    }

- A grid is defined in terms of "tracks", not columns. Tracks are the lines bordering a column, not the column itself.
- Tracks start from 1 (extreme left border of the grid).

Now place the following:

1. Place item "Two" in the center of the grid.
2. Place item "Three" at the bottom left, to occupy both left and center columns.
