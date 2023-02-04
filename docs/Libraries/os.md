# OS

[OS](https://www.lua.org/manual/5.4/manual.html#6.9) is a Lua standard library.

In Capy64 this library is modified and sandboxed.

## Removed features

The following features are removed due to sandboxing issues or better alternatives offered by other libraries.

* [os.execute](https://www.lua.org/manual/5.4/manual.html#pdf-os.execute)
* [os.exit](https://www.lua.org/manual/5.4/manual.html#pdf-os.exit)
* [os.remove](https://www.lua.org/manual/5.4/manual.html#pdf-os.remove)
* [os.rename](https://www.lua.org/manual/5.4/manual.html#pdf-os.rename)