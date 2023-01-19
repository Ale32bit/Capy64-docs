# Timer

The Timer library is used to schedule timers.

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

`timer.start( ms )`

Start a timer of `n` milliseconds.

!!! note
	Timer is bound to tickrate, therefore it will emit to the closest tick.

#### Parameters

1. `ms` : number - Milliseconds to wait

#### Returns

1. `timerId` : integer - ID of the timer just scheduled.

#### Emits

* [timer](/Events/timer)

### sleep

`timer.sleep( n )`

!!! Extension
	This function is an extension implemented by CapyOS!

Wait `n` milliseconds.

#### Parameters

1. `n` : number - Milliseconds to wait.

#### Throws

* If `n` is less than 1.
