#AVB Summary & note

##Standardization

|Standard|Title|Comment|
|:-|:-|:-|
|IEEE 802.1BA-2011|Audio Video Bridging (AVB) Systems|Identification of participating devices<br>[802.1ba](http://www.ieee802.org/1/pages/802.1ba.html)|
|IEEE 802.1Qav|Forwarding and Queuing for Time-Sensitive Streams (FQTSS)|Traffic shaping for AV streams(at both stream source and AVB bridge)<br>[802.1Qav](http://www.ieee802.org/1/pages/802.1av.html)|
|IEEE 802.1Qat|Stream Reservation Protocol (SRP)|Admission control<br>[802.1Qat](http://www.ieee802.org/1/pages/802.1at.html)|
|IEEE 802.1Q-2011|Incorporates IEEE 802.1Qav and IEEE 802.1Qat|[802.1Q-2014](http://www.ieee802.org/1/pages/802.1Q-2014.html)|
|IEEE 802.1AS-2011|Timing and Synchronization for Time-Sensitive Applications in Bridged Local Area Networks|Timing and Synchronization for Time-Sensitive Applications (gPTP)<br>Precise synchronization<br>[802.1AS](http://www.ieee802.org/1/pages/802.1as.html)<br>[802.1AS-Rev](http://www.ieee802.org/1/pages/802.1AS-rev.html)|
|IEEE 1722-2011|Layer 2 Transport Protocol for Time Sensitive Applications in a Bridged Local Area Network|[IEEE 1722-2011](http://standards.ieee.org/findstds/standard/1722-2011.html)|
|IEEE 1733-2011|Layer 3 Transport Protocol for Time Sensitive Applications in Local Area Networks|[IEEE 1733-2011](http://standards.ieee.org/findstds/standard/1733-2011.html)|
|IEEE 1722.1-2013|Device Discovery, Enumeration, Connection Management and Control Protocol for 1722-Based Devices|[IEEE 1722.1-2013](http://standards.ieee.org/findstds/standard/1722.1-2013.html)|

URL(some require auth)


##Organization

###AVnu
To help ensure interoperability between devices that implement the AVB standards, the [AVnu Alliance](http://avnu.org) develops device certification for the automotive, consumer, and professional audio and video markets.

![AVnu](https://upload.wikimedia.org/wikipedia/commons/thumb/8/80/AVnu_certification_mark.jpg/300px-AVnu_certification_mark.jpg)

### IEEE

Audio Video Bridging Task Group of the IEEE 802.1
Time-Sensitive Networking Task Group(Nov, 2012)

##Benefits

* Improved synchronization
* Low-latency
* Reliability
* No infrastructure requirements
* Networked Live Sound

##AVB difference with 802 architectures

* Precise synchronization,
* Traffic shaping for media streams,
* admission controls, and
* Identification of non-participating devices.

##Requirements

synchronizing multiple streams to ensure they can be rendered correctly in time.
lip synch.
stringent applications: with 1us;
Applications must be able to reserve network resources, sometimes called admission control.[

##Protocol
