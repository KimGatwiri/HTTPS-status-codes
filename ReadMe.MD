#  HTTP response status code
HTTP response status codes indicate whether a specific HTTP request has been successfully completed.  
 Responses are grouped in five classes:
 # HTTP Status Codes

## Informational Responses

- **100 Continue**  
  This   response indicates that the client should continue the request or ignore the response if the request is already finished.

- **101 Switching Protocols**  
  This code is sent in response to an Upgrade request header from the client and indicates the protocol the server is switching to.

- **102 Processing (Deprecated)**  
  This code was used in WebDAV contexts to indicate that a request has been received by the server, but no status was available at the time of the response.

- **103 Early Hints**  
  This status code is primarily intended to be used with the Link header, letting the user agent start preloading resources while the server prepares a response or preconnect to an origin from which the page will need resources.

## Successful Responses

- **200 OK**  
  The request succeeded. The result and meaning of "success" depends on the HTTP method:
  - **GET**: The resource has been fetched and transmitted in the message body.
  - **HEAD**: Representation headers are included in the response without any message body.
  - **PUT or POST**: The resource describing the result of the action is transmitted in the message body.
  - **TRACE**: The message body contains the request as received by the server.

- **201 Created**  
  The request succeeded, and a new resource was created as a result. This is typically the response sent after POST requests, or some PUT requests.

- **202 Accepted**  
  The request has been received but not yet acted upon. It is noncommittal since there is no way in HTTP to later send an asynchronous response indicating the outcome of the request. It is intended for cases where another process or server handles the request, or for batch processing.

- **203 Non-Authoritative Information**  
  This response code means the returned metadata is not exactly the same as is available from the origin server but is collected from a local or a third-party copy. Mostly used for mirrors or backups of another resource.

- **204 No Content**  
  There is no content to send for this request, but the headers are useful. The user agent may update its cached headers for this resource with the new ones.

- **205 Reset Content**  
  Tells the user agent to reset the document which sent this request.

- **206 Partial Content**  
  This response code is used in response to a range request when the client has requested a part or parts of a resource.

- **207 Multi-Status (WebDAV)**  
  Conveys information about multiple resources, for situations where multiple status codes might be appropriate.

- **208 Already Reported (WebDAV)**  
  Used inside a `<dav:propstat>` response element to avoid repeatedly enumerating the internal members of multiple bindings to the same collection.

- **226 IM Used (HTTP Delta encoding)**  
  The server has fulfilled a GET request for the resource, and the response is a representation of the result of one or more instance-manipulations applied to the current instance.

## Redirection Messages

- **300 Multiple Choices**  
  In agent-driven content negotiation, the request has more than one possible response, and the user agent or user should choose one of them.

- **301 Moved Permanently**  
  The URL of the requested resource has been changed permanently. The new URL is given in the response.

- **302 Found**  
  This response code means that the URI of requested resource has been changed temporarily.

- **303 See Other**  
  The server sent this response to direct the client to get the requested resource at another URI with a GET request.

- **304 Not Modified**  
  Used for caching purposes, it tells the client that the response has not been modified, so the client can continue to use the same cached version of the response.

- **305 Use Proxy (Deprecated)**  
  Defined in a previous version of the HTTP specification to indicate that a requested response must be accessed by a proxy. It has been deprecated due to security concerns.

- **306 Unused**  
  This response code is no longer used but is reserved.

- **307 Temporary Redirect**  
  The server sends this response to direct the client to get the requested resource at another URI with the same method that was used in the prior request.

- **308 Permanent Redirect**  
  This means that the resource is now permanently located at another URI specified by the Location response header.

## Client Error Responses

- **400 Bad Request**  
  The server cannot or will not process the request due to something perceived to be a client error.

- **401 Unauthorized**  
  The client must authenticate itself to get the requested response.

- **402 Payment Required**  
  Initially intended for digital payment systems, this status code is rarely used.

- **403 Forbidden**  
  The client does not have access rights to the content.

- **404 Not Found**  
  The server cannot find the requested resource. This response code is probably the most well-known due to its frequent occurrence on the web.

- **405 Method Not Allowed**  
  The request method is known by the server but is not supported by the target resource.

- **406 Not Acceptable**  
  Sent when the web server doesn’t find any content that conforms to the criteria given by the user agent.

- **407 Proxy Authentication Required**  
  Similar to 401 Unauthorized, but authentication is needed to be done by a proxy.

- **408 Request Timeout**  
  This response is sent on an idle connection by some servers.

- **409 Conflict**  
  This response is sent when a request conflicts with the current state of the server.

- **410 Gone**  
  This response is sent when the requested content has been permanently deleted from the server.

- **411 Length Required**  
  Server rejected the request because the Content-Length header field is not defined.

- **412 Precondition Failed**  
  The client has indicated preconditions in its headers which the server does not meet.

- **413 Content Too Large**  
  The request body is larger than limits defined by the server.

- **414 URI Too Long**  
  The URI requested by the client is longer than the server is willing to interpret.

- **415 Unsupported Media Type**  
  The media format of the requested data is not supported by the server.

- **416 Range Not Satisfiable**  
  The ranges specified by the Range header field in the request cannot be fulfilled.

- **417 Expectation Failed**  
  This response code means the expectation indicated by the Expect request header field cannot be met by the server.

- **418 I'm a teapot**  
  The server refuses the attempt to brew coffee with a teapot.

- **421 Misdirected Request**  
  The request was directed at a server that is not able to produce a response.

- **422 Unprocessable Content (WebDAV)**  
  The request was well-formed but unable to be followed due to semantic errors.

- **423 Locked (WebDAV)**  
  The resource that is being accessed is locked.

- **424 Failed Dependency (WebDAV)**  
  The request failed due to the failure of a previous request.

- **425 Too Early (Experimental)**  
  Indicates that the server is unwilling to risk processing a request that might be replayed.

- **426 Upgrade Required**  
  The server refuses to perform the request using the current protocol.

- **428 Precondition Required**  
  The origin server requires the request to be conditional.

- **429 Too Many Requests**  
  The user has sent too many requests in a given amount of time (rate limiting).

- **431 Request Header Fields Too Large**  
  The server is unwilling to process the request because its header fields are too large.

- **451 Unavailable For Legal Reasons**  
  The user agent requested a resource that cannot legally be provided.

## Server Error Responses

- **500 Internal Server Error**  
  The server has encountered a situation it does not know how to handle.

- **501 Not Implemented**  
  The request method is not supported by the server.

- **502 Bad Gateway**  
  The server, while working as a gateway, got an invalid response.

- **503 Service Unavailable**  
  The server is not ready to handle the request, often due to maintenance or overloading.

- **504 Gateway Timeout**  
  The server is acting as a gateway and cannot get a response in time.

- **505 HTTP Version Not Supported**  
  The HTTP version used in the request is not supported by the server.

- **506 Variant Also Negotiates**  
  The server has an internal configuration error during content negotiation.

- **507 Insufficient Storage (WebDAV)**  
  The server is unable to store the representation needed to complete the request.

- **508 Loop Detected (WebDAV)**  
  The server detected an infinite loop while processing the request.

- **510 Not Extended**  
  The client request declares an HTTP Extension that is not supported by the server.
