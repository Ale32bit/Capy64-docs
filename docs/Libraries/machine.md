# Machine

The Machine library is dedicated to functions related to power control and external features such as window title and Discord Rich Presence.

## Usage

```lua
local machine = require("machine")

-- Shutdown and exit Capy64
machine.shutdown()

-- Reboot
machine.reboot()
```

## Functions

### shutdown

`machine.shutdown()`

Shutdown and exit Capy64.

### reboot

`machine.reboot()`

Reboot the runtime.

### title

`machine.title( [ newTitle ] )`

Get and set the window title.

#### Parameters

1. `newTitle` : string? - New title to set.

#### Returns

1. `title` : string - Title before the change.

### version

`machine.version()`

Get the current version of Capy64.

#### Returns

1. `version` : string - Current version.

### setRPC

`machine.setRPC( details, [ state ])`

Set the Discord RPC texts if enabled.

#### Parameters

1. `details` : string - Top line.
2. `state` : string? - Bottom line.