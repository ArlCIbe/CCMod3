HTTP (aka HTTP verbs despite sometimes despite sometimes being nouns) - defines a set of request methods to indicate the desired action to be performed for a given resource. Each of them implements a different semantic but all are either:
  - safe - doesn't alter the state of the server, leads to a read-only operation, and is **idempotent**.
  - idempotent - the intended effect on the server of making a single request is the same as the effect of making several identical requests.
  - cacheable - can be stored to be retrieved and used later, saving a new request to the server.

`# GET` - requests a representation of the specified resource; should only retrieve data.

`# HEAD` - asks for a response identical to a GET request, but without the response body.

`# POST` - submits an entity to the specified resource, often causing a change in state or side effects on the server.

`# PUT` - replaces all current representations of the target resource with the request payload.

`# DELETE` - deletes the specified resource.

`# CONNECT` - establishes a tunnel to the server identified by the target resource.

`# OPTIONS` - describes the communication options for the target resource.

`# TRACE` - performs a message loop-back test along the path to the target resource.

`# PATCH` - applies partial modifications to a resource.

HTTP response status codes indicate whether a specific HTTP request has been successfully completed. Responses are grouped in five classes:

1. Informational responses (100 – 199)
2. Successful responses (200 – 299)
3. Redirection messages (300 – 399)
4. Client error responses (400 – 499)
5. Server error responses (500 – 599)