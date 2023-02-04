# FileSystem

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

### open

`fs.open( path, mode )`

Open a file handle.

#### Parameters

1. `path` : string - Path of the file to open.
2. `mode` : string - How to open the file.

#### Returns

If `mode` is `"r"`:

1. [ReadHandle](/Objects/Handles/ReadHandle/)

If `mode` is `"w"` or `"a"`:

1. [WriteHandle](/Objects/Handles/WriteHandle/)

If `mode` is `"rb"`:

 1. [BinaryReadHandle](/Objects/Handles/BinaryReadHandle/)

If `mode` is `"wb"` or `"ab"`:

1. [BinaryWriteHandle](/Objects/Handles/BinaryWriteHandle/)

### list

`fs.list( path )`

Get an array containing files and directories in a path.

#### Parameters

1. `path` : string - Path of the directory to list.

#### Returns

1. `list` : string[] - List of files and directories.

#### Throws

* If the directory is not found.

### combine

`fs.combine( ...path )`

Combine and resolves path segments together.

#### Parameters

1. `...path` : string - Path segment.

#### Returns

1. `path` : string - Combined path.

### getName

`fs.getName( path )`

Get the name of the path.

#### Example

```lua
local path = "foo/bar/hello.lua"

print(fs.getName(path))
-- Output:
-- hello.lua
```

#### Parameters

1. `path` : string - Path.

#### Returns

1. `name` : string - Name of path.

### getDir

`fs.getDir( path )`

get the name of the directory in path.

```lua
local path = "foo/bar/hello.lua"

print(fs.getDir(path))
-- Output:
-- bar
```

#### Parameters

1. `path` : string - Path.

#### Returns

1. `name` : string - Name of directory in path.

### getSize

`fs.getSize( path )`

Get the file size in bytes.

#### Parameters

1. `path` : string - Path.

#### Returns

1. `size` : number - Size of file in bytes.

### exists

`fs.exists( path )`

Check whether a path exists.

#### Parameters

1. `path` : string - Path.

#### Returns

1. `exists` : boolean - Whether it exists.

### isReadOnly

`fs.isReadOnly( path )`

Check if a file or directory is read-only.

#### Parameters

1. `path` : string - Path.

#### Returns

1. `isReadOnly` : boolean - Whether it is read only.

### makeDir

`fs.makeDir( path )`

Create a new directory.

#### Parameters

1. `path` : string - Path.

### move

`fs.move( source, destination )`

Move a file or directory from a source to a destination path.

#### Parameters

1. `source` : string - Source path.
2. `destination` : string - Destination path.

### copy

`fs.copy( source, destination )`

Copy a file from source to a destination path.

#### Parameters

1. `source` : string - Source path.
2. `destination` : string - Destination path.

### delete

`fs.delete( path, [ recursive ] )`

Delete a path. Enable `recursive` to delete a directory with files.

#### Parameters

1. `path` : string - Path to delete.
2. `recursive` : boolean - Delete path recursively.

### attributes

`fs.attributes( path )`

Get attributes of a path.

#### Parameters

1. `path` : string - Path.

#### Returns

1. `attributes` : table - Table containing attributes of the path.
   1. `size` : number - Size of file. 0 if directory.
   2. `isDirectory` : boolean - Whether the path is a directory.
   3. `isReadOnly` : boolean - Whether the path is read only.
   4. `created` : integer - Timestamp of creation date of the path.
   5. `modified` : integer - Timestamp of last modified date of the path.

### isDir

`fs.isDir( path )`

Check whether a path is a directory

#### Parameters

1. `path` : string - Path.

#### Returns

1. `isDirectory` : boolean - Whether there is a directory in the path.
