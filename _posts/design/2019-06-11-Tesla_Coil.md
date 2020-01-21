---
layout: page-fullwidth
title:  "Tesla Coil"
categories:
    - design
header:
   image_fullwidth: TC_Background.jpg
---
<div class="row">
    <div class="column.large-centered">
    <img src="{{ site.urlimg }}TC_full_bubbleshot2.jpg" alt="">
    </div>
</div>
<h2><em>So you built a tesla coil...</em><strong>Why would anyone do that for fun???</strong></h2>
<p>The idea of the Tesla coil came from its inventor <a href="https://en.wikipedia.org/wiki/Nikola_Tesla">Nikola Tesla</a>. A visionary genius, Nikola Tesla revolutionized humanities ability to harness electrical power, and in the end his Alternating Current (AC) won out in the <strong>War Of Currents</strong> against Thomas Edison. Along the way he designed several incredible electrical devices including: the AC transformer (transforms AC voltages to higher or lower levels), the AC induction motor, a steam powered electricity generator (He lit up the Chicago worlds fair in 1893 for the first time ever) and the incredible but highly inefficient Tesla Coil. The idea of the Tesla Coil was to transmit power directly the people. Thats right, through the air without the need for wires. We now know that he was obviously unsuccessful, but his idea is an incredible source of inspiration, and furthermore he didn't completely fail. Actually the Tesla coil does work, but it its highly inefficient because of the inverse square law that all EM waves including the ones his coil produced simply must follow. Transmitting power for our daily uses is simply to inefficient, not to mention dangerous (imagine people with pacemakers...)</p>

<h3><strong>Learning Electronics, Tesla Coil Journey</strong></h3>
<p>I'm a very patient person, but I almost gave up on this one... Let me tell you the story of my attempt to get this working alongside finishing my Ph.D.</p>
<p>When I first began graduate study I came to the realization that I was not only fascinated by my own field of study (Microbiology & Genetics), but also the realm of physics, specifically the electromagnetic force and the magic that comes with understanding it. Although I realized early on that I would likely never be on the level of understanding of Physics as I am with my own field, I began to dabble in electronics. It started simply enough with my own attempts to control direct electrical current (DC) via resistors and transistors, needless to say many were sacraficed such that I could understand even the most basic principles (i.e. Ohms Law V=IR). As I became more adept, I realized I needed a project. <em>A real project, something worth doing, that would require me to truely understand the nature of electricity</em>. So I figured, why not learn from the very best, Tesla himself.</p>
<p><strong>My god was it difficult...</strong> However, some of the reason I picked this project is because I knew it would be hard. I knew that building a Telsa Coil would put me one step closer to being the modern day electrical wizard I wanted to be. Never before had I struggled so hard to understand things that seemed to come easily to everyone else. It is safe to say, that building a functional tesla coil (i.e. one that does not immediately destroy its components) requires at least an intermediate level of mastry in the realm of electrical control. This is not to discourage newbies from trying, just realize what your getting into, the inherent danger of high voltage AC and that you may put > $700 into this before seeing anything happen. Furthermore, the process involves understanding the principles of Alternating Current, Transformers, RLC circuits, Impedance (the evil twin AC equivalent of DC resistance), and how electrical circuits evolve through time. As I said, at the moment of ordering the first parts I just didn't quite understand the gravity of the journey I just embarked upon. <strong>I am so happy I did it, I wouldn't trade my coil and what I learned from it for anything</strong>.</p>  
<p>Below I will only demonstrate the basics as: 1st. I'm barely qualified to :) and 2nd tons of resources exist on how to make a functional Tesla Coil. I will demonstrate the basic principles of a traditional (non-solid state) Tesla Coil and show you one of the only times I've ever almost given up on a project, and why I am sooooo happy I didn't.</p>
<h3><strong>Tesla Coil Basics</strong></h3>
<div class="row">
    <div class="column.large-centered">
    <img src="{{ site.urlimg }}TC_diagram.png" alt="">
    </div>
</div>
<p> A tesla coil is a loosely coupled high frequency and voltage AC transformer that emits electrical energy as radio waves. It has two circuits, the primary and the secondary. The primary controls the power input to the secondary via a balance of charging and discharging a high voltage capacitor (7 nF, >50kV breakdown resistance) across a spark gap and into a low impedance wire inductor (~100uH). If improperly controlled via safety gaps and bleeder resistors the primary circuit will rip itself apart within moments of normal operation. The primary capacitor is charged via a step up AC transformer that at least in my case takes line 120V AC and increases its voltage to 15kV AC. After the primary capacitor is charged fully the primary spark gap between the capacitor and the low impedance coil arcs across effectively turning an open circuit into a current flowing RLC circuit. At this point the transformer that supplied the energy is out of the game (as it only operates at 60 Hz) and the electrons slosh back and forth in the inductor at a very high frequency (<em>more on this later</em>). This sloshing,<strong>if properly tuned</strong>, induces a very high voltage in the secondary RF coil (inductor). The primary inductor coil on a homemade low power coil (< 1000 watts like mine) traditionally has between 5 to 20 coils of wire and the secondary inductor coil has anywhere from 700 to 1000's of turns of higher guage wire. When energy is transfered between the two, a massive voltage rise occurs in the secondary. This voltage rise is the reason for the electromagnetic wave emission and the pretty streamer arcs that come off of the torus (caused by ionization of nearby gases).</p>  

