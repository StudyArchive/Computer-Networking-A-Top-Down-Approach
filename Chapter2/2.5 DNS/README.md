# 2.5 DNS

## Local DNS Name server
- does not strictly belong to hierachy
- each ISP(residential ISP, company, university) has one
 - also called "default name server"
- when host makes DNS query, query is sent to its local DNS server
 - has local cache of recent name-to-address translation pairs(but may be out of date!)
 - acts as proxy, forwards query into hierachy



## DNS name resolution example
- host at cis.poly.edu wants IP address for gaia.cs.umass.edu

### iterated query:
- contacted server replies with name of server to cantact
- "I don't know this name, but ask this server"