---
id: 492bi6uorxged21j14ctm47
title: OSI Model
desc: ''
updated: 1666815893601
created: 1666814289260
---

There are 7 layers in the OSI Model which are:

1. Physical : Here bits or symbols are send as the PDU. This covers the transmission and reception of raw bit streams over a physical medium.
1. Data Link : Here data frames between two nodes cennected by a physical layer are sent to each other. A frame is a digital data transmission unit. A simple container for a single network packet. A packet is a unit of data containing a header that holds information about how to network the packet and a payload which contains the information given to the receiver. A frame includes frame synchronization features consisting of a sequence of bits or symbols that indicate to the receiver the geginning and end of the payload data within the stream of symbols or bits it receives. If a receiver is connected to the sustem during frame transmission, it ignores the data until it detects a new frame synchronization sequence. Frame are the result of the dinal layer of encapsulation before the data is transmitted over the physical layer.
1. Network : Here packets are the PDU. A packet contains control information and user data which is also called the payload. Control information provides data for lelivering the payload (e.g. source and destination network addresses, error detection codes, or sequencing information.) Control information is found in packet headers and trailers. Structuring and managing a multinode network, including addressing, routing and traffic control. 
1. 

