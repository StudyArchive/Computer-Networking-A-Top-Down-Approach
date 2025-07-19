## 1.5 protocol layers, service models

## Protocol

### Why layering?

- dealing with complex systems:
    - explicit stucture allows identification, relationship of complex system’s pieces
- modularization eases maintenance, updating of system (The similarity network layer can be likened to an architectural layer in software programming, where interfaces and functional decomposition promote modularity and clean code.)
- layering considered harmful?
    - One layer may duplicate lower-layer functionality(Overapping)
    - functionality of one layer may require information available in another layer.(Overhead)

### Internet protocol stack => Each protocol layer relies on the layer below it to achieve its own objectives.
- application layer : supporting network applications(encapsule message made by user application)
    - FTP(file), SMTP(e-mail), HTTP(web)
    - make message from user data
- transport layer : process-process data transfer(source process to destination process delivery)
    - TCP, UDP
    - make segment to attatch transport layer's header from message
- network layer : routing of datagrams from source to destination(host to host message transfer)
    - IP, routing protocols
    - make datagram to attach network layer's header from segment
- link layer : data transfer between neighboring network elements(hop to hop data transfer)
    - Ethernet, 802.111(WiFi), PPP
    - make frame to attach link layer's header from datagram
- physical layer : bits "on the wire"



<img width="700" height="500" alt="image" src="https://github.com/user-attachments/assets/0d0e4b19-f155-44b4-99a9-961b8eeb7bd3" />
