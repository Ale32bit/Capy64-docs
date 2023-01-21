# GPU

The GPU library is used to manipulate and draw on the screen.

## Usage

```lua
local gpu = require("gpu")

-- Draw a magenta rectangle starting at 10, 15
-- of size 27x65 with a border size of 4 pixels
gpu.drawRectangle(10, 15, 27, 65, 0xff00ff, 4)

local width, height = gpu.getSize()
print(string.format("The screen size is %s by %s", width, height))
```

!!! Warning
    All coordinates start from 1, 1

## Functions

### getSize

`gpu.getSize()`

Get the size of the screen

#### Returns

1. `width` : integer - Width of screen
1. `height` : integer - Height of screen

### setSize

`gpu.setSize()`

Set the size of the screen

#### Parameters

1. `width` : integer - Width of screen
2. `height` : integer - Height of screen

### getScale

`gpu.getScale()`

Get the scale of the screen

#### Returns

1. `scale` : number - Scale of screen

### setScale

`gpu.setScale()`

Set the scale of the screen

#### Parameters

1. `scale` : Number - Scale of screen

### getPixel

`gpu.getPixel( x, y )`

Get the color of pixel at X,Y.

The color returned is black (#000000) if out of bounds.

#### Parameters

1. `x` : number - X coordinate.
2. `y` : number - Y coordinate.

#### Returns

1. `color` : integer - Decimal RGB color.

### plot

`#!lua gpu.plot( x, y, color )`

Draw a pixel on the screen.

#### Parameters

1. `x` : number - X coordinate.
2. `y` : number - Y coordinate.
3. `color` : integer - Decimal RGB color.

### plots

`#!lua gpu.plots( { x1, y1, x2, y2, ..., xn, yn}, color )`

Draw multiple pixels on the screen.

#### Parameters

1. `coordinates` : number[] - Table containing pairs of coordinates.
2. `color` : integer - Decimal RGB color.

#### Throws

* If the `coordinates` table length is not even.
* If the `coordinates` table contains anything but numbers.

### drawPoint

`#!lua gpu.drawPoint( x, y, color, size? = 1)`

Draw a square point.

#### Parameters

1. `x` : number - X coordinate.
2. `y` : number - Y coordinate.
3. `color` : integer - Decimal RGB color.
4. `size` : number - Size of the pixel. Defaults to 1.

### drawCircle

`#!lua gpu.drawCircle( x, y, radius, color, size? = 1 )`

Draw a circle.

#### Parameters

1. `x` : number - X coordinate.
2. `y` : number - Y coordinate.
3. `radius` : numbeer - Radius of the circle.
4. `color` : integer - Decimal RGB color.
5. `size` : number - Border size.

### drawLine

`#!lua gpu.drawLine( startX, startY, endX, endY, color, size? = 1 )`

Draw a line.

#### Parameters

1. `startX` : number - Start X coordinate.
2. `startY` : number - Start Y coordinate.
3. `endX` : number - End X coordinate.
4. `endY` : number - End Y coordinate.
5. `color` : integer - Decimal RGB color.
6. `size` : number - Thickness.

### drawRectangle

`#!lua gpu.drawRectangle( x, y, width, height, color, size? = 1 )`

Draw a rectangle.

!!! Tip
    Setting border size to the smallest of width or height fills the rectangle.

#### Parameters

1. `x` : number - X coordinate.
2. `y` : number - Y coordinate.
3. `width` : number - Width.
4. `height` : number - Height.
5. `color` : integer - Decimal RGB color.
6. `size` : number - Border size.

### drawPolygon

`#!lua gpu.drawPolygon( x, y, { x1, y1, x2, y2, ..., xn, yn}, color, size? = 1 )`

Draw a polygon.

#### Parameters

1. `x` : number - X coordinate.
2. `y` : number - Y coordinate.
3. `points` : number[] - Table containing pairs of coordinates to indicate the points.
4. `color` : integer - Decimal RGB color.
5. `size` : number - Border size.

#### Throws

* If the `points` table length is not even.
* If the `points` table contains anything but numbers.

### drawEllipse

`#!lua gpu.drawEllipse( x, y, radiusX, radiusY, color, size? = 1 )`

Draw an ellipse.

#### Parameters

1. `x` : number - X coordinate.
2. `y` : number - Y coordinate.
3. `radiusX` : number - Radius of X coordinate.
4. `radiusY` : number - Radius of Y coordinate.
5. `color` : integer - Decimal RGB color.
6. `size` : number - Border size.

### drawString

`#!lua gpu.drawString( x, y, color, text )`

Draw a string.

#### Parameters

1. `x` : number - X coordinate.
2. `y` : number - Y coordinate.
3. `color` : integer - Decimal RGB color.
4. `text` : string - Text to draw.

### measureString

`#!lua gpu.measureString( text )`

Get the bounds of the string.

#### Parameters

1. `text` : string - Text to measure.

#### Returns

1. `width` : number - Width of the text.
2. `height` : number - Height of the text.

### getBuffer

`gpu.getBuffer()`

Get a unsigned 32-bit integer buffer of all colors in the screen in 0xRRGGBB format.

#### Returns

1. `gpuBuffer` : [GPUBuffer](/Objects/GPUBuffer/) - GPU Buffer

### setBuffer

`gpu.setBuffer( gpuBuffer )`

Set the screen buffer.

#### Parameters

1. `gpuBuffer` : [GPUBuffer](/Objects/GPUBuffer/) - GPU Buffer

### newBuffer

`gpu.newBuffer()`

Create a new empty buffer.

The buffer is already sized for the current screen size.

#### Returns

1. `gpuBuffer` : [GPUBuffer](/Objects/GPUBuffer/) - Empty GPU Buffer
