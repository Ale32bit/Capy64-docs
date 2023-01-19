# http_response

Emitted when a server responded to a HTTP request.

## Parameters

1. `http_response` : string - Event name.
2. `requestId` : integer - ID of the request returned by `requestAsync`.
3. `response` : [HTTPResponseHandle](/Objects/Handles/HTTPResponseHandle/) - Table containing information and methods to read the body.