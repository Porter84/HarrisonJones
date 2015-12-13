# Canvas HTML Element

## Basics

The canvas element can be used to draw graphics, make photo compositions or perform animations via scripting, usually JavaScript. You should provide alternative content inside the canvas block. That alternative content will be rendered on older browsers that don't support canvas and in browser with JavaScript disabled.

## Attributes

- Global attributes
- height: the height of the coordinate space in CSS pixels. Defaults to 150.
- width: the width of the coordinate space in CSS pixels. Defaults to 300.
- moz-opaque: lets the canvas know wheter or not translucency will be a factor. If the canvas knows there's no translucency, painting performance can be optimized. Only works in Mozilla-based rendering engines.

## Other

- HTML 5: It is an HTML 5 tag thats need to use HTML 5 doctype: <!DOCTYPE html>
- required closing tag: unlike the <img> element, the <canvas> element requires the closing tag </canvas>
- sizing: a canvas is basicly a bitmap image with rows and columns with pixels, when you setup the width and heigh in the canvas tag, you specify the actual resolution of that bitmap. The canvas can be changed using a stylsheet, but if you use CSS bitmap of canvas will scaled during rendering to fit the styled size. If your renderings seem distorted, try specifying your width and hieght attributes explicitly in the <canvas> attributes, and not using CSS.

## Examples

- Default sizing

```
<!-- defualt sizing 300x150 -->
<canvas id="canvas">
  Sorry, your browser doesn't support the canvas element.
</canvas>
```

- using attributes for sizing

```
<!-- using attributes for sizing -->
<canvas id="canvas" width="300" height="400">
  Sorry, your browser doesn't support the canvas element.
</canvas>
```

- If your canvas does not use transparency set moz-opaque attribute on the canvas tag. This information can be used internally to optimize rendering.

```
<!-- transparency -->
<canvas id="canvas" moz-opaque>
  Sorry, your browser doesn't support the canvas element.
</canvas>
```
