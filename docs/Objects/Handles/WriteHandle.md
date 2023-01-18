# WriteHandle

WriteHandle provides methods to write data to a stream.

## Methods

### write

`handle:write( data )`

Write data to the stream.

#### Parameters

1. `content` : string - Data to write.

### writeLine

`handle:writeLine( data )`

Write data to the stream and append a newline character.

#### Parameters

1. `content` : string - Data to write.

### flush

`handle:flush()`

Flush stream.

In case of file handles, this method applies the changes to the disk.

### close

`handle:close()`

Close the stream handle.
