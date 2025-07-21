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
- TCP connection clsed

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
