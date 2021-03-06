# ColorWheel
ESModule for rendering color wheels

Basically, I hate that browsers have different color pickers on different OSes.

![demo 0 - image](./example.png)

Take a look at the demo code:
[demo 0](./index.js)

Take a look at the output:
[demo 0 - visual](https://repcomm.github.io/colorwheel)

[demo 1 - visual](https://repcomm.github.io/colorwheel/examples/example-chaining.html)

Usage is fairly simple:

Creating the wheel
```javascript
let myWheel = new ColorWheel()
```

Adding & removing colors
```javascript
let red = WheelColor.fromRGB(255, 0, 0);
myWheel.addColor(red);
myWheel.removeColor(red);
```

Appending it to the dom
```javascript
myWheel.mount( myDiv );
//mount accepts an html or Component class (see component.js)

//Similar to
div.appendChild ( myWheel.element )
```

Helper functions that make life easy
```javascript
  //Handle window resizing
  .handleResize()

  //Auto render when state changes
  .handleRedrawLoop()

  //Applies 100% to width and height of canvas element
  .fillParentSize();
```

Color picking
```javascript
  .handleColorPicking()
  .on("color-pick", (color)=>{
    container.style["border-color"] = `rgb(${color.toString()})`;
  })
```