<h3><strong>How I actually did it:</strong></h3>
<p>I began as I do with many of my projects, I did a ton of research, constantly questioned my understanding of the basics and why I was doing this and eventually I drew up my first tesla coil schematic. </p>
<div class="row">
    <div class="column.large-centered">
    <img src="{{ site.urlimg }}TC_design_1.jpg" alt="">
    </div>
</div>
<p>It wasn't great, in fact looking back at it now, it is not even a good schematic :). Many component values and build parameters are simply missing or unclear. But if I've learned anything about completing electronics projects, it is that <strong>you have to start somewhere</strong>. Many great resources were used in the production of my tesla coil you can find them below:</p>
<ol>
<li><a href="http://www.teslacoildesign.com/docs/TheTeslaCoil-Gerekos.pdf">Christopher Gerekos undergraduate thesis</a> which describes the building of every component of his very own Zeus Tesla Coil </li>
<li><a href="http://www.hvtesla.com/terry.html"> HV tesla</a>: an exellent resource for anyone looking to appropriately build a TC </li>
<li><a href="http://www.kronjaeger.com/hv/index.html">Jochen Kronjager's High Voltage Page</a> probably saved my life a few times with safety tips on how to handle high voltage AC electricity. </li>
<li><a href="http://www.teslacoildesign.com">Kevin Wilson's Tesla Coil Design page</a> </li>
<li><a href="https://www.teslamap.com">Tesla Map Program</a> to assist in design parameters </li>
</ol>

<p> I mentioned above that many things are missing from that original schematic. <strong>What did I mean by that?</strong> Looking back I can see that several important pieces of data had yet to be filled in. The reason is two fold: 1st At the time of drawing this I didn't exactly know what component values would pair well, 2nd Cost. You always have to optimize for what you can afford, however in my case <strong>cost</strong> almost indirectly lead to me failure with this project.</p>

<p> The details that are missing include the electrical values and the corresponding geometry of the following parts:</p>
<ul>
<li>Primary Coil: Width, Length, Gauge, and  (i.e. geometry) and coil turns, which dictates inductance</li>
<li>Toroid: Geometry dictates frequency response of the secondary circuit</li>
<li>Seconday Coil: Geometry and total turns, final inductance</li>
<li>Tesla Coil Ground: Composition...<strong>IT CANNOT BE YOUR HOUSE GROUND!!!</strong></li>
<li>Input Transformer: Input & Output Voltage, Maximum Output Wattage</li>
<li>Primary Capacitor: Capacitance (nanoFarads), Voltage Maximum</li>
<li>Primary Spark Gap: Composition, distance between terminals</li>
<li>Security Spark Gaps: Composition, distance between terminals</li>
<li>Power Factor Correction (PFC) Capacitor: Capacitance</li> 
</ul>
<h3><strong>Component Builds and Buys:</strong></h3>
<h5><em>The NST-Transformer:</em></h5>
<p> I started with the transformer which will determine how much power your coil will be able to instantaneously output. It also determines what your primary capacitor size should be. For further information I recommend <a href="http://www.teslacoildesign.com">Kevin Wilson's Tesla Coil Design page</a>. I ended up ordering a 15,000 volt NST Franceformer which can output a maximum of 30 ma in a dead short. This ends up being ~450 watts max output.</p> 

<h5><em>The Primary Capacitor:</em></h5>
<p>To ensure your primary capacitor is up to the challenge of charging and discharding at 15KV, tesla coilers recommend generating a capacitor with between 1.5-2X the voltage rating. Additionally we must correct for the fact that the voltage is AC. If we multiply 15000*1.414 we get the peak voltage (21KV). The final consideration is that your capacitor must <a href="http://www.teslacoildesign.com/design.html#design_primarycap"><strong>NOT</strong> be resonant with the secondary coil of your transformer </a>. For safety, I built my capacitor to withstand voltage spikes up to 50KV and its final capacitance was measured at 7nF. I also added 10 MOhm bleeder resistors between each series capacitor. The goal of these is to bleed off the dangerous high voltage between TC runs. The final capacitance I measured (7nF) was a little closer than I'd like to be to the resonant capacitor with my secondary, but I don't always get what I want, especially on a budget :).</p>
<h5><em>The Secondary Coil:</em></h5>
<p>Next, I wound the secondary coil. I recommend starting a TV series, because this is gona take a while, especially if you do it by hand. I chose 26 gauge coated magnet wire, due to is ampacity and heat ratings and I picked a 3" piece of PVC and started wrapping coil after coil. Some 900 coils and 2 weeks later, I cut the final wire, removed the coating from the ends. My amplifier was near complete</p>
<h5><em>The Terry Filter:</em></h5>
<p>I also spent much time and effort in the winter of 2017 completing a Terry Filter, better documented <a href="http://www.hvtesla.com/terry.html"> here</a>.</p>

