# IoT Wireless Packet Capture & Analysis

## Overview

Built an embedded IoT monitoring device using an Adafruit Feather RP2040, a LoRa radio, an AirLift WiFi module, and an OLED display. The system monitors nearby LoRa traffic, shows live packet info right on the device, and exports captured packets in PCAP and PCAP-NG format for analysis in Wireshark.

![LoRa Monitor](https://raw.githubusercontent.com/jgafron/adafruit-wireless-capture/main/images/adafruit1.jpg)

*Live packet monitoring on the Adafruit Feather RP2040 showing packet count, RSSI, IP address, and the most recently received LoRa packet.*

## Core Features

- Live LoRa packet monitoring
- RSSI measurement
- OLED status display
- Packet decoding
- PCAP & PCAP-NG export
- Wireshark integration
- WiFi connectivity
- Passive hardware reconnaissance

## Hardware

- Adafruit Feather RP2040
- LoRa RFM95
- AirLift ESP32 WiFi
- OLED FeatherWing

## Skills Demonstrated

- Embedded Systems
- CircuitPython
- Wireless Networking
- Packet Analysis
- PCAP Generation
- USB Serial Communication
- Wireshark
- IoT Security

## My Contributions

I designed and built the embedded firmware from the ground up, pulling WiFi, LoRa, and OLED hardware into a single monitoring application rather than treating each module in isolation. I wrote support for multiple radio libraries (`rfm9xfsk` and `adafruit_rfm9x`) instead of hard-coding one implementation, then built out packet decoding, RSSI reporting, OLED telemetry, and packet counting in the main monitoring loop.

From there, I added a secondary USB CDC serial channel, implemented PCAP and PCAP-NG writers, generated timestamps with `time.monotonic()`, and streamed captured LoRa traffic to a host computer for live Wireshark analysis.

This also doubled as hands-on passive hardware reconnaissance work, monitoring and capturing traffic from nearby embedded IoT devices without transmitting anything myself.
