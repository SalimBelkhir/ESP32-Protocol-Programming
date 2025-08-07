# ESP32 Protocol Programming

![ESP32](https://img.shields.io/badge/ESP32-ESP--IDF-blue)

A comprehensive ESP32 project demonstrating multiple network TCP protocol via Socket programming

## Features

- **TCP Client/Server** - Basic socket communication


## Getting Started

### Prerequisites
- ESP-IDF v5.1+
- ESP32 or compatible board

run 
```
idf.py menuconfig 
```
Select->Example configuration->configure IP version (v4 or v6) -> Write your IP adress and port (mainly 8080)
You can know your IP adress with 
```
#Linux
ifconfig | grep "inet "
#Windows
 ipconfig 
```
Beware ! 
ESP32 and your local PC must be in the same Subnet e.g. connected in the same router 
for instance 
```
ESP32 IP @ : 192.45.1.x
Local PC IP @ : 192.128.1.x
Router IP @ : 192.168.1.x
both connected in the same subnet 1 
```
For Virtual Machines connect As bridge and not NAT 
```
#build
idf.py build
#flash
idf.py flash
#see the monitor
idf.py monitor
```
open another terminal and run netcat 
```
#if your port is 8080
nc -l 8080
#option -l is for istening for incoming connections rather than initiating a connection  to  a remote host.
```
what you should see : 

```
salim@salim-VMware-Virtual-Platform:~$ nc -l 8080
Message from ESP32
```