<h3><strong>Where I nearly fell short...</strong></h3>
<h5><em>What happened?</em></h5>
<p><strong>I jumped the gun...</strong> I had a tested working NST-transformer, a 50 KV capacitor and a secondary coil. What else was left, I thought... All you need to do is slap a primary coil on this sucker, craft a torus, tune it all and you'll have a working tesla coil in no time. So thats exactly what I did. I assembled 4-5 turns of 6 gauge solid copper wire around my secondary coil, due to the high cost of the wire. I hastily fashioned a torus made of from aluminum ducting and two pie tins and assembled all the components onto a painted plywood mount. I tossed on my terry coil, turned my auto-transformer to a low setting and looked for the first light. The primary gap lit brilliantly bright and was much louder than I thought it would be. The neighbors aren't gona like this :)... However, upon closer inspection, it seemed nothing was coming off the Torus, no sparks, nothing... To my dismay, no amount of cranking on the auto-transformer or tuning could fix it. My coil was DOA, and their wasn't a soul around who could tell me what to do to fix it.</p>

<h5><strong><em>I was in the process of being taught a very valuable lesson:</em></strong></h5>
<p><em>The bottom line was: all electronic devices follow the laws of physics, and as such, if you desire the ones you build to work, then you must understand the rules that govern their operation</em>... Those rules are written in the very fabric of nature and can often be adequately described by mathematical equations. If you refuse to do the math, <strong>GO FURTHER, YOU SHALL NOT...</strong></p>

<p>Up to this point in my electronics exploration, I was simply following what other people told me to do, because when it worked, it felt absolutely magical... <strong>Never before had I faced such a complex problem, and WORSE I had no idea what was wrong or even how to figure out what was wrong </strong>. Why wouldn't my tesla coil do the cool sparky thingy everyone else's did. I was doomed ... It was another 18 months until I had accrued enough knowledge, courage and capital to retry the project...</p>

<h5><strong> Two years later I came back at this project like a 4-ton Saber-Toothed-Moose-Lion protecting is cub</strong></h5>
<p>I had decided that winter, that I could no longer be humiliated by my own ignorance.<strong> I had to know what was wrong and I had to fix it!</strong> In hindsight, <strong>trying this project one more time was unquestionably one of the best decisons I've ever made </strong>. I set about pouring over the websites described above where I found loads of descriptions of the frequencies of operation of the primary and secondary circuit and the parameters of the coils and capacitors involved. They generally matched my own parameters, but I had never bothered to measure the primary and secondary coil inductance. Measuring inductance is difficult if you don't have an LCR meter and many forum users had implied it wasn't important and you could simply tune your way out of understanding it. I now had a target. Could I measure and calculate my way out of this problem ?</p>

<div class="row">
    <div class="large-6 columns">
    <img src="{{ site.urlimg }}TC_inductance_by_resistance.jpg" alt="">
    </div>
    <div class="large-6 columns">
    <img src="{{ site.urlimg }}TC_resonant_freq.jpg" alt="">
    </div>
</div> 

<p>The answer is, Yes!!! Measuring and calculating all variables is the only way out of an electronics problem I know and it almost always works the first time. You must be: adequately patient, knowledgable and have the appropriate equipment. Above I discovered that my hastily crafted primary coil had waaaaaaay to low of inductance, to properly transfer the energy of the primary circuit into the secondary. This meant it was impossible to tune the primary to the proper frequency... I simply didn't have enough expensive 6 gauge copper wire on the intial coil. I bought more, retapped the primary coil at the appropriate length and the results are below!</p>

<h3><strong>The Glorious First Light</strong></h3>
<div>
<video width="1000" controls>
    <source src="/images/TC_description.mp4" type="video/mp4">
    <source src="movie.ogg" type="video/ogg">
    Your browser does not support the video tag.
</video>
</div>


<h3><strong>Finally, it works...it works!!!!!</strong></h3>
<h5><strong>Tuning and Improved Streamer images</strong></h5>
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
