# 1.3 network core
## The network core
- mesh of interconnected routers
- packet-switching: hosts break application-layer messages into packets(the typical packet size is 1500 bytes)
  - forward packets from one router to the next, across links on path from source to destination
  - each packet transmitted at full link capacity
  - no call set up and no resource no reservation
- stored and forward

## Packet-switcing: store-and-forward
- takes L/R seconds to transmit (push out) L-bit packet into link at R bps
- store and forward: entire packet must arrive at router before it can be transmitted on next link

## Packet Switching: queueing delay, loss => congestion
### queuing and loss
- If arrival rate (in bits) to link exceeds transmission rate of link for a period of time
  - packets will queue, wait to be transmitted on link
  - packets can be dropped (lost) if memory (buffer) fills up