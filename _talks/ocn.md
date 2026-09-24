---
title: "Vehicle-to-Vehicle Communication using Free Space Optics"
collection: talks
permalink: /talks/ocn
level: Undergraduate
year: "2020"
category: exploratory
order: 4
header:
  teaser: /images/ocn_block.png
teaser: /images/ocn_block.png
tags: ["Free-Space Optics", "Embedded Telemetry", "V2V Communication", "Protocol Design"]
affiliation: "Optical Communication Networks (ECE4005) | VIT"
excerpt: "Line-of-sight Free-Space Optical (FSO) vehicle-to-vehicle communication system featuring a custom error-resilient framing protocol, bit stuffing, and stop-and-wait telemetry transmission."
---

## Overview

Radio frequency (RF) bands utilized for vehicular communications face increasing spectrum congestion and susceptibility to electromagnetic interference. Free-Space Optics (FSO) offers an alternative, highly directional line-of-sight communication medium with high data integrity.

In this project, developed for *ECE4005 - Optical Communication Networks* at Vellore Institute of Technology, I designed and prototyped an end-to-end Free-Space Optical Vehicle-to-Vehicle (V2V) telemetry system from scratch, complete with custom transceivers, a physical-layer framing protocol, and error-recovery mechanisms.

---

## System Architecture

![System Block Diagram](../../images/ocn_block.png)
*Figure 1: Transmitter and receiver hardware architecture for optical vehicle telemetry.*

---

## Hardware Implementation

### 1. Transmitter Circuit
Input telemetry (braking status, lane-change indicators, speed) is collected from vehicle control interfaces, framed by an embedded microcontroller, and modulated onto a collimated laser diode transmitter.

![Transmitter Circuit](../../images/ocn_cir1.png)
*Figure 2: Laser transmitter circuit schematic and driver stage.*

### 2. Receiver Circuit
A high-sensitivity photodetector array receives the modulated optical signal, applies thresholding to resolve binary pulses, and passes the bitstream to the receiver microcontroller for frame synchronization and telemetry decoding.

![Receiver Circuit](../../images/ocn_cir2.png)
*Figure 3: Optical receiver circuit schematic with signal conditioning.*

---

## Protocol Design & Synchronization

### Frame Structure
A custom 17-bit frame was designed to balance throughput with error recovery over optical channels:
- **Header**: 4 bits (`1011`)
- **Data Payload**: 9 bits:
  - Lane change indicator: 1 bit (Left / Right)
  - Braking alert: 1 bit (Active / Inactive)
  - Vehicle speed: 7 bits (0 – 127 km/h range)
- **Trailer**: 4 bits (`1010`)

![Frame Structure](../../images/ocn_frame.png)
*Figure 4: 17-bit optical telemetry packet structure.*

### Error Recovery & Bit Stuffing
- **Bit Stuffing**: Implemented bit-stuffing rules to ensure that reserved header and trailer flag sequences do not appear within the data payload, preventing false synchronization.
- **Stop-and-Wait ARQ**: Sender transmits a frame and waits for an optical acknowledgment (ACK). If no ACK is received within a 1.5-second timeout window, the frame is retransmitted. The receiver dynamically resynchronizes to the next incoming frame using header flag detection if intermediate bits are dropped.

![Bit Stuffing and Output Waveforms](../../images/ocn_op.jpg)
*Figure 5: Oscilloscope traces showing transmitted and received optical pulse streams under synchronization.*
