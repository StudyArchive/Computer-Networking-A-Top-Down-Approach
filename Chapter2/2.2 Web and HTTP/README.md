# 2.2 Web and HTTP
## Web and HTTP
- web page consists of objects
- object can be HTML file, JPEG image, Java applet, audio file
- web page consists of base HTML file which includes several refereneced objects
- each object is addressable by a URL
 - eg. www.example.com/dept/pic.gif


## HTTP overiew
### HTTP: hypertext transfer protocol
- Web's application layer protocol
- client/server model
  - client: browser that requests, receives(using HTTP protocol) and 'displays' Web objects
  - server: Web server sends (using HTTP protocol) objects in response to requests

### HTTP uses TCP
- client initiates TCP connections(creates socket) to server, port 80
- server accests TCP connection from client
- HTTP messages(application-layer protocol messages) exchanged between browser(HTTP client) and Web server(HTTP server)
- TCP connection closed

### HTTP is "stateless"
- server maintains no information about past client requests
- protocols that maintain 'state(history)' are complex

## HTTP connections
### The first HTTP version is non-persistent HTTP
 - at most one object sent over TCP connection and then connection closed
- downloading multiple objects requires multiple connections

### Recent HTTP versions are persistent HTTP
- multiple objects can be sent over sigle TCP connection between client, server

<img width="700" height="500" alt="image" src="https://github.com/user-attachments/assets/118e04b0-a512-429e-bc5d-269207bd0688" />
<img width="700" height="500" alt="image" src="https://github.com/user-attachments/assets/aecbd3f6-6096-4b8f-a309-bf11a92aec2d" />

## Non-persistent HTTP: response time
- RTT(Round Trip Time)
 - time for a small packet to travel from client to server and back
- HTTP response time
  - one RTT to initiate TCP
  - one RTT for HTTP request and first few bytes of HTTP response to return
  - file transmission time
  - one-persistent HTTP response time = 2RTT + file transmission time


## Persistent HTTP
### non-persistent HTTP issues
- requires 2RTTs per object
- browsers often open parallel TCP connetions to fetch referenced objects
- OS overhead for each TCP connection

### persistent HTTP
- server leaves connection open after sending response
- subsequent HTTP messages between same client/server sent over open connection
- client sends requests as soon as it encouters a referenced object
- as little as one RTT for all the refrenced objects


## HTTP request message
- two types of HTTP messages: request, reponse
- HTTP request message : ASCII(human-readable format)

<img width="689" height="308" alt="image" src="https://github.com/user-attachments/assets/daab9338-7f14-4e71-a04e-3ae32dfcd3a5" />



## Uploading form input
- POST method
  - web page often includs form inpu
  - input is uploaded to server in entity body
- URL method
  - uses GET method
  - input is uploaded in URL filed of request line: www.example.com/animalsearch?monkeys&banana

## Method types
- HTTP/1.0
 - GET
 - POST
 - HEAD : asks server to leave queststed object out of response

- HTTP/1.1
 - GET, POST, HEAD
 - PUT
  - uploads file in entity body to path specified in URL field
 - DELETE
  - deeltes file specified in the URL field 

## HTTP response message
<img width="670" height="395" alt="image" src="https://github.com/user-attachments/assets/6b2baa73-e1b5-4f7f-97e5-5dc1bb9f397f" />

##Cookie