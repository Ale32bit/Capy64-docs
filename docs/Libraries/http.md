# HTTP

The HTTP library is used to send HTTP requests and open WebSocket connections.

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

`http.checkURL( url )`

Check whether the URL is valid and the protocol is either `http`, `https`, `ws`, or `wss`.

#### Parameters

1. `url` : string - The URL to check.

#### Returns

1. `valid` : boolean - Whether the URL is valid.

### requestAsync

`http.requestAsync( url, body?, headers?, options? )`

Send an asynchronous HTTP request.

#### Parameters

1. `url` : string - The URL to request
2. `body` : string? - The body to send.
3. `headers` : table? - Table containing the headers to send `[HeaderKey] = HeaderValue`.
4. `options` : table? - Table containing options.

#### Returns

1. `requestId` : integer - ID of the request to await for.

#### Emits

* [http_response](/Events/http_response/)
* [http_failure](/Events/http_failure/)

#### Throws

* If request URL is invalid. Check with `checkURL` before calling this function.

### websocketAsync

`http.websocketAsync( url, headers )`

Open a WebSocket connection.

#### Parameters

1. `url` : string - The URL to connect to.
2. `headers` : table? - Table containing the headers to send `[HeaderKey] = HeaderValue`.

#### Returns

1. `requestId` : integer - ID of the request to await for.

#### Emits

* [websocket_connect](/Events/websocket_connect/)
* [websocket_failure](/Events/websocket_failure/)

#### Throws

* If request URL is invalid. Check with `checkURL` before calling this function.
* If WebSockets are disabled in configuration.
* If maximum concurrent connections is reached.

#### Related

##### Events

* [websocket_connect](/Events/websocket_connect/)
* [websocket_failure](/Events/websocket_failure/)
* [websocket_message](/Events/websocket_message/)
* [websocket_close](/Events/websocket_close/)

### request

`http.request( url, body?, headers?, options? )`

Send a HTTP request and wait for response.

!!! Extension
	This function is an extension implemented by CapyOS!

#### Parameters

1. `url` : string - The URL to request
2. `body` : string? - The body to send.
3. `headers` : table? - Table containing the headers to send `[HeaderKey] = HeaderValue`.
4. `options` : table? - Table containing options.

#### Returns

If successful

1. `response` : [HTTPResponseHandle](/Objects/Handles/HTTPResponseHandle/) - Table containing information and methods to read the body.

##### OR

If failed

1. `nil` : nil
2. `message` : string - Error message.

### get

`http.get( url, headers?, options? )`

Send a HTTP GET request and wait for response.

!!! Extension
	This function is an extension implemented by CapyOS!

#### Parameters

1. `url` : string - The URL to request
2. `headers` : table? - Table containing the headers to send `[HeaderKey] = HeaderValue`.
3. `options` : table? - Table containing options.

#### Returns

If successful

1. `response` : [HTTPResponseHandle](/Objects/Handles/HTTPResponseHandle/) - Table containing information and methods to read the body.

##### OR

If failed

1. `nil` : nil
2. `message` : string - Error message.

### websocket

`http.websocket( url, headers )`

Open a WebSocket connection.

!!! Extension
	This function is an extension implemented by CapyOS!

#### Parameters

1. `url` : string - The URL to connect to.
2. `headers` : table? - Table containing the headers to send `[HeaderKey] = HeaderValue`.

#### Returns

If successful

1. `websocketHandle` : [WebSocketHandle](/Objects/Handles/WebSocketHandle) - WebSocket handle.

##### OR

If failed

1. `nil` : nil
2. `message` : string - Error message.

#### Throws

* If request URL is invalid. Check with `checkURL` before calling this function.
* If WebSockets are disabled in configuration.
* If maximum concurrent connections is reached.

#### Related

##### Events

* [websocket_connect](/Events/websocket_connect/)
* [websocket_failure](/Events/websocket_failure/)
* [websocket_message](/Events/websocket_message/)
* [websocket_close](/Events/websocket_close/)