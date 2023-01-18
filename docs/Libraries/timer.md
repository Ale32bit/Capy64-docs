# Timer

!!! Extension
	This library is extended: [Timer extensions](/Extensions/timer).

The Timer library is schedule timers.

## Usage

```lua
local timer = require("timer")
local event = require("event")

-- Start a timer of 5 minutes
local timerId = timer.start(300000)
-- Wait for the timer to trigger
repeat
    local _, id = event.pull("timer")
until id == timerId
```

## Functions

### start

`start( ms )`

Start a timer of `n` milliseconds.

!!! note
	Timer is bound to tickrate, therefore it will emit to the closest tick.

#### Parameters

1. `ms` : number - Milliseconds to wait

#### Returns

1. `timerId` : integer - ID of the timer just scheduled.

#### Emits

##### timer

This event is emitted when the scheduled timer has finished.

1. `timer` : string - Event name.
2. `timerId` : integer - ID of the timer that finished.
