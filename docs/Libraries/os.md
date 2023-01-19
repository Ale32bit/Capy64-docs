# OS

[OS](https://www.lua.org/manual/5.4/manual.html#6.9) is a Lua standard library.

In Capy64 this library is modified and sandboxed.

## Removed features

The following features are removed due to sandboxing issues or better alternatives offered by other libraries.

* [os.execute](https://www.lua.org/manual/5.4/manual.html#pdf-os.execute)
* [os.exit](https://www.lua.org/manual/5.4/manual.html#pdf-os.exit)
* [os.remove](https://www.lua.org/manual/5.4/manual.html#pdf-os.remove)
* [os.rename](https://www.lua.org/manual/5.4/manual.html#pdf-os.rename)
* [os.rename](https://www.lua.org/manual/5.4/manual.html#pdf-os.rename)

## Added features

### version

`os.version()`

Get Capy64 version.

#### Returns

1. `version` : string - Version of Capy64

### shutdown

`os.shutdown( reboot = false )`

Shutdown or reboot Capy64.

#### Parameters

1. `reboot` : boolean - Restart instead of shutting down.