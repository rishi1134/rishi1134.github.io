---
title: "V2V Communication using Free Space Optics"
collection: talks
permalink: /talks/ocn
order: 9
---

Another project I'm really proud of, where I combined the principles of Optical Communication and Networking to develop a Vehicle-to-Vehicle (V2V) communication system using optics as the communication medium. I designed an error-resilient communication protocol from scratch and successfully demonstrated the transmission of vehicle lane changes, braking, and speed information to another vehicle through a free-space optics medium. #V2V #Networking #FSO

Project developed as part of the coursework ECE4005 – Optical Communication Network in my undergrad. 

Working
===
![image res](../../images/ocn_block.png)

Hardware Setup
===
* Transmitter End 
![image res](../../images/ocn_cir1.png)

* Receiver End 
![image res](../../images/ocn_cir2.png)

Working
===
* At the Transmitter, It takes the input of speed/lane/brake information from the keypad and 
converts that into frame of bits and sends using LASER. 
* At Receiver, a LDR detects the light and based on the intensity it determines 1/0 and reforms 
the frame bits into meaningful info. Once this is done it sends the ACK. 
* At transmitter, it waits for a ACK for certain timeout period, if not received it retransmits 
again. During this transmission if the RX misses any bits, it can dynamically adjust the 
reception to the next incoming frame based on the header and trailer information. 

Frame 
The frame is 17 bits long and the data bits are 9 bits long.  
![image res](../../images/ocn_frame.png)

The dataword length is chosen based on the information transmitted range.  
- Lane change - 1 bits (Left/Right) 
- Braking - 1 bit (1/0) 
- Speed - 7 bit (MAX_SPEED = 127)

Synchronization 
===

* We implemented a header/trailer system with bit stuffing. Due to this additional feature the 
frames which are partially missed by the receiver, can be received again without much re
transmission. Header - 1011 , trailer - 1010. 
 
* The system follows Stop and Wait protocol.  The sender waits for a ACK from the receiver 
after each frame, if not received, transmitter sends the frame again. Right now the timeout 
period for acknowledgement is 1.5sec at the transmitter end.

![image res](../../images/ocn_op.jpg)

Bit Stuffing and De Stuffing 
===
![image res](../../images/ocn_op2.jpg)

