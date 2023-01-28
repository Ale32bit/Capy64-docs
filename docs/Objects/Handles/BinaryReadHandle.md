# BinaryReadHandle

BinaryReadHandle provides methods to read a stream of binary data.

## Methods

!!! Warning
	The following methods will return `nil` if the EOF is reached.

### readAll

`handle:readAll()`

Read all data from current position to the end of file.

#### Returns

1. `data` : string - File data

### seek

`handle:seek( [whence [, offset]] )`

Change the position of the stream.

#### Parameters

1. `whence` : string - The position moves relative to
   * `set`: From the start of the file (absolute).
   * `cur`: From the current position, is default.
   * `end`: From the end of the file.
2. `offset` : integer - Offset of the new position relative to whence. Defaults to 0.

#### Returns

1. `position` : integer - New position.

### nextByte

`handle:nextByte( [count] )`

Get the next `n` bytes.

#### Parameters

1. `count` : number = `1` - Amount of bytes to read.

#### Returns

1. `...data` : integer - Unsigned bytes read.

### nextShort

`handle:nextShort()`

Get the next short integer.

#### Returns

1. `value` : integer - 16-bit signed integer.

### nextInt

`handle:nextInt()`

Get the next integer.

#### Returns

1. `value` : integer - 32-bit signed integer.

### nextLong

`handle:nextLong()`

Get the next long integer.

#### Returns

1. `value` : integer - 64-bit signed integer.

### nextSByte

`handle:nextSByte()`

Get the next signed byte integer.

#### Returns

1. `value` : integer - Signed byte.

### nextUShort

`handle:nextUShort()`

Get the next unsigned short integer.

#### Returns

1. `value` : integer - 16-bit unsigned integer.

### nextUInt

`handle:nextUInt()`

Get the next unsigned integer.

#### Returns

1. `value` : integer - 32-bit unsigned integer.

### nextULong

`handle:nextShort()`

Get the next unsigned long integer.

!!! Warning
	Due to how Lua works, this method will actually return a signed long integer.

#### Returns

1. `value` : integer - 64-bit unsigned integer.

### nextHalf

`handle:nextHalf()`

Get the next 16-bit floating point number.

#### Returns

1. `value` : number - 16-bit floating point number.

### nextFloat

`handle:nextFloat()`

Get the next 32-bit floating point number.

#### Returns

1. `value` : number - 32-bit floating point number.

### nextDouble

`handle:nextDouble()`

Get the next 64-bit floating point number.

#### Returns

1. `value` : number - 64-bit floating point number.

### nextChar

`handle:nextChar( [count] )`

Get the next `n` characters.

#### Parameters

1. `count` : number = `1` - Amount of characters to read.

#### Returns

1. `...data` : string - Characters read.

### nextString

`handle:nextString( count )`

!!! Warning
	Work in progress.
	This method may not work as described.

Get the next string.

#### Returns

1. `value` : string - string.

### nextBoolean

`handle:nextBoolean()`

Get the next boolean.

#### Returns

1. `value` : boolean - The next boolean.

### close

`handle:close()`

Close the stream handle.
