# Basic Usage of Canvas

## The Rendering Context

The ```<canvas>``` element creates a fixed-size drawing surface that exposes one or more **rendering contexts**, which are used to create and manipulate the content shown. The canvas is initially blank. To display something, a script first need to access the rendering context and draw on it. The ```<canvas>``` element has a method called ```getContext()```, used to obtain the rendering context and its drawing functions. The ```getContext()``` takes one parameter, the type of context. For 2D graphics you specify "2d" to get a ```CanvasRenderingContext2D```.

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
