#AVB Summary & note

[TOC]

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
[AVB/TSN](https://avb.statusbar.com/page/)

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

##AVB Glossary

###Audio Channel

One monophonic audio signal

###Audio Cluster

A group of audio channels in a stream.

Examples:

* A single channel of audio
* A single S/PDIF or AES3 connection which may contain a stereo audio signal with meta-data or an encoded 5.1 surround-sound audio.

###Audio Map

A static mapping between an audio Stream’s channels and an Audio Cluster’s channels for Streams and Stream Ports.

Example:

* The Audio Map allows you to select which Audio Channels within which Audio Clusters in a Stream will be processed. For instance, an Audio Map could select: The “Third Channel” from the second 8 audio channel stream by choosing Channel 0 from Cluster 3 from the second audio stream

###Audio Unit

Contains Signal processing for a single Audio Clock Domain.

Example:

* If a device had the capability of doing processing in multiple clock domains at the same time, the processing for each clock domain would be done within a separate Audio Unit.

###AVB Interface

An AVB capable network interface capable of sourcing or sinking Streams and participating in an AVB domain.

###AVDECC

The Acronym used to refer to IEEE Std 1722.1-2013 (Audio Video Discovery Enumeration Connection and Control)

###AVDECC Entity

A logical object within an End Station that can accept and respond to AVDECC messages.

Example:

* A device may contain more than one AVDECC Entity. Typically, an AVB device will only contain one AVDECC Entity. As far as the AVDECC Controller is concerned, two entities on one device is indistinguishable from two devices with one entity each. One use case for having two AVDECC Entities in one device is to partition it - allow one user to use one portion of a device while allowing another user on the network to change settings on another portion of the same device but not allowing the two users to affect each other’s settings.

###Descriptor

A machine-readable description of an object within the AVDECC Entity data Model (AEM). Each descriptor has a Descriptor Type and a Descriptor Index.

Example:

* An AVB_INTERFACE Descriptor describes an AVB Interface. A JACK_INPUT descriptor describes an Input Jack. There are descriptors for every user-relevant aspect of the device. A controller program can ask a device for these descriptors to learn about the capabilities of the device to present to the user.

###Entity ID

The EUI-64 identifier (IEEE-defined 64-bit Extended Unique Identifier) of an AVDECC Entity. The Entity ID is based on the device’s ethernet port’s MAC address, the value of the top bits of which are purchased by a manufacturer from IEEE. The Entity ID for a specific device is a globally unique number.

###Entity Model ID

The EUI-64 identifier of an AVDECC Entity data Model (AEM). This is a unique number that the manufacturer assigns to device every time a new version of the entity model / object layout / processing structure changes.

Example:

* If a controller sees two devices on the network with the same Entity Model ID, then it will know that these two devices have identical capabilities and processing structure without having to interrogate both of the devices.

###Input Stream

A Stream that is received by an AVB Listener.

###Jack

An ingress or egress point of a non-media-stream signal to or from an AVDECC Entity.

Example:

* Typically, a Jack represents a physical connector on a device. A Jack may also be called “Captive” if the logical connector is internal only such as a connection to an amplifier for an embedded speaker driver.

###Localized Description

A textual description of an object within the AVDECC Entity data Model (AEM) which can be represented in multiple languages. These descriptions are only set by the manufacturer of a device and the user can not change them.

Example:

* An Input Jack may have a Localized Description which would contain the equivalent to the text that is printed on the Silk Screen on the chassis for the jack. Since manufacturers may have different silkscreens for different markets, the data model can contain the multiple languages as well.

###Matrix

A collection of orthogonal Controls arranged in a two dimensional array.

Examples:

* 8 Audio Channel signals are sent to an 8x16 Matrix. The Matrix contains 128 “level” control points (represented in decibels), one for each combination of 8 inputs and 16 outputs. The Matrix mixes each input to each output based on the cross point level and outputs 16 Audio Channel signals.
* 32 Audio Channel signals are sent to an 32x32 Matrix. The Matrix contains 1024 control points, each with a “level” value (represented in decibels) and “delay” value (represented in seconds), one for each combination of 32 inputs and 32 outputs. The Matrix mixes and delays each input to each output and outputs 32 Audio Channel Signals.

###Mixer

A Control that combines multiple signals into a single output signal.

Example:

* 8 Audio Channel signals are sent to a Mixer. The Mixer contains one “level” control point per input (represented in decibels). The 8 inputs are mixed with the appropriate levels and outputs one Audio Channel signal.

###Media component

Fundamental data within an IEEE Std 1722 stream payload.

Examples:

* A single channel of audio
* A single S/PDIF or AES3 connection containing stereo audio and meta data
* A single S/PDIF or AES3 connection containing encoded 5.1 audio
* MPEG video

###Object Name

A 64 character UTF8 name of an object which the user may be able to set, if the device allows it.

Example:

* Almost all objects (Descriptors) can have a user settable name. The most likely objects to have user settable names are the device (Entity), Stream Inputs, Stream Outputs, Input Jacks, and Output Jacks.

###Port

An ingress or egress point of a signal for a Unit (one clock domain).

Example:

* There are Audio Ports, Video Ports, and Sensor Ports, which correspond to processing done in Audio Units, Video Units, and Sensor Units.

###Sub-Signal, Signal, Multi-channel Signal

'part of' or 'one or more media components'.

Examples:

* Video portion from MPEG Video data
* Audio from an MPEG Video data
* Closed captioning from MPEG Video data
* A single S/PDIF or AES3 connection.
* A single audio channel

###Signal Selector

A Control for switchable signal routing.

Example:

* A Signal Selector would be used to select audio coming from an analog input jack signal, a digital input jack signal, or an audio channel signal from an AVB stream. Only one source may be selected at a time.

###Signal Splitter

A Control for splitting a signal into multiple sub-signals.

Examples:

* A Signal Splitter would be used to extract the 6 individual Audio Channels from an encoded 5.1 encoded S/PDIF signal. In this case, there would be one S/PDIF signal going into the Signal Splitter, and there would be 6 single audio channel signals coming out of the signal splitter.
* A Signal Splitter would be used to extract the video media component and the audio media component from an MPEG transport stream. In this case there would be one MPEG video signal going into the Signal Splitter, and there would be one video signal and one MP3 encoded audio stream signal coming out of the signal splitter.

###Signal Demultiplexer

A Control for demultiplexing a signal into multiple signals.

Example:

* MIDI data sent over an AVB Stream is transported in an Audio Cluster. One Audio Cluster contains up separate 8 MIDI Cables worth of MIDI data which are all multiplexed together. A Signal Demultiplexer would be used to extract the 8 MIDI cables from the one Audio Cluster into 8 individual MIDI cable signals.

###Stream

A unidirectional flow of IEEE Std 1722 frames with the same StreamID.

Examples:

* A stream can be a single channel of audio
* An MPEG video stream with embedded audio
* An 8 channel stream
* One or more S/PDIF lines
* SMPTE time code
* MIDI messages

###Stream Input

A Stream Input defines a the part of a device that receives a single AVB Stream and tracks the format and stream status.

###Stream Port Input

An ingress point of an AVB Stream into an Audio Unit

Example:

* The Stream Input receives the AVB stream and sends it to the appropriate Audio Unit for processing within a Clock Domain via a Stream Port Input.

##Terminology

|Name|Full Name|Comment|
|:-|:-|:-|
|AVB|Audio Video Bridging||
|TSN|Time Sensitive Networking||
|[AES3(aka AES/EBU)](https://en.wikipedia.org/wiki/AES3)| a standard for the exchange of digital audio signals between professional audio devices.|Developed by the Audio Engineering Society (AES) and the European Broadcasting Union (EBU).<br>AES3 has been incorporated into the International Electrotechnical Commission's standard [IEC 60958](https://en.wikipedia.org/wiki/IEC_60958).<br>, and is available in a consumer-grade variant known as [S/PDIF](https://en.wikipedia.org/wiki/S/PDIF).|
|[S/PDIF](https://en.wikipedia.org/wiki/S/PDIF)|Sony/Philips Digital Interface|The signal is transmitted over either a coaxial cable with RCA connectors or a fibre optic cable with TOSLINK connectors. S/PDIF interconnects components in home theatres and other digital high-fidelity systems.<br><br>IEC 60958 Type I—Balanced, XLR<br>![XLR connectors](https://upload.wikimedia.org/wikipedia/commons/thumb/1/15/Xlr-connectors.jpg/450px-Xlr-connectors.jpg)<br><br>IEC 60958 Type II—Unbalanced, RCA<br>![RCA connectors](https://upload.wikimedia.org/wikipedia/commons/thumb/9/91/Composite-cables.jpg/450px-Composite-cables.jpg)<br><br>IEC 60958 Type III Optical—Fiber, F05/TOSLINK<br>![TOSLINK connector](https://upload.wikimedia.org/wikipedia/commons/thumb/4/4d/TOS_LINK_clear_cable.jpg/330px-TOS_LINK_clear_cable.jpg)<br><br>Composite Video RCA connector(yellow)<br>![Composite Video RCA connector yellow](https://upload.wikimedia.org/wikipedia/commons/thumb/c/cd/Composite-video-cable.jpg/263px-Composite-video-cable.jpg)<br>|
|SDI|Serial digital interface (SDI)|a family of digital **video** interfaces first standardized by SMPTE (The Society of Motion Picture and Television Engineers) in 1989.<br>![SDI](https://upload.wikimedia.org/wikipedia/commons/thumb/b/b2/BNC_connector_%28male%29.jpg/330px-BNC_connector_%28male%29.jpg)|
|ADAS|Advanced driver-assistance systems||
|MOST|Media Oriented System Transport||
|[LIN](https://en.wikipedia.org/wiki/Local_Interconnect_Network)|(Local Interconnect Network) a very low cost in-vehicle sub-network||
|[FlexRay](https://en.wikipedia.org/wiki/FlexRay)|a general purpose high-speed protocol with safety-critical features|FlexRay is an [automotive network communications protocol](https://en.wikipedia.org/wiki/Vehicle_bus) developed by the FlexRay Consortium to govern on-board automotive computing. It is designed to be faster and more reliable than [CAN](https://en.wikipedia.org/wiki/Controller_Area_Network) and [TTP](https://en.wikipedia.org/wiki/Time-Triggered_Protocol), but it is also more expensive. The FlexRay consortium disbanded in 2009, but the FlexRay standard is now a set of ISO standards, ISO [17458-1](http://www.iso.org/iso/home/store/catalogue_tc/catalogue_detail.htm?csnumber=59804) to [17458-5](http://www.iso.org/iso/home/store/catalogue_tc/catalogue_detail.htm?csnumber=59809). |
|[IVI](https://baike.baidu.com/item/ivi/1069515)|In-Vehicle Infotainment|IVI能够实现包括三维导航、实时路况、IPTV、辅助驾驶、故障检测、车辆信息、车身控制、移动办公、无线通讯、基于在线的娱乐功能及TSP服务等一系列应用，极大的提升的车辆电子化、网络化和智能化水平。|
|ICE|In-Car entertainment|同上|
|RSES|Rear Seat Entertainment System|同上|
|HUD|Head Up Display||
|AAA2C|Avnu Automotive Advisory Council ||
|[AVTP]((http://avnu.org/wp-content/uploads/2014/05/AVnu-AAA2C_Audio-Video-Transport-Protocol-AVTP_Dave-Olsen.pdf))|Audio Video Transport Protocol||