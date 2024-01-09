# CREATING YOUR OWN SYNTHESIZER
#### Why do you need to be able to create your own synthesizers?
- To understand well how different synthesizers work
- To understand logic and be able to use various other visual constructors to build your own synthesizers
- To create your own unique procedural sound systems (for example, as in the game ["No Man's Sky"](https://youtu.be/zKJ_XuQjjiw?si=2arQ-Z844xnpbwW-&t=2198)
- To create your own unique solutions or your own convenienceм

Plugins from the company [LeSound](https://lesound.io/)a good example of unique procedural systems for specific tasks.

---
As we have already learned, synthesizers usually generate harmonics that are related to the main tone. The number of harmonics depends on the type of wave that is selected in the oscillator.

[Waveforms and harmonics](Волны%20и%20гармоники.canvas)
![](Волны%20и%20гармоники.png)

---

#### How to recreate a sound in which the number of harmonics is not a multiple?

![](Spector_Metal_Impact.png)
![](Metal_Impact.wav)

**The first way:** You can create many synthesizers inside the DAW, select a sine wave inside the oscillator and repeat all harmonics. The disadvantages of this method is that not all synthesizers have the ability to enter the desired frequency in numbers, so each harmonic will have to be adjusted manually using pitch and fine. Also, this method is very resource-intensive, since we will have to create a very large number of synthesizers. 

**The second method:** Create your own synthesizer that would meet all our needs.
![](Reaktor6_Impact_synth.png)
---
#### Where can I build my own synthesizer?
- [Max MSP](https://cycling74.com/products/max)
- [Pure Date](https://puredata.info/)
- [Reaktor6](https://www.native-instruments.com/en/products/komplete/synths/reaktor-6/)
These are all visual programming languages

As part of our lesson, we will create a synthesizer in Reactor 6 constructors, since it can be opened inside a DAW, as well as as a separate standalone application.

 > [!note] 
 > [REAKTOR USER LIBRARY](https://www.native-instruments.com/en/reaktor-community/reaktor-user-library/)- a section on the site **Reactor 6** where you can download and familiarize yourself with examples of various synthesizers, effects, midi effects created by other users. 
 > Don't forget to create an account on Native Instruments, otherwise you won't be able to download patches from other users.

---
#### Let's remember how the synthesizer works
![[Pasted image 20230930150259.png]]

<center>The scheme of operation of a simple synthesizer</center>

![[Pasted image 20230928112417.png]]
<center>The scheme of operation of a simple synthesizer with a filter</center>

![[Pasted image 20230928112758.png]]

---
#### Getting to know Reactor 6
- Panel View / Structure View
- Clicking on the PCM opens the Build-in Modules
- Panel menu - Adds visual controls
- Midi-in/Out - synthesizer communication controllers via midi
- Oscillators - the main blocks of sound generators

1. Built-in Module / Embedded Module
2. Library/Library - Library of ready patches
4. Searchbox - search for blocks and patches
 ![[Pasted image 20230928113242.png]]
>[!info] 
>All the functions of **Reactor 6** can be found in more detail at this [link](https://www.native-instruments.com/fileadmin/ni_media/downloads/manuals/REAKTOR_6_Getting_Started_English_0419.pdf)

---
#### Impact Synthesizer circuitry on the Reactor 6 platform

![](H1.png)
1. Oscillator generating a sine wave
- **P** - Pitch - pitch control input. Accepts MIDI values
- **A** - Amplitude - volume control input 
- **Out** - Signal output
2. **Freq** - pitch controller. The default value is 127, which corresponds to the full-format layout of the midi keyboard. For convenience, we will set from 20 to 20000 in the Function panel, which will correspond to the standard frequency range. 
3. **Log.(F)** - Logarithm for converting linear frequency values in Hz to logarithmic patch values in semitones
4. **Multiply** - multiplier for multiple signal
5. **Mult** - controller in which we set the range of values for multiplication
6. **Switch** - enables and disables the signal
7. **In** - input 
8. **Out** - signal output

![](Синтезатор%20импактов_Схема.png)

9. **Gate** - Source for MIDI Note on and Note Off events, switching the status of a gate output signal. The amplitude is controlled by the On velocity
10. **Envelope** modulator (Attack, Hold, Decay, Sustain, Release)
11. **Macro** - the object is a folder in which the circuitry of the oscillator 1 (H1) is nested
12. **Add** - adder for multiple signal
13. **Distortion**
14. **Add**
15. **Filter**
16. **Master Volume**
17. **Output**