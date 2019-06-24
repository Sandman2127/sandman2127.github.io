---
layout: page-fullwidth
title:  "Tesla Coil"
categories:
    - design
header:
   image_fullwidth: TC_Background.jpg
---
<h2><em>So you built a tesla coil...</em><strong>Why would anyone do that for fun???</strong></h2>
<p>The idea of the Tesla coil came from its inventor <a href="https://en.wikipedia.org/wiki/Nikola_Tesla">Nikola Tesla</a>. A visionary genius, Nikola Tesla revolutionized humanities ability to harness electrical power, and in the end his Alternating Current (AC) won out in the <strong>War Of Currents</strong> against Thomas Edison. Along the way he designed several incredible electrical devices including: the AC transformer (transforms AC voltages to higher or lower levels), the AC induction motor, a steam powered electricity generator (He lit up the Chicago worlds fair in 1893 for the first time ever) and the incredible but highly inefficient Tesla Coil. The idea of the Tesla Coil was to transmit power directly the people. Thats right, through the air without the need for wires. We now know that he was obviously unsuccessful, but his idea is an incredible source of inspiration, and furthermore he didn't completely fail. Actually the Tesla coil does work, but it its highly inefficient because of the inverse square law that all EM waves including the ones his coil produced simply must follow. Transmitting power for our daily uses is simply to inefficient, not to mention dangerous (imagine people with pacemakers...)</p>

<h3><strong>My Personal Tesla Coil Journey</strong></h3>
<p>I'm a very patient person, but I almost gave up on this one... Let me tell you the story of my attempt to get this working alongside finishing my Ph.D.</p>
<p>When I first began graduate study I came to the realization that I was not only fascinated by my own field of study (Microbiology & Genetics), but also the realm of physics, specifically the electromagnetic force and the magic that comes with understanding it. Although I realized early on that I would likely never be on the level of understanding of Physics as I am with my own field, I began to dabble in electronics. It started simply enough with my own attempts to control direct electrical current (DC) via resistors and transistors, needless to say many were sacraficed such that I could understand even the most basic principles (i.e. Ohms Law V=IR). As I became more adept, I realized I needed a project. <em>A real project, something worth doing, that would require me to truely understand the nature of electricity</em>.</p>
<p><strong>I picked the Tesla Coil and my god was it difficult... However, some of the reason I picked this project is because I knew it would be hard </strong>. I knew that building a Telsa Coil would put me one step closer to being the modern day electrical wizard I wanted to be. Never before had I struggled so hard to understand things that seemed to come easily to everyone else. It is safe to say, that building a functional tesla coil (i.e. one that does not immediately destroy its components) requires at least an intermediate level of mastry in the realm of electrical control. This is not to discourage newbies from trying, just realize what your getting into, you may put > $700 into this before seeing anything happen. Furthermore, the process involves understanding the principles of Alternating Current, transformers, RLC circuits, Impedance (the evil twin AC equivalent of DC resistance), and how electrical circuits evolve through time. As I said, at the moment of ordering the first parts I just didn't quite understand the gravity of the journey I just embarked upon. <strong>I am so happy I did it</strong>.</p>  
<p>I will only demonstrate the basics as: 1st. I'm barely qualified to :) and 2nd. tons of resources exist on how to make a functional Tesla Coil. I will demonstrate the basic principles of a Tesla Coil and show you one of the only times I've ever almost given up on a project, and why I am sooooo happy I did not quit.</p>
<h3><strong>Tesla Coil Basics</strong></h3>
<p> A tesla coil is a losely coupled high frequency and voltage AC transformer that emits electrical energy as radio waves. It has two circuits, the primary and the secondary. The primary controls the power input to the secondary via a balance of charging and discharging a high voltage capacitor (7 nF, >50kV breakdown resistance) across a spark gap and into a low impedance wire inductor (~100uH). If improperly controlled via safety gaps and bleeder resistors the primary circuit will rip itself apart within moments of normal operation. The primary capacitor is charged via a step up AC transformer that at least in my case takes line 120V AC and increases its voltage to 15kV AC. After the primary capacitor is charged fully the primary spark gap between the capacitor and the low impedance coil arcs across effectively turning an open circuit into a current flowing RLC circuit. At this point the transformer that supplied the energy is out of the game (as it only operates at 60 Hz) and the electrons slosh back and forth in the inductor at a very high frequency (<em>more on this later</em>). This sloshing,<strong>if properly tuned</strong>, induces a very high voltage in the secondary RF coil (inductor). The primary inductor coil on a homemade low power coil (< 1000 watts like mine) traditionally has between 5 to 20 coils of wire and the secondary inductor coil has anywhere from 700 to 1000's of turns of higher guage wire. When energy is transfered between the two, a massive voltage rise occurs in the secondary. This voltage rise is the reason for the electromagnetic wave emission and the pretty streamer arcs (caused by ionization of nearby gases) I was so excited to see.</p>  

<h3><strong>How I actually did it</strong></h3>

<h3><strong>Where I nearly fell short</strong></h3>


<div class="row">
    <div class="large-6 columns">
    <img src="{{ site.urlimg }}TC_inductance_by_resistance.jpg" alt="">
    </div>
    <div class="large-6 columns">
    <img src="{{ site.urlimg }}TC_resonant_freq.jpg" alt="">
    </div>
</div>  


<br>
<h3><strong>The Glorious First Light</strong></h3>
<div>
<video width="1000" controls>
    <source src="/images/TC_description.mp4" type="video/mp4">
    <source src="movie.ogg" type="video/ogg">
    Your browser does not support the video tag.
</video>
</div>

<h3><strong>Finally, it works...it works!!!!!</strong></h3>
<div class="row">
    <div class="large-12 columns">
    <img src="{{ site.urlimg }}TC_full_bubbleshot2.jpg" alt="">
    </div>
</div>

<h3><strong>Tuning and Improved Streamer images</strong></h3>
<div>
<video width="1000" controls>
    <source src="/images/TC_test2.mp4" type="video/mp4">
    <source src="movie.ogg" type="video/ogg">
    Your browser does not support the video tag.
</video>
</div>


<h3><strong>Plasma emission without nearby conductor</strong></h3>
<div class="row">
    <div class="large-12 columns">
    <img src="{{ site.urlimg }}TC_Plasma_emission.jpg" alt="">
    </div>
</div>



<!--TC_Background.jpg               TC_Plasma_emission.jpg          TC_full_bubbleshot.jpg          TC_inductance_by_resistance.jpg TC_resonant_freq.jpg                    



https://online-video-cutter.com    for video cutting-->
