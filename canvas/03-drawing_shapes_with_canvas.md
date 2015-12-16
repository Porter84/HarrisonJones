# Drawing Shapes with Canvas

## Drawing Rectangles

Unlike ```<canvas>``` only support one primitive shape: rectangles. All other shapes must be created by combining one or more paths, lists of points connected by lines.

There are three functions that draw rectangles on the canvas:

Draws a filled rectangle:
```
fillRect(x, y, width, height)
```

Draws a rectangular outline:
```
strokeRect(x, y, width, height)
```

Clears the specified rectangular area, making it fully transparent:
```
clearRect(x, y, width, height)
```

## Drawing Paths

Another primitive is the path. A path is a list of points, connected by segments of lines that can be of different shapes, curved or not, of different width and of different color. A path or a subpath can be closed.
To making path takes these steps:
1. **Create path:** ```beginPath()``` creates a new path. Internally, paths are stored as a list of subpaths, which together form a shape. Every time this method is called, the list is reset and start drawing new shapes. When the current path is empty, or on a newly created canvas, the first path construction command is always treated as a ```moveTo()```. For that reason, you will almost always want to specifically set your starting position. You could also use ```moveTo()``` to draw unconnected paths.
2. **Use path commands:** The second step is calling the methods that actually specify the path to be drawn. ```moveTo()```, ```lineTo()```, ```bezierCurveTo()```, etc.
3. **Close the path:** The third and optional step, is to call ```closePath()``` method. It will try to close the shape with a line from the current point to the start point if it is possible, otherwise this function does nothing.
4. **Once the path has been created, render it with stroke or fill:** ```stroke()```, ```fill()```. When you call ```fill()```, any open shapes are closed automatically, so you don't have to call ```closePath()```.

## Drawing functions

- ```moveTo(x, y)```: Moves the pen to the coordinates specified by x and y.
- ```lineTo(x, y)```: Draws a line from the current drawing position to the position specified by x and y, so the arguments specified the line's ending point, and the starting point is dependent on previously drawn path.
- ```arc(x, y, radius, startAngle, endAngle, anticlockwise)```: Draws an arc which is centered at (x, y) position with radius, starting at startAngle and ending at andAngle going in the given direction indicated by anticlockwise (default to clockwise). Angles are measured in radians, not degrees. To convert degrees to radians you can use the following expression: ```radians = (Math.PI/180)*degrees```.
- ```arcTo(x1, y1, x2, y2, radius)```: Draws an arc with the given control points and radius, connected to the previous point by a straight line.
- ```quadraticCurveTo(cp1x, cp1y, x, y)```: Draws a quadratic Bezier curve from the current pen position to the end point specified by x and y. using the control point specified cp1x and cp1y.
- ```bezierCurveTo(cp1x, cp1y, cp2x, cp2y, x, y)```: Draws a cubic Bezier curve from the current pen position to the end point specified by x and y, using the control points specified by (cp1x, cp1y) and (cp2x, cp2y).
- ```rect(x, y, width, height)```: Draws a rectangle whos top-left corner is specified by (x, y) with the specified width and height. When this method is executed, the ```moveTo(x, y)``` method is automatically called.

## Path2D objects

To simplify the code and to improve performance, the ```Path2D``` object, available in recent versions of browsers, lets you cache or record these drawing commands.

```Path2D()```: The ```Path2D()``` constructor returns a newly instantiated ```Path2D``` object, optionally with another path as an argument (creates a copy), or optionally with a string consisting of SVG path data.

```
new Path2D();            // empty path object
new Path2D(path);        // copy from another Path2D object
new Path2D(d);           // path from SVG path data
```

All path methods (```moveTo()```, ```lineTo()```, ```bezierCurveTo()```, etc.) are available on ```Path2D``` objects.

The ```Path2D``` API also adds a way to combine paths using the ```addPath``` method. This can be useful when you want to vuild objects from several components.

```Path2D.addPath(path, [, transform])```: Add a path to the current path with an optional transformation matrix.

## Using SVG path

You can use SVG path data to initialize paths on your canvas.

```
var p = new Path2D('M10 10 h 80 v 80 h -80 Z');
```

The path will be move to point (M10 10) and then move horizontally 80 points to the right (h 80), then 80 points down (v 80), then 80 pionts to the left (h -80), and then back to the start (z).
