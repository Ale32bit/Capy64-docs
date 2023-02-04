# Audio

The Audio library allows you to play audio and beep frequencies.

## Usage

```lua
local audio = require("audio")

-- Play a square wave of 440Hz for half a second, at 40% volume.
audio.beep(440, 0.5, 0.4)
```

## Functions

### play

`audio.play( data )`

Play audio.

#### Parameters

1. `data` : string - Data to play. One character is one byte.

### beep

`audio.beep( frequency, [time], [volume] )`

Play a square wave tone.

#### Parameters

1. `frequency` : number - Frequency to play.
2. `time` : number - How long to play. In seconds.
3. `volume` : number - Volume of the tone from 0 to 1. 0.5 is 50%.

### resume

`audio.resume()`

Resume the paused audio.

### pause

`audio.pause()`

Pause the audio.

### stop

`audio.stop()`

Stop the audio and clear the buffers.

### getVolume

`audio.getVolume()`

Get the master volume.

#### Returns

1. `volume` : number - Percentage of the volume from 0 to 1.

### setVolume

`audio.setVolume( volume )`

Set the master volume.

#### Parameters

1. `volume` : number - Percentage of the volume from 0 to 1.

### status

`audio.status()`

Get the state of the audio.

#### Returns

1. `status` : string - One of the following options:
    * `playing`
    * `stopped`
    * `paused`