---
layout: page-fullwidth
title:  "A computer... from scratch?"
categories:
    - design
header:
   image_fullwidth: cpufull.jpg
---
<h3>Inspiration</h3>
<p> Why do this in the first place? When I first looked at <a href="https://eater.net/8bit/"> Ben Eaters plans to make a computer on a breadboard</a> I was instantly hooked. I decided then and there, if it could be done, I would do it. In the <a href="/design/Tesla_Coil">tesla coil project</a>, I learned the hard way that reading about the principles of electronics and building functional electronics require entirely different levels of understanding. For quite some time I have been enthralled by the idea of unvieling the mysteries of the mysterious and powerful electromagnetic forces that permeate our everyday lives. Additionally, I was hoping this might be that one project that put me over the top, the one project that transformed me to a definable electrical wizard. Turns out, I was right, after you build a computer from scratch you move to the next level and then you jump 8 more. The rules of physics are the only bounds that exist.</p>
<h3><strong>What is a computer, really?</strong></h3>
A digital computer is an information processing device. On a basic level, a digital computer uses many arrays of transistors set into specific configurations (gates) to control and store voltage differences. It is these voltage differences (highs and lows, 1's and 0's ...) that when properly processed and interpreted provide all the magic of a modern computing experience.
<h4>Logic Gates and Universal Gates</h4>
If the most basic unit of a digital computer is a semiconductor transistor, then the next level up is a logic gate.
<div class="row">
    <div class="column.large-centered">
    <img src="{{ site.urlimg }}LogicGates0.png" alt="">
    </div>
</div>
Logic gates allow the processing of information in the form of voltage differences using boolean logic. For each gate the voltage potential at the input(s) dictate the output voltage as according to the truth table for that gate. My favorite gates are the <strong>Universal NOR and NAND gates</strong>. 
<div class="row">
    <div class="column.large-centered">
    <img src="{{ site.urlimg }}NOR.png" alt="">
    </div>
</div>
<div class="row">
    <div class="column.large-centered">
    <img src="{{ site.urlimg }}NAND.png" alt="">
    </div>
</div>
They are universal because these gates can be chained together in various ways to build any other gate. These two logic gates are thus <strong>completely self sufficient</strong> in their ability execute any mathematical logic that exists.

<h4>Storage of Information</h4>
One of the most natural extensions of logic gates is the ability to store information as the presence or absence of a voltage potential. In this case a 0 volt potential represents a boolean 0 and a high voltage potential (i.e. > 4.5 volts) represents a boolean 1. A single digital output is called a bit. One of the simplest forms of storing a bit is in the flipflop circuit.
<div class="row">
    <div class="column.large-centered">
    <img src="{{ site.urlimg }}FlipFlop.png" alt="">
    </div>
</div>

<!-- <p><strong>Boolean mathematics</strong></p>
<p></p> -->


<h3><strong>An 8 Bit Breadboard Computer</strong></h3>
<h4>Building in stages</h4>
When attacking a big problem I always appreciate following the reductionist mindset. Generally, the simple thought of building a computer from wires and IC's sounds completely mental. However if we break the problem of a computer into parts, i.e. sets of simpler problems, solve all those, and integrate them together, building a computer is no harder than building anything else. I'm just lucky I had the experience and resources to do it.
<h4>The Long Term Memory of an 8 bit computer</h4>

<h4>The Short Term Memory of an 8 bit computer</h4>

<h4>The Heart of an 8 bit computer</h4>

<h4>The Brain of an 8 bit computer</h4>

<h4>Doing Math with 0's and 1's</h4>

<h3>Bringing it all together</h3>


<h3><strong>From humble beginnings</strong></h3>
<div class="row">
    <div class="column.large-centered">
    <img src="{{ site.urlimg }}cpustage2.jpg" alt="">
    </div>
</div>
<h3><strong>Programming flash memory</strong></h3>
<div class="row">
    <div class="column.large-centered">
    <img src="{{ site.urlimg }}cpuprog1.jpg" alt="">
    </div>
</div>

<h3><strong>Microcode programming</strong></h3>
<video width="1000" height="800" controls>
  <source src="/images/eepromprogammer.mp4" type="video/mp4">
<source src="movie.ogg" type="video/ogg">
Your browser does not support the video tag.
</video>


<h3><strong>Runtime</strong></h3>
<!-- <div class="row">
    <div class="column.large-centered">
    <img src="{{ site.urlimg }}" alt="">
    </div>
</div> -->

<h3><strong>Simple Operations</strong></h3>
<!-- <video width="1000" height="800" controls>
  <source src="/images/eepromprogammer.mp4" type="video/mp4">
<source src="movie.ogg" type="video/ogg">
Your browser does not support the video tag.
</video> -->