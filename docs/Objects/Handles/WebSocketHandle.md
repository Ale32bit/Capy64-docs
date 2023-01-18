# WebSocketHandle

WebSocketHandle provides methods to communicate with the server and properties about the response.

## Properties

### success

`success`: boolean

Whether the request was successful.

### statusCode

`statusCode` : number

HTTP Status code of the response.

### reasonPhrase

`reasonPhrase` : string

Message of the status code.

### headers

`headers` : table

Key-value pairs of all headers received.

### requestId

`requestId` : integer

ID of the request.

!!! Extension
	This property is an extension implemented by CapyOS!

## Methods

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