---
title: " Pi-Eye: Visual Aid for the Colour Blind"
collection: talks
permalink: /talks/pieye
order: 6
---

Yet another project I am proud of is Pi-Eye. This system empowers individuals with severe or mild color blindness (total absence of cone cells) to identify the color of an object as well as its name. Additionally, it assists individuals with mild visual impairments in recognizing objects within their field of view. The system processes input frames from a camera and remains idle until the user points to an object using a pointer pen. It then activates an audio output, announcing the name and color of the object.

Project developed as part of the coursework ECE4003– EMBEDDED SYSTEMS DESIGN in my undergrad. 

Working
===
![image res](../../images/pieye_block.png)

We developed the system with two distinct modes of operation: MinMode and MaxMode, each designed to adapt based on the battery level of the system.

In MinMode, the system operated with minimal power consumption when the battery level was low. In this mode, the user manually selected the frame they wanted to process by triggering an interrupt through a switch. The system, upon receiving this input, used TensorFlow's object detection API to identify all objects within the frame. For each detected object, it determined the dominant color and the object’s name, delivering this information to the user via an audio jack.

On the other hand, MaxMode was activated when the battery level exceeded a specific threshold. In this mode, the system processed every incoming frame from the camera. The user interacted with the system using a pointer pen to indicate the object they wanted information about. This action generated an interrupt, prompting the system to analyze the previous frame stored in the frame buffer. A neural network model, trained to detect the pointer pen, identified the region of the object being pointed to. Within that region, TensorFlow's object detection API determined the object's name (if applicable) and its dominant color, which was then conveyed to the user through audio output.

Throughout the operation, the user was informed of the current mode (MinMode or MaxMode) via the audio device. This project demonstrated an innovative application of free-space optics and neural networks to provide real-time assistance, particularly to individuals with visual impairments. It was an incredibly fulfilling challenge to design and implement!

Demo Video
===

Guess what I stumbled upon—an ancient draft of our demo video. Watch at your own risk, though; it’s practically a roller coaster in disguise and might come with a side of motion sickness. Consider it a workout for your equilibrium!
[Demo Video](https://drive.google.com/file/d/1UOnIgLff9UmnFGvDaFxGuVn7YWzoan8s/view?usp=sharing)