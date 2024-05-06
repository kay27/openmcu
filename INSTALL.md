# OpenMCU-ru Installation

There are three ways of installing OpenMCU-ru:
 * from a packet;
 * through one-click installation script;
 * manual build.

## One-Click Installation Script

There is a script that tries to do all the work automatically:
 * [stuff/openmcu-oci](stuff/openmcu-oci)

There is no guarantee though, because it is a bit outdated.

## Dependencies

### Mandatory:
 * build tools: `gcc make flex bison autoconf automake pkg-config`
 * FFmpeg >= 0.10.4 - http://www.ffmpeg.org
     * or Libav >= 0.8  - http://libav.org
 * libx264          - http://www.videolan.org/developers/x264.html
 * libvpx >= 1.0    - http://webm.googlecode.com

### Optional (will be used if present in system):
 * FreeType (http://freetype.org/)
 * libjpeg-turbo (http://libjpeg-turbo.virtualgl.org/)
     * or libjpeg (http://ijg.org/)

### Built-In

OpenMCU-ru contains the following required libraries right in its repository:
 * PTLib            - http://www.opalvoip.org
 * H323Plus         - http://www.h323plus.org
 * Sofia-SIP        - http://www.sofia-sip.sourceforge.net
 * libSRTP          - http://srtp.sourceforge.net/srtp.html
 * libzrtp          - http://zfoneproject.com/prod_sdk.html
 * libyuv           - http://www.code.google.com/p/libyuv

### For Ubuntu users

Use the following lines to install build dependencies on Ubuntu:
```
  apt-get install gcc make flex bison autoconf automake pkg-config
  apt-get install libtool
  apt-get install libavcodec-dev
  apt-get install libavformat-dev
  apt-get install libswscale-dev
  apt-get install libfreetype6-dev
  apt-get install libssl-dev
  apt-get install libx264-dev
  apt-get install libvpx-dev
```

## Build on Linux

```
./autogen.sh
./configure
make
make install
```

## Build on FreeBSD

```
./autogen.sh
./configure
gmake
gmake install
```

## Build on Windows

Build using Microsoft Visual Studio in the following order:
 * ptlib\ptlib_*.sln
 * h323plus\h323plus_*.sln
 * openmcu-ru\win\openmcu_*.sln

## Build and Start in the Docker container

```
cd Docker/openmcu-ru/centos-7
docker build -t openmcu-ru .
docker run --network=host -d openmcu-ru
```
