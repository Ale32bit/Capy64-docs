# HTTP

The HTTP library is used to do HTTP requests and open WebSocket connections.

!!! Warning

	HTTP must be enabled in the settings file!

## Usage

```lua
local term = require("http")

local response = http.get("https://example.com")
print(response:readAll())
response:close()
```

## Functions

### checkURL

`checkURL( url )`

Check whether the URL is valid and the protocol is either `http`, `https`, `ws`, or `wss`.

#### Parameters

1. `url` : string - The URL to check.

#### Returns

1. `valid` : boolean - Whether the URL is valid.

### requestAsync

`requestAsync( url, body?, headers?, options? )`

Send an asynchronous HTTP request.

#### Parameters

1. `url` : string - The URL to request
2. `body` : string? - The body to send.
3. `headers` : table? - Table containing the headers to send `[HeaderKey] = HeaderValue`.
4. `options` : table? - Table containing options.

#### Returns

1. `requestId` : integer - ID of the request to await for.

#### Emits

##### http_response

This event is emitted when the server responded to the request.

1. `http_response` : string - Event name.
2. `requestId` : integer - ID of the request returned by `requestAsync`.
3. `response` : [HTTPResponseHandle](/Objects/Handles/HTTPResponseHandle/) - Table containing information and methods to read the body.

##### http_failure

This event is emitted when the request failed to reach the server.

1. `http_failure` : string - Event name.
2. `requestId` : integer - ID of the request returned by `requestAsync`.
3. `message` : string? - Error message.

#### Throws

* If request URL is invalid. Check with `checkURL` before calling this function.

#### Related

##### Events

* [http_response]()
* [http_failure]()

### websocketAsync

`websocketAsync( url, headers )`

Open a WebSocket connection.

#### Parameters

1. `url` : string - The URL to connect to.
2. `headers` : table? - Table containing the headers to send `[HeaderKey] = HeaderValue`.

#### Returns

1. `requestId` : integer - ID of the request to await for.

#### Emits

##### websocket_connect

This event is emitted when the connection is established successfully.

1. `websocket_connect` : string - Event name.
2. `requestId` : integer - ID of the request returned by `websocketAsync`.
3. `websocketHandle` : [WebSocketHandle](/Objects/Handles/HTTPResponseHandle) - WebSocket handle.

##### websocket_failure

1. `websocket_failure` : string - Event name.
2. `requestId` : integer - ID of the request returned by `websocketAsync`.
3. `message` : string? - Error message.

#### Throws

* If request URL is invalid. Check with `checkURL` before calling this function.
* If WebSockets are disabled in configuration.
* If maximum concurrent connections is reached.

#### Related

##### Events

* [websocket_connect]()
* [websocket_failure]()
* [websocket_message]()
* [websocket_close]()
