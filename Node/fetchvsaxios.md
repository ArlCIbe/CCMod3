For web applications to communicate with servers using the HTTP protocol they use **fetch** or **axios**

fetch API -  uses **Request and **Response objects 
    [(and other things involved with network requests), as well as related concepts such as CORS and the HTTP Origin header semantics.]

Fetch Interfaces

`fetch()` - a global method (in both `Window` [and `Worker` contexts]) that makes a request and "fetches" a resource.
- takes the URL of the resource to be fetched as a mandatory argument
- provides a JS interface for accessing and manipulating parts of the HTTP pipeline (requests and responses)
- returns a Promise that can be used to retrieve the response to the request. 
     [as soon as the server responds with headers even if the server response is an HTTP error status. You can also optionally pass in an init options object as the second argument.]

promise - represents the eventual completion (or failure) of an asynchronous operation and its resulting value 

```bash
fetch('path-to-the-resource-to-be-fetched')
  .then((response) => {
    // Code for handling the response
  })
  .catch((error) => {
    // Code for handling the error
  });
```

Headers
Represents response/request headers, allowing you to query them and take different actions depending on the results.

`Request()` - Fetch API interfeace that represents a resource request. 

`Response()` - Fetch API interfeace that represents the response to a request.

  note: most likely will encounter `Request()` and `Response()` objects being returned as the result of another API operation

worker context - functionality not seen by the user, goes on in the background

Axios - an isomorphic,
    [promise-based HTTP Client for node.js and the browser. On the server-side it uses the native node.js http module, while on the client (browser) it uses XMLHttpRequests.]
    [a Javascript library used to make HTTP requests from node.js or XMLHttpRequests from the browser and it supports the Promise API that is native to JS ES6. It can be used intercept HTTP requests and responses and enables client-side protection against XSRF. It also has the ability to cancel requests.]

isomorphic - can run in the browser and nodejs with the same codebase. 

```bash
axios.get('url')
  .then((response) => {
    // Code for handling the response
  })
  .catch((error) => {
    // Code for handling the error
  })
```

Features
Make XMLHttpRequests from the browser
Make http requests from node.js
Supports the Promise API
Intercept request and response
Transform request and response data
Cancel requests
Timeouts
Query parameters serialization with support for nested entries
Automatic request body serialization to:
JSON (application/json)
Multipart / FormData (multipart/form-data)
URL encoded form (application/x-www-form-urlencoded)
Posting HTML forms as JSON
Automatic JSON data handling in response
Progress capturing for browsers and node.js with extra info (speed rate, remaining time)
Setting bandwidth limits for node.js
Compatible with spec-compliant FormData and Blob (including node.js)
Client side support for protecting against XSRF