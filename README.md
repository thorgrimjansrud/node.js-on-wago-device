# Install Node.js on a Wago Device.
Be aware of the device partition sizes and space required for the installation and future apps/add-ons etc.
This example is based on 750-9301 (Compact Controller 100) with firmware 21, and requires some basic knowledge of Wago controllers.

## Setup
If the controller network card is not DHCP (default), this must be set to have an online connection to internet.

## Download Node.js
Latest version of Node.js found on homepage [Node.js.](https://nodejs.org/en/download/) <br/>
In this example we use Node v16.13.1.

Log in as root and make/select a folder:
```
cd /home
mkdir node
cd home
```
Get the Node.js tarball:
```
wget https://nodejs.org/dist/v16.13.1/node-v16.13.1-linux-armv7l.tar.xz
```
We must also have additional GCC support for atomic operations:
```
wget http://ftp.de.debian.org/debian/pool/main/g/gcc-6/libatomic1_6.3.0-18+deb9u1_armhf.deb
```
## Unpack and install Node.js:

Unpack Node.js in /home/node directory:
```
tar -xJvf node-v16.13.1-linux-armv7l.tar.xz -C /home/node
```
Unpack libatomic from .deb to /usr/lib directory:
```
ar x libatomic1_6.3.0-18+deb9u1_armhf.deb 
cp usr/lib/arm-linux-gnueabihf/libatomic.so.1 /usr/lib
```
If you want, clean up unwanted files:
```
rm control.tar.gz && rm data.tar.xz && rm debian-binary && rm libatomic1_6.3.0-18+deb9u1_armhf.deb && rm node-v16.13.1-linux-armv7l.tar.xz && rm -r usr
```
Set the environment variable ~/.profile to installation path:
```
# Nodejs
VERSION=v16.13.1
DISTRO=linux-armv7l
export PATH=/home/node/node-$VERSION-$DISTRO/bin:$PATH
```
Refresh:
```
. ~/.profile
```
Test:
```
node -v
npm version
npx -v
```
> Output would depend on version. <br/>
> Run prefered updates. <br/>

