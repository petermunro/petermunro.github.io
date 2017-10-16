# Canvas

### Make a simple drawing program

1. Create an HTML page which includes a canvas element.
2. Write some JavaScript so that pressing the button in the canvas draws a rectangle.

Detailed steps:

1. First, add an empty canvas ‘mousedown’ handler:

``` javascript
document.getElementsByTagName('canvas')[0].addEventListener('mousedown', event => {

});
```

2. Inside the handler, use `this` (the canvas element the mouse was clicked on) to retrieve a 2-D drawing context:

``` javascript
let ctx = this.getContext('2d');
```

3. Set the fill style:

``` javascript
ctx.fillStyle = "rgba(0, 0, 200, 0.3)";
```

4. Finally, calculate the mouse position relative to the canvas, and draw the rectangle:

``` javascript
var x = e.pageX - $(this).position().left;
var y = e.pageY - $(this).position().top;
ctx.fillRect(x, y, 5, 5);
```

5. How would you modify this so that it paints as it follows the mouse (ie without clicking)?
