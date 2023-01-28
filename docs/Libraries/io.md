# IO

[IO](https://www.lua.org/manual/5.4/manual.html#6.8) is a Lua standard library.

This library is heavily different from the Lua standard and is not available natively.

This library is implemented by CapyOS and is available globally.

## Example

```lua
while true do
    local userInput = io.read()
    io.write('You said "' .. userInput .. '"!\n')
end
```

## Functions

### write

`io.write( text )`

Write text to the terminal without newline.

#### Parameters

1. `text` : any - Text to write.

#### Returns

1. `lines` : number - How many lines it wrote.

### read

`io.read( replace?, history?, complete?, default? )`

Prompt user to input a text.

#### Parameters

1. `replace` : string - Character to hide what is typed in.
2. `history` : table - String array that contains the history, browseable by pressing up and down keys.
3. `complete` : function - Function to resolve user input and give hints to complete.
4. `default` : string - Value to start with.

#### Returns

1. `input` : string - Text inputted by user.

### stderr.write

`io.stderr.write( text )`

Write text to the terminal without newline. In red color.

#### Parameters

1. `text` : any - Text to write.

#### Returns

1. `lines` : number - How many lines it wrote.

### stderr.print

`io.stderr.print( ... )`

Print text to the terminal with newline. In red color.

### Parameters

1. `...text` : any - Text to write.

#### Returns

1. `lines` : number - How many lines it wrote.
