The last challenge introduced the animation-timing-function property and a few keywords that change the speed of an animation over its duration. 
CSS offers an option other than keywords that provides even finer control over how the animation plays out, 
through the use of Bezier curves.

In CSS animations, `Bezier` curves are used with the `cubic-bezier` function. 
The shape of the curve represents how the animation plays out. 
The curve lives on a 1 by 1 coordinate system. 
* The X-axis of this coordinate system is the duration of the animation (think of it as a time scale), 
and the 
* Y-axis is the change in the animation.

The cubic-bezier function consists of four main points that sit on this 1 by 1 grid: `p0, p1, p2, and p3`. `p0 and p3` are set for you - 
they are the beginning and end points which are always located respectively at the origin (0, 0) and (1, 1). 
You set the x and y values for the other two points, 
and where you place them in the grid dictates the shape of the curve for the animation to follow. 
This is done in CSS by declaring the x and y values of the p1 and p2 "anchor" points in the form: (x1, y1, x2, y2). 
Pulling it all together, here's an example of a Bezier curve in CSS code:
```html
animation-timing-function: cubic-bezier(0.25, 0.25, 0.75, 0.75);
```

In the example above, the x and y values are equivalent for each point `(x1 = 0.25 = y1 and x2 = 0.75 = y2)`, 
which if you remember from geometry class, results in a line that extends from the origin to point (1, 1). 
This animation is a linear change of an element during the length of an animation, 
and is the same as using the linear keyword. In other words, it changes at a constant speed.

```html
<style>

  .balls{
    border-radius: 50%;
    background: linear-gradient(
      35deg,
      #ccffff,
      #ffcccc
    );
    position: fixed;  
    width: 50px;
    height: 50px;
    margin-top: 50px;
    animation-name: bounce;
    animation-duration: 2s;
    animation-iteration-count: infinite;
  }
  #ball1 { 
    left: 27%;
    animation-timing-function: cubic-bezier(0.25, 0.25, 0.75, 0.75);
  }
  #ball2 { 
    left: 56%;
    animation-timing-function: ease-out;
  }

@keyframes bounce {
  0% {
    top: 0px;
  } 
  100% {
    top: 249px;
  }
} 

</style>

<div class="balls" id="ball1"></div>
<div class="balls" id="ball2"></div>
```

In general, changing the p1 and p2 anchor points drives the creation of different Bezier curves, which controls how the animation progresses through time. Here's an example of a Bezier curve using values to `mimic the ease-out` style:
```html
animation-timing-function: cubic-bezier(0, 0, 0.58, 1);
```
Remember that all cubic-bezier functions start with p0 at (0, 0) and end with p3 at (1, 1). 
In this example, the curve moves faster through the Y-axis (starts at 0, goes to p1 y value of 0, then goes to p2 y value of 1) than it moves through the X-axis (0 to start, then 0 for p1, up to 0.58 for p2). 
As a result, the change in the animated element progresses faster than the time of the animation for that segment. 
Towards the end of the curve, the relationship between the change in x and y values reverses - the y value moves from 1 to 1 (no change), and the x values move from 0.58 to 1, making the animation changes progress slower compared to the animation duration.

```html
<style>
  .balls{
    border-radius: 50%;
    position: fixed;
    width: 50px;
    height: 50px;
    margin-top: 50px;
    animation-name: bounce;
    animation-duration: 2s;
    animation-iteration-count: infinite;
  }
  #red {
    background: red;
    left: 27%;
    animation-timing-function: cubic-bezier(0, 0, 0.58, 1);
  }
  #blue {
    background: blue;
    left: 56%;
    animation-timing-function: ease-out;
  }
  @keyframes bounce {
    0% {
      top: 0px;
    }
    100% {
      top: 249px;
    }
  }
</style>
<div class="balls" id= "red"></div>
<div class="balls" id= "blue"></div>
```
The animation-timing-function automatically loops at every keyframe when the animation-iteration-count is set to infinite. 
Since there is a keyframe rule set in the middle of the animation duration (at 50%), 
it results in two identical animation progressions at the upward and downward movement of the ball.

The following cubic Bezier curve simulates a `juggling movement`:
```html
cubic-bezier(0.3, 0.4, 0.5, 1.6);
```
Notice that the value of y2 is larger than 1. 
Although the cubic Bezier curve is mapped on an 1 by 1 coordinate system, 
and it can only accept x values from 0 to 1, the y value can be set to numbers larger than one. 
This results in a bouncing movement that is ideal for simulating the juggling ball.
```html
<style>
  .balls {
    border-radius: 50%;
    position: fixed;  
    width: 50px;
    height: 50px;
    top: 60%;
    animation-name: jump;
    animation-duration: 2s;
    animation-iteration-count: infinite;
  }
  #red {
    background: red;
    left: 25%;
    animation-timing-function: linear;
  }
  #blue {
    background: blue;
    left: 50%;
    animation-timing-function: ease-out;
  }
  #green {
    background: green;
    left: 75%;
    animation-timing-function: cubic-bezier(0.311, 0.441, 0.444, 1.649);
  }

  @keyframes jump {
    50% {
      top: 10%;
    }
  }
</style>
<div class="balls" id="red"></div>
<div class="balls" id="blue"></div>
<div class="balls" id="green"></div>
