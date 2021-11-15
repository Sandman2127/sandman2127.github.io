---
layout: page-fullwidth
title:  "A Universal DC adapter"
categories:
    - design
header:
   image_fullwidth: psuWaveBackground.png
---
<h2>A Brief History of Power Distribution using Alternating Current (AC) vs Direct Current (DC)</h2>
<p>Alternating Current alternates lol... and Direct Current remains constant at a constant voltage. In the United States alternating current leads to electrons sloshing back over a miniscule distance opposing directions exactly 60 x per second (Hz). That seems academically interesting, but not very useful... Right? The AC form of electricity is unanimously used for power distribution across the earth. But why??? It makes little sense to those of us who are first starting electronics why this decision was made. Many, if not most electronics we use on a daily basis operate on DC at some level. Why not just use DC to start with? The reason for this is historical in nature, in the beginnings of world electrification a great battle known as the <a href="https://www.energy.gov/articles/war-currents-ac-vs-dc-power">War of the Currents</a> ensued between the two top minds of the electrical world (<a href="https://en.wikipedia.org/wiki/Nikola_Tesla">Nikola Tesla</a> & <a href="https://en.wikipedia.org/wiki/Thomas_Edison">Thomas Edison</a>). In the end the battle was decidedly won by economic factors. The victory lap showing the obvious winner was Nikola Tesla's first massive display of the electrification in the <a href="https://en.wikipedia.org/wiki/World%27s_Columbian_Exposition">1893 Chicago World's Fair</a>. The polyphase system displayed wowed the world with a display of artificial light brighter than had ever been seen by human eyes. It was enabled by Tesla's induction motor and the newly created AC power transformer. To this day improved versions of those inventions allow smaller wires to carry more power during distribution than DC systems every could. The means is simple, modern power plants use steam turned inductions motors to generate AC and voltage step up transformers to convert low voltage high energy currents --> to high voltage low current. Using high voltage means we can pass more current with less heating of the wires. Thus, a worldwide grid of electrical energy was born. The creation of this grid forced electrons to live busy and confusing lives using their potential energy to do the bidding of a recently woken consciousness.</p>

<h2>Power Supply Types</h2>
<p>The goal of the powersupply we are producing is to convert AC --> DC, yep like the band...</p>
<h3>An Unregulated Power Supply</h3>
<div class="row">
    <div class="column.large-centered">
    <img src="{{ site.urlimg }}psuUnreg.jpg" alt="">
    </div>
</div>
<p>image credit: https://www.elprocus.com/</p>
<p>An unregulated power supply uses a transformer to step down wall voltage (120v @ 60 Hz) to a lower voltage (12v @ 60 Hz). The step down transformer output is fed to system of rectifier diodes that recitify both sides of the AC waveform to a bouncing positive (+) wave. The diodes achieve this by acting as one way valves for current flow, i.e. once current has passed a diode, it cannot return through the same path. Finally, a thick sufficient voltage electrolytic capacitor is used to smooth the bouncing wave to a near Direct Current output DC. Unregulated supplies are unable to smoothly regulate the voltage at the outputs. For simple cases they are acceptable, but anything requiring more precise voltage regulation should avoid them.</p>

<h3>A Linear Regulated Power Supply</h3>
<p></p>
<div class="row">
    <div class="column.large-centered">
    <img src="{{ site.urlimg }}psuRegLin.jpg" alt="">
    </div>
</div>
<p>image credit: https://www.elprocus.com/</p>
<p>In a regulated power supply the majority of the above description still applies. One major difference occurs once that the current reaches the regulator IC. The IC uses internal circuitry to vary the input current at whatever level is necessary to maintain the output voltage set by the user. Modern day regulator IC's can reject >75 Db of signal ripple, producing an extremely stable output voltage at the cost of outputting heat at a rate equivalent to the voltage drop across them. 

<h4>Regulator output examples:</h4>
<p>If 12V is applied the leads of the regulator and it is required to maintain a voltage at 6V while flowing 3A through a resistive load. According to <a href="https://en.wikipedia.org/wiki/Ohm%27s_law">Ohm's Law</a> (P=IV) the load will dissipate 18 watts. However, we must not forget about the potential difference still in the circuit. Since we started with 12V - 6V (load) we still have 6V across the regulator. Since the load is pulling 3A that means the same 3A current must flow through the IC and this is where trouble begins. Thus, 3A * 6V = 18 watts. While the load may be able to handle 18 watts that is quite a lot of heat for a non-heatsinked regulator to dissipate. See the real world results of similar mistake below:</p>
<div class="row">
    <div class="column.large-centered">
    <img src="{{ site.urlimg }}psuLinRegOops.jpg" alt="">
    </div>
</div>
<p>The left is the remainder of a linear regulator IC designed to handle 5A @ 24V. As I discovered that rating means little when you dead short it. Needless to say, protection from such a mistake is something you realize you need in hindsight.</p>
<h2>A Dual Rail Linear Power Supply with Short Circuit Protection</h2>
<div class="row">
    <div class="column.large-centered">
    <img src="{{ site.urlimg }}psuFullOpAmpCircuitRun.jpg" alt="">
    </div>
