# 2.5 DNS

## DNS: domain name system
- people: many identifiers:


### Domain Name System
- distributed database implemented in hierachy of many name servers
- application-layer protocol:
 - host, name servers communicate to resolve names(address/name translation)

## DNS: services, structure
### DNS services
- hostname to IP address translation
- mail server aliasing
- load distribution
    - replicated Web servers: many IP addresses correspond to one name

### why not centralize DNS?
- single point of failure
- traffic volume
- distant centralized database
- maintenance 


## DNS: a distributed, hierachical database


## DNS:root name servers
- contaced by local name server that can not resolve name
- root name server:
 - contacts authoritative name server if name mapping not known gets mapping
 - return mapping to local name server
- 13 root name "servers" worldwide(2012)

## TLD, authoritative servers
## top-level domain(TLD) servers:
- responsible for com, org, net, edu, aero, jobs, museums, and all top-level county domains, e.g:uk, fr, ca, jp
- Network Solutions maintains servers for .com TLD Educause for .edu TLD
- 한국인터넷정보센터 for .kr TLD

## authoritative DNS server:
- organizations's own DNS server(s), providing authoritative hostname to IP mappings for organization's named hosts
- can be maintained by organization's named hosts
- can be maintained by organization or service provider

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

<img width="430" height="560" alt="image" src="https://github.com/user-attachments/assets/a96c4214-802b-45a9-a8cf-ef97cab36918" />


### recursive query:
- puts burden of name resolution on contaced name server
- heavy load at uppper levels of hierachy

<img width="430" height="560" alt="image" src="https://github.com/user-attachments/assets/1fc491b7-fa31-448b-a213-3bd271bdec30" />