# PSD - Plastic Scintillation Detector
## Introduction
During my time at [CERN](https://home.cern/about) I worked in basic R&D on a novel additive manufactured plastic scintillation detector - which is fancy for "3d printed particle detector". Large parts of my work happened at [IdeaSquare - The Innovation Space at CERN](https://ideasquare.cern/), for whom I built an exhibition prototype - which this part of the repository revolves around. 
At this Point I want to thank all the wonderfull people I had the pleasure of working with, and that I spent so much time with.

## PSD explained
**PSD** stands for **P**lastic **S**cintillation **D**etector, and is a subclass of particle detectors utilising the scintillation properties of plastic based scintillating materials to detect and identify particles. For non-experts those already are a lot of heavy words, so let me explain.
From a general point of view a particle is a very very small portion of matter, like a dust particle. In particle physics the consideration of what is and what is not a particle is a bit more strict. Particles are the very building block of our existence, very much like a house is built from individual bricks or sticks. Everything is built from Molecules and atoms, Molecules themselves are made out of atoms, and atoms are made out of electrons, protons, and neutrons. These we consider particles - there are more, and also more specialized views on what we consider a particle and what not. However this shall suffice for our purposes. 
Compared to the dust particles from earlier (which we do not consider particles in this context), our particles are much much smaller, so much so that you cn barely imagine. You might think those particles do not move, or are very limited within their movement, however this is not true. The particles are usually consantly moving, vibrating, etc. Every secone Trillions of neutrinos (a specific kind of particle) pass through you at near light speed. Now for the special case of neutrinos they do usually not interact with you and leave you the same as they entered you. If you now were to wonder which particles are flying past you, you need a particle detector. A **particle detector** is a machine that measures specific changes in its environement and allows you to conclude how many of which kind of particles travelled through it.
The kind of changes a detector measures specify which kind of particles it can detect. And the way these changes are detected determine which kind or subclass of detector you are dealing with.
One of these subclasses are scintillation detectors. Scintillation is when a particle disrupts the electromagnteic field within a material, which causes flashes of light to be produced in a sort of chain reaction. Scientists use the location of the light flashes is used to determine the path, and the wavelength (color) of the light is used to determine how much energy the incoming particle had, and conclude from this how fast it went. The combination of these can be used to figure out which particle you are dealing with - every particle kind of has its own fingerprint, signature in that manner. This is concept roughly id how scientists determine which particle passes through where and when.
Lastly you need to know that not every material produces those light flashes, only specific ones called scintillating materials. One kind of scintillating materials are very specific and carefully engineerd plastics - they look notingh like the plastic you know from your everyday life, but rather like plastic glass, that may be slightly opaque.
Now you know what a plastic scintillting detector is: A particle detector utilizing scintillating plastic. Congrats!

## The Project
While working in R&D for a 3d printed PSD I was asked to prepare a prototype that would be used for exhibition purposes at IdeaSquare. The goal was to create a visualizing small functioning version of the prototype, that special guests could see, touch and experience.

Now what concept did I eventually come up with?
It is stupidly simple: A PSD, which visualizes its inner measurements both on screen, and with an LED setup.

## The Implementation
While the Concept might be stupidly simple, the implementation is not. 
Lets elaborate the setup required:
- Segmented Scintillation detector
- Pre-amp
- Computer
- Arduino
- LED Setup

Those five parts make up the whole setup. The detector itself consists of segmented scintillating material cubes, which are encapsuled by highly reflective walls, such that light created in a specific cube stays within that cube. The cubes are staged in a 3-dimensional array, giving a resolution similiar to pixel on a screen - just in 3d. Through the cubes run special optical fibers that will guide light out of the cubes onto a special aperature called a photo multiplier - which will translate the light into an electrical signal. The signal however is very weak, and needs to be amplified - this is done with a pre-amplifier (pre-amp). 
A Pre-amplifier is a very special kind of amplifier, it amplifies the electrical signal without amplifying noise. Noise, also called background, are random signals that are there at any given time, with or without the signal. Imagine you are trying to have a conversation in a restaurant, with lots of noise people aroun you. You have trouble understanding your friend. Now you could use a hearing aid that just makes everything louder, that might help, but if your friend whispers, you might want to opt for a more sophisticated hearing aid that filters all the noise around you out and leaves you with your friends whisper - which it amplifies additionally. This is the difference between a normal amplifyier and a pre-amp, your friends' whisper is the signal and the noise all around you is the background aka noise.
Within the pre-amplifier the enhanced signal is now converted from an analog electrical signal to a digital signal, and documented as a value called ADC value. This value is linearly correlated with the intensity of the amplified electrical signal.
The Pre-amp is now connected to a computer with a special software. The software controls the pre-amp, receives and documents the signals and can be used for further purposes we will ignore.
With a second software one can now read the data that we collected and visualize them with a 3-dimensional graphic on screen, or with a special LED setup shown below. For simplicity the LEDs are contolled via an Arduino-breadboard setup. The LEDs were mounted onto custom designed PCBs, allowing for control over both color, and brightness of the individual LEDs. The LEDs were used to visualize the concept of the inner measurements of the detector.
I am aware that this is a very superficial and simplified explanation, however a more detailed explanation would exceed the purpose of this explanation. If you wish to know more, there are plenty of great resources out there.
At this point huge thanks to my research group and collaboration, it was a fantastic time!

During this project I designed and installed the following components:
1. Assembly of scintillation cubes
2. Preperation, and installation of optical fibers
3. Case design for detector, and photomultiplier
4. Firmware adaptation of pre-amp components (C, C++)
5. Visualization software combined with the communication software with Arduino (Python)
6. Arduino software for receiving information and controlling the LEDs (C)
7. PCB design of LED setup
8. Overall design of the exhibition prototype

What I did not design:
1. The Pre-amp and its software (which was provided by the company designing and manufacturing the Pre-amp)
2. Detector design (which had been ideated by the supervisor of my master thesis)

