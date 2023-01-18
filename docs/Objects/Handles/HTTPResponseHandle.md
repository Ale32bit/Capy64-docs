# HTTPResponseHandle

HTTPResponseHandle provides methods to read the body of the response and properties about the response.

!!! Note
	This object extends [ReadHandle](/Objects/Handles/ReadHandle)

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
