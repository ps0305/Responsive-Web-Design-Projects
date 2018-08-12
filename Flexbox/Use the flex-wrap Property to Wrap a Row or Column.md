CSS flexbox has a feature to split a flex item into multiple rows (or columns). 
By default, a flex container will fit all flex items together. For example, a row will all be on one line.

However, using the flex-wrap property, it tells CSS to wrap items. 
This means extra items move into a new row or column. 
The break point of where the wrapping happens depends on the size of the items and the size of the container.

CSS also has options for the direction of the wrap:

* nowrap: this is the default setting, and does not wrap items.

* wrap: wraps items from left-to-right if they are in a row, or top-to-bottom if they are in a column.

* wrap-reverse: wraps items from bottom-to-top if they are in a row, or left-to-right if they are in a column.


The current layout has too many boxes for one row. 
Add the CSS property `flex-wrap` to the #box-container element, and give it a value of wrap.

```js
<style>
  #box-container {
    background: gray;
    display: flex;
    height: 100%;
    flex-wrap: wrap;
      
  }
  #box-1 {
    background-color: dodgerblue;
    width: 25%;
    height: 50%;
  }

  #box-2 {
    background-color: orangered;
    width: 25%;
    height: 50%;
  }
  #box-3 {
    background-color: violet;
    width: 25%;
    height: 50%;
  }
  #box-4 {
    background-color: yellow;
    width: 25%;
    height: 50%;
  }
  #box-5 {
    background-color: green;
    width: 25%;
    height: 50%;
  }
  #box-6 {
    background-color: black;
    width: 25%;
    height: 50%;
  }
</style>

<div id="box-container">
  <div id="box-1"></div>
  <div id="box-2"></div>
  <div id="box-3"></div>
  <div id="box-4"></div>
  <div id="box-5"></div>
  <div id="box-6"></div>
</div>
