# rak7200_config

A tool to configure a [RAK7200](https://store.rakwireless.com/products/rak7200-lpwan-tracker).

## Introduction

The RAK7200 is a LoRA GPS tracker with an AT command set.  This tool
can configure the device from the command line as well as monitor the
console.

## Invocation

```
./rak7200_config [-v] [-d] [--baud 115200] --port /dev/tty.usbserial-1420 COMMAND
```

Where:

* -v enables verbose logging
* -d enabled debug logging
* --baud sets a baud rate (defaults to 115200)
* --port specifies the serial port (system specific)

## Commands

### show

Show displays status of the device, the options are:

#### all-channels

Show all channels available in the region

```text
Channel State   Frequency       ??      ??      Star?
0       off     902.3 MHz       0       3       False
1       off     902.5 MHz       0       3       False
2       off     902.7 MHz       0       3       False
3       off     902.9 MHz       0       3       False
4       off     903.1 MHz       0       3       False
5       off     903.3 MHz       0       3       False
6       off     903.5 MHz       0       3       False
7       off     903.7 MHz       0       3       False
8       on      903.9 MHz       0       3       True
9       on      904.1 MHz       0       3       True
10      on      904.3 MHz       0       3       True
11      on      904.5 MHz       0       3       True
12      on      904.7 MHz       0       3       True
13      on      904.9 MHz       0       3       True
14      on      905.1 MHz       0       3       True
15      on      905.3 MHz       0       3       True
16      off     905.5 MHz       0       3       False
17      off     905.7 MHz       0       3       False
18      off     905.9 MHz       0       3       False
19      off     906.1 MHz       0       3       False
20      off     906.3 MHz       0       3       False
21      off     906.5 MHz       0       3       False
22      off     906.7 MHz       0       3       False
23      off     906.9 MHz       0       3       False
24      off     907.1 MHz       0       3       False
25      off     907.3 MHz       0       3       False
26      off     907.5 MHz       0       3       False
27      off     907.7 MHz       0       3       False
28      off     907.9 MHz       0       3       False
29      off     908.1 MHz       0       3       False
30      off     908.3 MHz       0       3       False
31      off     908.5 MHz       0       3       False
32      off     908.7 MHz       0       3       False
33      off     908.9 MHz       0       3       False
34      off     909.1 MHz       0       3       False
35      off     909.3 MHz       0       3       False
36      off     909.5 MHz       0       3       False
37      off     909.7 MHz       0       3       False
38      off     909.9 MHz       0       3       False
39      off     910.1 MHz       0       3       False
40      off     910.3 MHz       0       3       False
41      off     910.5 MHz       0       3       False
42      off     910.7 MHz       0       3       False
43      off     910.9 MHz       0       3       False
44      off     911.1 MHz       0       3       False
45      off     911.3 MHz       0       3       False
46      off     911.5 MHz       0       3       False
47      off     911.7 MHz       0       3       False
48      off     911.9 MHz       0       3       False
49      off     912.1 MHz       0       3       False
50      off     912.3 MHz       0       3       False
51      off     912.5 MHz       0       3       False
52      off     912.7 MHz       0       3       False
53      off     912.9 MHz       0       3       False
54      off     913.1 MHz       0       3       False
55      off     913.3 MHz       0       3       False
56      off     913.5 MHz       0       3       False
57      off     913.7 MHz       0       3       False
58      off     913.9 MHz       0       3       False
59      off     914.1 MHz       0       3       False
60      off     914.3 MHz       0       3       False
61      off     914.5 MHz       0       3       False
62      off     914.7 MHz       0       3       False
63      off     914.9 MHz       0       3       False
64      off     903.0 MHz       4       4       False
65      off     904.6 MHz       4       4       False
66      off     906.2 MHz       4       4       False
67      off     907.8 MHz       4       4       False
68      off     909.4 MHz       4       4       False
69      off     911.0 MHz       4       4       False
70      off     912.6 MHz       4       4       False
71      off     914.2 MHz       4       4       False
```

#### channels

Show enabled channels

```text
Channel State   Frequency       ??      ??      Star?
8       on      903.9 MHz       0       3       True
9       on      904.1 MHz       0       3       True
10      on      904.3 MHz       0       3       True
11      on      904.5 MHz       0       3       True
12      on      904.7 MHz       0       3       True
13      on      904.9 MHz       0       3       True
14      on      905.1 MHz       0       3       True
15      on      905.3 MHz       0       3       True
```

#### commands

Show all AT commands supported by the device

#### device

Show device status

```text
.
*************************************************
===============Device Status List================
Board Core:  S76G_B
MCU:  STM32L073RZ
LoRa chip:  SX1276

Battery Voltage = 3.867 V
Support Gps:true
gps_timeout: 100s
gps_format:standard LPP format
No signal with Satellite.

MPU9250 sensor:
Acceleration(g) of X,Y,Z:
1.04,0.01,0.00
Gyro(degress/s) of X,Y,Z:
0.32,1.42,0.26
Magnetometer(uT) of X,Y,Z:
-15.15,0.30,-44.10

===================List End======================
*************************************************
```

#### lora

Show LoRa config and status

```text
 Work Mode: LoRaWAN
Region: US915
Send_interval: 600s
Auto send status: false.
Join_mode: OTAA
DevEui: XXXXXXXXXXXXXXXX
AppEui: XXXXXXXXXXXXXXXX
AppKey: XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
Class: A
Joined Network:true
IsConfirm: unconfirm
AdrEnable: true
EnableRepeaterSupport: false
RX2_CHANNEL_FREQUENCY: 923300000, RX2_CHANNEL_DR:8
RX_WINDOW_DURATION: 3000ms
RECEIVE_DELAY_1: 1000ms
RECEIVE_DELAY_2: 2000ms
JOIN_ACCEPT_DELAY_1: 5000ms
JOIN_ACCEPT_DELAY_2: 6000ms
Current Datarate: 3
Primeval Datarate: 3
ChannelsTxPower: 0
UpLinkCounter: 0
DownLinkCounter: 0
```

#### version

Show the device version

```text
3.1.0.13
```

### config

Set configuration of the device.  Use 

```
$ ./rak7200_config --port /dev/tty.usbserial-1420 config --help
```

To see all the available configuration options

### join

Request the device join the LoRa network

```text
$ ./rak7200_config --port /dev/tty.usbserial-1420 join
join: OTAA:
```

### restart

Restart the device

```text
$ ./rak7200_config --port /dev/tty.usbserial-1420 restart
,restart ...
```

### monitor

Monitor the serial console.  In this mode, single character commands
can be used to request status or perform actions, they are:

```
C       List channels
H       List commands
J       Join
L       LoRa Status
R       Restart Device
S       Device Status
V       Device Version
Q,^C    Quit monitor mode
?       Display this message
```

Example:

```text
./rak7200_config --port /dev/tty.usbserial-1420 monitor
Restart Device: set_config=device:restart
OK,restart ...


========================================================
______  ___   _   __  _    _ _          _
| ___ \/ _ \ | | / / | |  | (_)        | |
| |_/ / /_\ \| |/ /  | |  | |_ _ __ ___| | ___  ___ ___
|    /|  _  ||    \  | |/\| | | '__/ _ \ |/ _ \/ __/ __|
| |\ \| | | || |\  \ \  /\  / | | |  __/ |  __/\__ \__ \
\_| \_\_| |_/\_| \_/  \/  \/|_|_|  \___|_|\___||___/___/
========================================================
********************************************************
RAK7200 version:3.1.0.13
********************************************************
========================================================
Please Configurate parameters within 30 seconds ...
lorasend_interval: 600s
MPU9250 Init OK
GPS Init OK
Initialization OK,Current work_mode:LoRaWAN, join_mode:OTAA, Class: A
gps_timeout: 100s
Configuration OK!
OTAA Join Start...
[LoRa]:Joined Successed!
```

## Finding the serial port

### macOS

```bash
$ ls /dev/tty.usbserial*
/dev/tty.usbserial-1420
```

The last four digits will change.

## Environment

Tested on macOS Catalina with python 3 installed by homebrew.  Should
work on Linux

Requires [pyserial](https://pypi.org/project/pyserial/)

```bash
pip install pyserial
```

Tested with RAK7200 3.1.0.13

## TODO

* Add standard format for enable/disable yes/no true/false
  * `confirm [yes|no|true|false|enable|disable]`
* What are all the columns (and the star) in Channel list?
* Re-enable sending valid AT commands
* Test on Linux
* Test on Windows or WSL

* Add options
  * Enable/Disable GPS - at+set_config=device:gps:X
  * Configure GPS timeout - at+set_config=device:gps_timeout:X
  * Configure GPS Format - at+set_config=device:gps_format:X
  * configure LoRa DR - at+set_config=lora:dr:X
  * configure LoRa send_interval - at+set_config=lora:send_interval:X:Y

## Issues

1. Trying to mask/unmask multiple channels seems intermittent, how long does it take?
1. Both my devices go dead after a while, what's up with that?

## LICENSE

Copyright 2020 Jeffrey C Honig <jch@honig.net>

Licensed under the Apache License, Version 2.0 (the "License"); you
may not use this file except in compliance with the License.  You may
obtain a copy of the License at http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or
implied.  See the License for the specific language governing
permissions and limitations under the License.
