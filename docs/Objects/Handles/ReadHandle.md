# ReadHandle

ReadHandle provides methods to read a stream of data.

## Methods

### readAll

`handle:readAll()`

Read stream to the end.

#### Returns

1. `content` : string | nil - Stream content. Returns `nil` if reached EOF.

### readLine

`handle:readLine()`

Read the stream until it reaches a newline character.

#### Returns

1. `line` : string | nil - Line content. Returns `nil` if reached EOF.

### read

`handle:read( [count] )`

Read `n` amount of characters.

#### Parameters

1. `count` : number = `1` - Amount of characters to read.

#### Returns

1. `data` : string | nil - Data read. `nil` if reached EOF.

### close

`handle:close()`

Close the stream handle.
