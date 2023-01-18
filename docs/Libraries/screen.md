# Screen

The Screen library is used to manipulate the window.

## Usage

```lua
local screen = require("screen")

local width, height = screen.getSize()
print(string.format("The screen size is %s by %s", width, height))
```

## Functions

### getSize

`screen.getSize()`

Get the size of the screen

#### Returns

1. `width` : integer - Width of screen
1. `height` : integer - Height of screen

### setSize

`screen.setSize()`

Set the size of the screen

#### Parameters

1. `width` : integer - Width of screen
2. `height` : integer - Height of screen

### getScale

`screen.getScale()`

Get the scale of the screen

#### Returns

1. `scale` : number - Scale of screen

### setScale

`screen.setScale()`

Set the scale of the screen

#### Parameters

1. `scale` : Number - Scale of screen