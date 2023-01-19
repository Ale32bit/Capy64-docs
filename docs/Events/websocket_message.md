# websocket_message

This event is emitted when the WebSocket server transmits data.

## Parameters

1. `websocket_message` : string - Event name.
2. `requestId` : integer - ID of the request returned by `websocketAsync`.
3. `data` : string - Data sent by server.