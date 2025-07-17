## 2.1 principles of network apllication

- app architectures
- app requirements

About Application Layer.

- concepts
- protocol 예(HTTP, SMTP/ POP3/IMAP, DNS)
- socket API(Network Application 작성 인터페이스)

Network application

- e-mail
- web
- void over IP
- search

Application architecture 

⇒ network application은 아래 구조중 한 가지 를 취함. 네트워크 프로토콜도 아래 중 하나의 구조를 가짐.

- client-server
- peer-to-peer(P2P)

Client-server architecture

- 실질적으로는 host가 아니라 program(process)이 커뮤니케이션을 함.
- Server(process)
    - always-on host
    - permanent IP address
    - data centers for scaling
- Clients(process)
    - always communicate with server.
        - do not communicate with client each other
    - may be intermittently connected
    - ma have dynamic IP address

P2P architecture

- user host communicate with each other
    - no always-on server
- arbitrary end systems directly communicate(end system=peer)
- peers request service from other peers, provide service in return to other peer(서로 주기도 하고 받기도함)
    - self scalability
- complex management
- running client process and also running server process on peer

process: program running within a host

- withins same host, tow processes communicate using inter-process communication(defined by OS)
- processes in different hosts communicate by exchanging messages(network communicate)
    - client process : initiates communication (client host)
    - server process : waits to be contacted (server host)

view of network layer

application (process) controlled by app developer

transport, network, link, physical controlled by OS

Sockets : 

application layer communicate with transport layer

pro cess sends/recieves messages to/from its socket

Addressing processes

port numbers : for identifying process in host

- HTTP Web application process : 80 port
- mail server process : 25 port

An app need transport service

- data integrity
    - some apps(eg. file transfer, web transactions) require 100% reliable data transfer
    - other apps(eb. audio) can tolerate some loss
- timing
    - some apps(eg. Internet telephony, interactive games) require low delay to be “effective”
- throughput
    - some apps(eg. multimedia streaming) require minimum amount of throughput to be “effective”
    - other apps(’elastic apps) make
- security
    - encryption, data integrity

**Transport service requirements: commons apps**

| application | data loss(reliable transport) | throughput | time sensitive |
| --- | --- | --- | --- |
| file transfer | no loss | elastic | no |
| e-mail | no loss | elastic | no |
| text messaging | no loss | elastic | yes and no |
| real-time audio/video | loss-tolerant | audio: 5kbps-1Mbps
video:10kbps-5Mbps | yes, 100’s msec |
| sotred audio/video | loss-tolerant | same as above | yes, few secs |
| interactive games | loss-tolerant | few kbps up | yes, 100’s msec |

Internet transport protocols services

TCP service
- reliable transport between sending and receving process
- flow control: sender won’t overwhelm receiver (, TCP control OS layer kernel stack buffer control for Receiver’s Buffer)
- connection-oriented: setup required between client and server processes(not physically, only conceptual and logically connection)
- congestion control: throttle sender when network overloaded(Network overhead control)
- do not privede : timing, minimum throughput gurantee, security

UDP
- unreliable data transfer beween sending and receiving process
- does not provide: reliability, flow control, congestion control timing, throughput, guarantee, security, or connection setup

Application-layer protocol defines

- types of messages exchange(request messgae, response message)
- message syntax
    - what fields in messages  how fields are delineated
- message semantics
    - meaning of information in fields
- rules for when and how proccess send & respond to messages