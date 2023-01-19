# key_down

Emitted when any keyboard key is pressed.

## Parameters

1. `key_down` : string - Event name.
2. `keyCode` : number - ID of the key.
3. `keyName` : string - Name of the key.
4. `modifiers` : integer - Flags of pressed modifiers.
5. `isHeld` : string - Whether the key is being held down.

## Modifiers flag

| Value | Key           |
|-------|---------------|
| 0     | None          |
| 1     | Left Shift    |
| 2     | Right Shift   |
| 4     | Left Alt      |
| 8     | Right Alt     |
| 16    | Left Control  |
| 32    | Right Control |
