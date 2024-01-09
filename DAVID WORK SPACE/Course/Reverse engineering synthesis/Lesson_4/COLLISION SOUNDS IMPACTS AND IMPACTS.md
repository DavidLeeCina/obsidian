# COLLISION SOUNDS: IMPACTS AND STEPS

#### What is a collision?

**Collision** - This is a game event in which two or more objects collide with each other. 
![](Demo_Collision.png)
#### Collision Studies
Why do we need procedural collisions? - To simulate physical modeling.

What is a generative syste, and what is a procedural system?

![](Pasted%20image%2020231223103324.png)
In a game engine, collision occurs according to some laws.

##### GENERATIVE COLLISION SYSTEMS
In most games, the collision system is built on a generative system consisting of ready-made sound files. It looks something like this: 

[Simple Generative Blast System](obsidian://open?vault=DAVID%20WORK%20SPACE&file=Course%2FReverse%20engineering%20synthesis%2FLesson_4%2F%D0%9F%D1%80%D0%BE%D1%81%D1%82%D0%B0%D1%8F%20%D0%B3%D0%B5%D0%BD%D0%B5%D1%80%D0%B0%D1%82%D0%B8%D0%B2%D0%BD%D0%B0%D1%8F%20%D1%81%D0%B8%D1%81%D1%82%D0%B5%D0%BC%D0%B0%20%D0%B2%D0%B7%D1%80%D1%8B%D0%B2%D0%BE%D0%B2.canvas)

![](Простая%20генеративная%20система%20взрывов.png)
For each object in the game that has the ability to destruct, parameters are entered, such as: the size of the object, what materials it contains (metal, glass, wood, and so on). Then, during a collision, these parameters are transferred to the game using RTPC, where the content for the game event (explosion) is generated. An RTPC can be present on the common bus, which acts as an ADSR and shapes the length of the sound. 

Examples of games with a complex generative collision system:

**Battlefield**
<iframe width="560" height="315" src="https://www.youtube.com/embed/cFacOVBwWZI?si=9cH10BE-sMcJP7W1&amp;start=75" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

**Teardown**
<iframe width="560" height="315" src="https://www.youtube.com/embed/ZTUMHoWJPvM?si=l2MMOs9mIL1oWkAq&amp;start=114" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>


### COLLISION INVESTIGATION BY **MICROSOFT**

[PDF](https://www.microsoft.com/en-us/research/wp-content/uploads/2016/10/5.pdf)
<iframe width="560" height="315" src="https://www.youtube.com/embed/Qafl_LGLDKg?si=DGJnqVamLihgcfnj" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>



**Inference:**
- Collision sound is the sum of tonal resonance and noise
	![| 500](Pasted%20image%2020231007184914.png)

- The live signal attenuates non-linearly, but chaotically exponentially
	![| 500](Amplitude%20Envelop.png)

- By randomizing the volume of harmonics, it is possible to achieve realistic randomization of collision sounds 
	 ![| 652](Pasted%20image%2020231007185239.png)

- By randomizing the filter parameters, you can get a variety of sound
	![650](Pasted%20image%2020231007185422.png)
