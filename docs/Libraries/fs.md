# FS

The FileSystem library provides function to manipulate files and directories.

## Usage

```lua
local fs = require("fs")

-- Open a file in write mode
local handle = fs.open("foo", "w")

-- Write "Foo bar" to the file.
handle:write("Foo bar")

-- Close the file.
handle:close()
```

## Functions

### list

`fs.list`