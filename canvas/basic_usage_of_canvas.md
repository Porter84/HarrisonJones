# Basic Usage of Canvas

## The Rendering Context

The ```<canvas>``` element creates a fixed-size drawing surface that exposes one or more **rendering contexts**, which are used to create and manipulate the content shown. The canvas is initially blank. To display something, a script first need to access the rendering context and draw on it. The ```<canvas>``` element has a method called ```getContext()```, used to obtain the rendering context and its drawing functions. The ```getContext()``` takes one parameter, the type of context. For 2D graphics you specify "2d" to get a ```CanvasRenderingContext2D```.

The first thing you want to do is getting a reference element from the page.

```javascript
// id
var canvas = document.getElementById('canvas');
```

```javascript
// tag
var canvas = document.getElementsByTagName('canvas')[0];
```

```javascript
// jQuery
var canvas = $('#canvas')[0];
```

Or creating a new one.

```javascript
// create
var canvas = document.createElement('canvas');
document.body.appandChild(canvas);
```

When you use this canvas reference, you can setup width and height via code, if you already done in the HTML, or if you want to change size for some reason. It will resize the bitmap itself, create a new bitmap with a new resolution, and cealring out any other drawing was on the canvas previously.

```javascript
// change size via code
var canvas = document.getElementById('canvas');
canvas.width = 400;
canvas.height = 400;
```

Never use for same reason jQuery, because this will chnage the style through CSS, and it can cause distortion issues on your canvas. It won't change the resolution of the canvas.

```javascript
// change size via code
var canvas = document.getElementById('canvas');
$('#canvas').width(400)                           // Dont't do that!!!
```

Finally you get a 2d rendering context, what you can use to drawing something. The context is where the magic happens.

```javascript
var canvas = document.getElementById('canvas');   // Retrieves the node from the DOM
var context = canvas.getContext('2d');            // Access the drawing context
```

```javascript
var canvas = document.getElementById('canvas');   // Retrieves the node from the DOM

if (canvas.getContext) {                          // Checking for support
  var context = canvas.getContext('2d');
  // drawing code
} else {
  // canvas-unsupported code here
}
```

## The Grid

The **canvas grid** is basically a **coordinate space**. Normally one unit in the grid corresponds to one pixel on the canvas. The origin of this grid is positioned in the top left corner at coordinate (0, 0). All elements are placed relative to this origin.

![Canvas drid](../images/canvas_grid.png)
