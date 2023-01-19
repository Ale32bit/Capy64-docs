# BinaryWriteHandle

BinaryWriteHandle provides methods to write binary data to a stream.

## Methods

### writeByte

`handle:writeByte( value | { byte1, byte2, ...byten} )`

Write bytes.

#### Parameters

1. `value` : integer | table - Bytes to write.

### writeShort

`handle:writeShort( value )`

Write the next short integer.

#### Parameters

1. `value` : integer - 16-bit signed integer.

### writeInt

`handle:writeInt( value )`

Write the next integer.

#### Parameters

1. `value` : integer - 32-bit signed integer.

### writeLong

`handle:writeLong( value )`

Write the next long integer.

#### Returns

1. `value` : integer - 64-bit signed integer.

### writeSByte

`handle:writeSByte( value )`

Write the next signed byte integer.

#### Returns

1. `value` : integer - Signed byte.

### writeUShort

`handle:writeUShort( value )`

Write the next unsigned short integer.

#### Returns

1. `value` : integer - 16-bit unsigned integer.

### writeUInt

`handle:writeUInt( value )`

Write the next unsigned integer.

#### Returns

1. `value` : integer - 32-bit unsigned integer.

### writeULong

`handle:writeShort( value )`

Write the next unsigned long integer.

!!! Warning
	Due to how Lua works, this method will actually write a signed long integer.

#### Returns

1. `value` : integer - 64-bit unsigned integer.

### writeHalf

`handle:writeHalf( value )`

Write the next 16-bit floating point number.

#### Returns

1. `value` : number - 16-bit floating point number.

### writeFloat

`handle:writeFloat( value )`

Write the next 32-bit floating point number.

#### Returns

1. `value` : number - 32-bit floating point number.

### writeDouble

`handle:writeDouble( value )`

Write the next 64-bit floating point number.

#### Returns

1. `value` : number - 64-bit floating point number.

### writeChar

`handle:writeChar( value | { char1, char2, ...charn} )`

Write the next `n` characters.

#### Parameters

1. `value` : integer | table - Characters to write.

### writeString

`handle:writeString( count )`

!!! Warning
	Work in progress.
	This method may not work as described.

Write the next string.

#### Returns

1. `value` : string - string.

### writeBoolean

`handle:writeBoolean()`

Write the next boolean.

#### Returns

1. `value` : boolean - The next boolean.

### flush

`handle:flush()`

Flush the stream and apply changes.

### close

`handle:close()`

Close the stream handle.
