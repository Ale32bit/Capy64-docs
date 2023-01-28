# WebSocketClient

WebSocketClient provides methods to communicate with the server.

## Methods

### getRequestID

`handle:getRequestID()`

Get the ID of the request.

#### Returns

1. `requestId` : integer - ID of the request.

### send

`handle:send( data )`

Send data to the WebSocket server.

#### Parameters

1. `data` : string - Data to transmit

#### Throws

* If connection is closed

### closeAsync

`handle:closeAsync()`

Close the connection.

#### Emits

##### websocket_close

1. `websocket_close` : string - Event name.
2. `requestId` : integer - ID of the request.

### receive

`handle:receive()`

Await data to receive

!!! Extension
	This function is an extension implemented by CapyOS!

#### Returns

1. `data` : string - Data received.

#### Throws

* If connection is closed

### close

`handle:close()`

Close the connection.

!!! Extension
	This function is an extension implemented by CapyOS!