</div>
<h2>Custom Built Overcurrent Protection Circuit</h2>
<div class="row">
    <div class="column.large-centered">
    <img src="{{ site.urlimg }}psuEverycirc.png" alt="">
    </div>
</div>
<p><a href="https://everycircuit.com/circuit/6734605162643456/overcurrent-short-circuit-protection-circuit">EveryCircuit Simulation of this custom circuit</a></p>
<h3>Description of Operation</h3>
<p>This is a functional overcurrent protection circuit. It measures the voltage drop across the 220 mOhm resistor on the far left supply. That voltage is boosted and compared against a reference voltage in the second opamp (comparator mode) and an SR latch is used to latch the overcurrent result.</p> 
<p>If the output of the first opamp is lower than the inverting input (-) voltage the output of the second opamp is low, otherwise the output goes high.</p>  
<p>The output of the second opamp is fed to an SR latch (2 NOR gates). When the opamp output and the reset switch are low the output Q is low and the relay is off (i.e. the circuit operates normally).</p> 
<p>When the opamp goes high (due to sensing an overcurrent event across the 0.22 ohm resistor) Q latches, the red LED turns on and the circuit deactivates nearly instantly protecting your supply.  You can simulate overcurrent by reducing the 8 ohm resistor resistance.</p> 
<p>To reset the system properly, flip the switch to high and back to low. This resets the latch (and green LED protected indicator). Note the circuit will only continue operating again when you increase resistance of the primary load (>= 8 ohm). </p>

<h3>Power supply in shutdown state (red led active)</h3>
<div class="row">
    <div class="column.large-centered">
    <img src="{{ site.urlimg }}psuKillCircuit.jpg" alt="">
    </div>
</div>
<p>My system is hardwired to allow no more than 2A @ 16VDC. If the resistance of load drops below a threshold that higher than 2A <em>would flow</em> the protection circuit activates and immediately shuts off the supply. It can only be reactivated through the reset switch.</p>

<h3>Power supply in active passing current state (blue led active)</h3>
<div class="row">
    <div class="column.large-centered">
    <img src="{{ site.urlimg }}psuBoxOpen.jpg" alt="">
    </div>
</div>

<h2>Enough nonsense, what can you use it for?</h2>
<p>We have just built the universal DC adapter :). Anything that runs on voltages below 16V and requires < 2A current can be powered by this circuit. This includes: computers, motors, arduinos, fans, whatever you can come up with that takes DC electricity. The inherent safety added by the protection circuit makes this a perfect power system for testing parts and fixing other electrical systems.</p>

<h2>Why build the supply with +/- rails?</h2>
<h3>Operational Amplifiers (opamps)</h3>
<p>Having a supply with + & - voltage rail allows the user to amplify analog signals like music or sensor data with massive signal gain. One way to do this is to use an opamp.</p>
<div class="row">
    <div class="column.large-centered">
    <img src="{{ site.urlimg }}psuOpAmpNonInv_InvConfig.png" alt="">
    </div>
</div>
<p><a href="https://everycircuit.com/circuit/6586919818625024">View this non-inverting and inverting op-amp simulation</a>. Using the circuit configuration shown allows both amplification and inversion of any analog input signal within that opamps range. <strong>The results in real life are nothing short of astounding...</strong></p>
<h4>100x signal gain using using a non-inverting amplifier w/negative feedback</h4>
<div class="row">
    <div class="column.large-centered">
    <img src="{{ site.urlimg }}psuinputAmplified.jpg" alt="">
    </div>
</div>
<p style="color:red;">Input Signal (20 mVpp)</p>
<p style="color:gold;">NonInverted Output Signal (1.8 Vpp)</p>
<p>Using the linear power supply with +/- 10V rails fed to the opamp we can amplify the sine wave (20 mVpp) input to nearly 2 Vpp (~100x gain) with near perfect accuracy using a <a href="https://www.futurlec.com/Motorola/MC33174.shtml">Motorolla MC33174</a>. In order to amplify the signal without clipping the waveform, the range of the rails must be larger than the highest amplified output on both edges. In this case, we were aiming for 100x amplification and nearly achieved it.</p>
<h4>Waveform Inversion & 100x signal gain using an inverting amplifier</h4>
<div class="row">
    <div class="column.large-centered">
    <img src="{{ site.urlimg }}psuinputAmplifiedReversed.jpg" alt="">
    </div>
</div>
<p style="color:red;">NonInverted Output Signal (1.8 Vpp)</p>
<p style="color:gold;">Inverted Output Signal (1.8 Vpp)</p>

<h4>Amplifying live audio from <a href="https://www.youtube.com/watch?v=Vsy1URDYK88">Language</a> by: Porter Robinson</h4>
<div>
<video width="800">
    <source src="/images/psuLanguageAliveFullH264.mov">
</video>
</div>
<p style="color:red;">Audio Input Signal (100 mVpp scale)</p>
<p style="color:gold;">Voltage Amplified Output Signal (1 Vpp scale)</p>