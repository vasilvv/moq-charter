# Draft Charter for Media over QUIC

Media over QUIC (moq) will work on solution for a simple low-latency 
media delivery protocol for ingest and distribution. 
This work may address use cases including live streaming, gaming, and 
media conferencing and allows efficient scaling. The solution supports 
both web browsers and simple devices that don’t contain embedded browsers. 
 
The work focuses on building protocol mechanisms for publication of media 
and ways to identify and receive the media.

The media publication protocol will be a push protocol for sending 
media including audio, video, and timed metadata.
The common protocol for publishing media over ingest and distribution 
will support:

* one or more media formats, 
* an interoperable way to request media and encodings,
* rate adaption strategies based on changing codec rates, changing chosen media encoding/qualities,  
* a cache friendly media mechanisms. 

The mechanism to name and receive media will enable:

* Requesting server start sending media related to given point in the stream
* Cue points
* Integration with captions
* Selection of desire encoding ( choosing language, bit rate , etc ) 

Media will be mapped onto underlying QUIC mechanisms (QUIC Streams and/or
QUIC datagrams) and can be used over raw QUIC or WebTransport.

The proposed solution provides extensibility for supporting different 
media formats and shall specify a mandatory to implement media format to ensure interoperability. Support for multiple media types, media encodings shall be proposed, in addition to a simple method of authentication to access media as well as carrying information for additional decryption of media payloads where required.
  
The MOQ architecture allows for the use of optional relays as first 
class elements of the design. The media publication protocol can 
leverage on-path relays/caches wherever applicable to improve the 
media quality. Media is encrypted, possibly end-to-end encrypted 
for certain usecases. The keying mechanisms for media confidentiality
is however outside the scope of this working group. Even when media is 
end-to-end encrypted, the relays can access metadata needed for caching
such as timestamp, making media forwarding decisions (such as drop or 
delay under congestion) and so on.
 
This working group will not propose changes to underlying QUIC 
transport, but may propose requirements for QUIC extensions to the QUIC WG. This working group will not define signaling mechanisms for discovery of relay or media producers or consumers. 
 
This working group will coordinate with the QUIC and WebTransport working 
groups as needed. It will liaise with MPEG-DASH, and W3C WebTransport 
as appropriate. 
 
## Milestones

* WG adoption of Protocol Specification for Common Media Publication Protocol over QUIC
* WG adoption of Protocol Specification for Datagram Extension to Media Publication Protocol over QUIC
* WG adoption of Protocol Specification for Media Subscription Protocol over QUIC
* WG adoption of Architecture Specification for a Common Media Delivery Protocol over QUIC draft
* WG adoption of Usescase and Requirements document for Media Delivery over QUIC - decision about whether to forward to IESG for publication to be made later, by WG consensus  
* Forward Protocol Specification for Common Media Publication Protocol over QUIC draft to IESG
* Forward Protocol Specification for Datagram Extension to Media Publication Protocol over QUIC draft to IESG
* Forward Protocol Specification for Media Subscription Protocol over QUIC draft to IESG
* Forward Architecture Specification for a Common Media Delivery Protocol over QUIC draft to IESG
