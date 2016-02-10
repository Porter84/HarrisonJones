#HTTP

##What is HTTP? Why was it created?

 - It is an abbreviation for Hypertext Transfer Protocol.
 - The Hypertext Transfer Protocol (HTTP) is an application-level protocol (TCP/IP has five layer: physical-layer, link-layer, internet-layer, transport-layer, application-layer). It is a stateless, protocol which can be used for many tasks beyond its use for hypertext, through extension of its request methods, error codes and headers. HTTP is the foundation of data communication for the World Wide Web. HTTP functions as a request-response protocol in the client-server computing model.

##What is the difference between HTTP and HTTPS?

 - HTTPS (also called HTTP over TLS, HTTP over SSL and HTTP Secure) is a protocol for secure communication over a computer network which is widely used on the Internet. HTTPS consists of communication over Hypertext Transfer Protocol (HTTP) within a connection encrypted by Transport Layer Security (TLS) or its predecessor, Secure Sockets Layer (SSL). The main motivation for HTTPS is authentication of the visited website and protection of the privacy and integrity of the exchanged data. It provides bidirectional encryption of communications between a client and server. Because HTTPS piggybacks HTTP entirely on top of TLS, the entirety of the underlying HTTP protocol can be encrypted. This includes the request URL (which particular web page was requested), query parameters, headers, and cookies (which often contain identity information about the user).
 - Difference from HTTP: HTTPS URLs begin with "https://" and use port 443 by default, whereas HTTP URLs begin with "http://" and use port 80 by default.
HTTP is not encrypted and is vulnerable to man-in-the-middle and eavesdropping attacks, which can let attackers gain access to website accounts and sensitive information, and modify webpages to inject malware or advertisements. HTTPS is designed to withstand such attacks and is considered secure against them (with the exception of older, deprecated versions of SSL).

##How a HTTP request looks like?

Request-Line = HTTP Method SP Request-URI SP HTTP-Version CRLF

##Please describe a HTTP request-response process.

1. You enter a URL into the browser
2. The browser looks up the IP address for the domain name
3. The server sends back a HTML response
4. The browser begins rendering the HTML

##How HTTP stores states?

It cannot store states, because HTTP is a stateless protocol.

##Please describe the purpose of GET, POST, DELETE, PUT methods. (3-4 sentences for each)
 - **GET:** The GET method means retrieve whatever information (in the form of an entity) is identified by the Request-URI. If the Request-URI refers to a data-producing process, it is the produced data which shall be returned as the entity in the response and not the source text of the process, unless that text happens to be the output of the process.
 - **POST:** The POST method requests that the server accept the entity enclosed in the request as a new subordinate of the web resource identified by the URI. POST is designed to allow a uniform method to cover the following functions:
  - Annotation of existing resources;
  - Posting a message to a bulletin board, newsgroup, mailing list, or similar group of articles;
  - Providing a block of data, such as the result of submitting a form, to a data-handling process;
  - Extending a database through an append operation.
 - **PUT:** The PUT method requests that the enclosed entity be stored under the supplied URI. If the URI refers to an already existing resource, it is modified; if the URI does not point to an existing resource, then the server can create the resource with that URI.
 - **DELETE:** The DELETE method deletes the specified resource.

##What other request types do you know?
 - **HEAD:** The HEAD method asks for a response identical to that of a GET request, but without the response body. This is useful for retrieving meta-information written in response headers, without having to transport the entire content.
 - **TRACE:** The TRACE method echoes the received request so that a client can see what (if any) changes or additions have been made by intermediate servers.
 - **OPTIONS:** The OPTIONS method returns the HTTP methods that the server supports for the specified URL. This can be used to check the functionality of a web server by requesting '*' instead of a specific resource.
 - **CONNECT:** The CONNECT method converts the request connection to a transparent TCP/IP tunnel, usually to facilitate SSL-encrypted communication (HTTPS) through an unencrypted HTTP proxy.
 - **PATCH:** The PATCH method applies partial modifications to a resource. All general-purpose HTTP servers are required to implement at least the GET and HEAD methods,[20] and, whenever possible, also the OPTIONS method.[citation needed]

##Enumerate at least 4 HTTP status code from 4 different code groups.
 - 1xx: Informational - Request received, continuing process
 - 2xx: Success - The action was successfully received, understood, and accepted
   202 Accepted

The request has been accepted for processing, but the processing has not been completed. The request might or might not eventually be acted upon, as it might be disallowed when processing actually takes place. There is no facility for re-sending a status code from an asynchronous operation such as this.

The 202 response is intentionally non-committal. Its purpose is to allow a server to accept a request for some other process (perhaps a batch-oriented process that is only run once per day) without requiring that the user agent's connection to the server persist until the process is completed. The entity returned with this response SHOULD include an indication of the request's current status and either a pointer to a status monitor or some estimate of when the user can expect the request to be fulfilled.

      - 3xx: Redirection - Further action must be taken in order to
        complete the request
        307 Temporary Redirect

The requested resource resides temporarily under a different URI. Since the redirection MAY be altered on occasion, the client SHOULD continue to use the Request-URI for future requests. This response is only cacheable if indicated by a Cache-Control or Expires header field.

The temporary URI SHOULD be given by the Location field in the response. Unless the request method was HEAD, the entity of the response SHOULD contain a short hypertext note with a hyperlink to the new URI(s) , since many pre-HTTP/1.1 user agents do not understand the 307 status. Therefore, the note SHOULD contain the information necessary for a user to repeat the original request on the new URI.

If the 307 status code is received in response to a request other than GET or HEAD, the user agent MUST NOT automatically redirect the request unless it can be confirmed by the user, since this might change the conditions under which the request was issued.


      - 4xx: Client Error - The request contains bad syntax or cannot
        be fulfilled
        404 Not Found

The server has not found anything matching the Request-URI. No indication is given of whether the condition is temporary or permanent. The 410 (Gone) status code SHOULD be used if the server knows, through some internally configurable mechanism, that an old resource is permanently unavailable and has no forwarding address. This status code is commonly used when the server does not wish to reveal exactly why the request has been refused, or when no other response is applicable.
      - 5xx: Server Error - The server failed to fulfill an apparently
        valid request
        500 Internal Server Error

The server encountered an unexpected condition which prevented it from fulfilling the request.


##What is the difference between HTTP standard and REST?
HTTP is a protocol, REST is a technology what using HTTP.

##What is a Cookie? What are its pros and cons?
