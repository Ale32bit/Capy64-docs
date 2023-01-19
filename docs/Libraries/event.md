# Event

The Event library is used to pull events.

## Usage

```lua
local event = require("event")

while true do
	local _, button, x, y = event.pull("mouse_down")

	print(string.format("You clicked at %s, %s with button %s", x, y, button))
end
```

## Functions

### pull

`event.pull( [eventName1 [, eventName2, ...]] )`

Wait for events.

#### Parameters

1. `...eventName` : string - Events to wait for.

#### Returns

1. `eventName` : string - Name of the event.

...n. `parameter` : any - Any parameter related to the event pulled.

#### Throws

* If [interrupt](/Events/interrupt/) event is emitted anytime despite the filter.

### pullRaw

`event.pullRaw( [eventName1 [, eventName2, ...]] )`

Wait for events.

!!! note
	[interrupt](/Events/interrupt/) event is emitted despite the filter, but will not error.

#### Parameters

1. `...eventName` : string - Events to wait for.

#### Returns

1. `eventName` : string - Name of the event.

...n. `parameter` : any - Any parameter related to the event pulled.