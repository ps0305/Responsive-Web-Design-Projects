The `align-items` property is similar to `justify-content`. 
Recall that the `justify-content` property aligned flex items along the main axis. 
For rows, the main axis is a horizontal line and for columns it is a vertical line.

Flex containers also have a `cross axis` which is the opposite of the `main axis`. 
For rows, the `cross axis` is vertical and for columns, the cross axis is horizontal.

CSS offers the align-items property to align flex items along the `cross axis`. 
For a row, it tells CSS how to push the items in the entire row up or down within the container. 
And for a column, how to push all the items left or right within the container.

The different values available for `align-items` include:

* flex-start: aligns items to the start of the flex container. For rows, this aligns items to the top of the container. 
For columns, this aligns items to the left of the container.

* flex-end: aligns items to the end of the flex container. For rows, this aligns items to the bottom of the container. 
For columns, this aligns items to the right of the container.

* center: align items to the center. For rows, this vertically aligns items (equal space above and below the items). 
For columns, this horizontally aligns them (equal space to the left and right of the items).

* stretch: stretch the items to fill the flex container. For example, rows items are stretched to fill the flex container top-to-bottom.

* baseline: align items to their baselines. Baseline is a text concept, think of it as the line that the letters sit on.


An example helps show this property in action. 
Add the CSS property `align-items` to the` #box-container` element, and give it a value of center.

