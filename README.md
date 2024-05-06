----------------------------------
OpenMCU-ru Video Conference Server
----------------------------------

Authors are listed in [AUTHORS.md](AUTHORS.md).

License: [LICENSE.md](LICENSE.md).
  * Some plugins have other open-source licenses - see the appropriate files in the plugin folders.

Installation instructions: [INSTALL.md](INSTALL.md).

News: [ChangeLog](ChangeLog).

---------------
1. Introduction
---------------

OpenMCU-ru is an open-source Mutli Conference Unit using the H.323, SIP and RTSP
protocols (software MCU). It is a fork of the original OpenMCU with many new features.
Server runs on Linux, Windows and FreeBSD.

-----------
2. Features
-----------

OpenMCU-ru has the following features:
  * Web interface to configure and control the server
    (to connect: http://host:1420)
  * Multiple interface languages: English, French, Japanese, Portuguese, Russian, Ukrainian
  * Multiple VoIP protocols: H.323, RTSP, SIP
    - Built-in H.323 Gatekeeper
    - Built-in SIP registrar
    - RTSP server and client
    - Internal calls (including different-protocol transcoding)
  * Video codecs: H.261, H.263, H.263+, H.264, MP4V-ES, VP8
  * Audio codecs: G.711, G.722, G.722.1, G.722.1C, G.722.2, G723.1, G.726, G.729, iLBC, Speex, SILK, OPUS
  * Does not require codec hardware to operate
  * Outgoing video caches to reduce the load on the server
  * Multiple conference rooms
  * Real-time call statistics
  * Call initiation from the MCU to remote endpoints
  * Conference recording
  * Conference streaming


------------
3. Operation
------------

OpenMCU-ru listens on H.323 and SIP ports for incoming connections.

On an incoming connection, server creates the room specified by remote
terminal and connects the client to it. If a client does not specify
any room then it will be connected to the default room ("room101",
can be changed in options).

You can call to the server using the destination address:
"room_name@hostname_or_ip_address".

The new rooms are created automatically when they are accessed.
Also, there is a default room - for the clients calling without
the name of the room (e.g NetMeeting is unable to specify it).

During the conference you hear other members and see them in the video
window. You can set up Voice activation detection (VAD), change the
layout of the conference and configure other parameters.
