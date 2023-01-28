# Term

The Term library is used to emulate a terminal.

## Usage

```lua
local term = require("term")

term.setPos(1, 1)
term.clearLine()
term.write("Hello, World!")
```

## Functions

### write

`write( text )`

Write a string to the terminal.

#### Parameters

1. `text?` : string - Text to write on terminal

### getPos

`getPos()`

Get the cursor position.

Coordinates start from 1, 1.

#### Returns

1. `x` : integer - X coordinate
2. `y` : integer - Y coordinate

### setPos

`setPos( x, y )`

Set the cursor position.

Coordinate start from 1,1.

#### Parameters

1. `x` : number - X coordinate
2. `y` : number - Y coordinate

### getSize

`getSize()`

Get the size of the terminal.

#### Returns

1. `width` :  integer - Width of the terminal
2. `height` : integer - Height of the terminal

### setSize

`setSize( width, height )`

Set the size of the terminal.

#### Parameters

1. `width` : number - Width of the terminal
2. `height` : number - Height of the terminal

### getForeground

`getForeground()`

Get the decimal RGB value of the current text color.

#### Returns

1. `rgb` : integer - Decimal RGB value

### setForeground

`setForeground( r, g, b )` or `setForeground( rgb )`

Set the text color.

#### Parameters

Values range from 0 to 255.

1. `r` : integer - Red value
2. `g` : integer - Green value
3. `b` : integer - Blue value

##### OR

Value is hex color 0xRRGGBB (e.g. `0xff7700`).

1. `rgb` : integer - Decimal value of RGB combined.

### getBackground

`getBackground()`

Get the decimal RGB value of the current background color.

#### Returns

1. `rgb` : integer - Decimal RGB value

### setBackground

` setBackground( r, g, b )` or`setBackground( rgb )`

Set the background color.

#### Parameters

Values range from 0 to 255.

1. `r` : integer - Red value
2. `g` : integer - Green value
3. `b` : integer - Blue value

##### OR

Value is hex color 0xRRGGBB (e.g. `0xff7700`).

1. `rgb` : integer - Decimal value of RGB combined.

### clear

`clear()`

Wipes the terminal and set the background to the current set.

### clearLine

`clearLine()`

Like `clear()` but only clears the horizontal line of the cursor position.

### scroll

`scroll( lines )`

Scroll the terminal by `n` lines.

Lines that go out of bounds are lost.

#### Parameters

1. `lines` : integer - Lines to scroll

### getBlink

`getBlink()`

Get the status of the cursor blink.

#### Returns

1. `isBlinking` : boolean - Whether it is blinking.

### setBlink

`setBlink( enable )`

Set the status of the cursor blink.

#### Parameters

1. `enable` : boolean - Whether to blink.

### toRealPos

`toRealPos( x, y )`

Convert from terminal coordinates to screen coordinates.

#### Parameters

1. `x` : number - X coordinate of terminal
2. `y` : number - Y coordinate of terminal

#### Returns

1. `x` : integer - X coordinate of screen
2. `y` : integer - Y coordinate of screen

### fromRealPos

`fromRealPos( x, y )`

Convert from screen coordinates to terminal coordinates.

**Use this function to convert mouse event positions relative to terminal**

#### Parameters

1. `x` : number - X coordinate of screen
2. `y` : number - Y coordinate of screen

#### Returns

1. `x` : integer - X coordinate of terminal
2. `y` : integer - Y coordinate of terminal