---
layout: page-fullwidth
title:  "A Universal DC adapter"
categories:
    - design
header:
   image_fullwidth: psufull.jpg
---
<h2>Converting Alternating Current (AC) into Direct Current (DC)</h2>
<p>Alternating Current</p>
<p>Across the earth the AC form of electricity is almost unanimously used for power distribution as opposed to DC. There are advantages and disadvantages to this:</p>
<!-- <p> </p>
<ul>
<li></li>
<li></li>
<li></li>
<li></strong></li>
<li></li>
<li></li>
<li></li>
<li></li>
<li></li> 
</ul> -->

<h2>Power Supply Types</h2>
<h3>An Unregulated Power Supply</h3>
<div class="row">
    <div class="column.large-centered">
    <img src="{{ site.urlimg }}psuUnreg.jpg" alt="">
    </div>
</div>
<p>image credit: https://www.elprocus.com/</p>
<p></p>

<h3>A Linear Regulated Power Supply</h3>
<p></p>
<div class="row">
    <div class="column.large-centered">
    <img src="{{ site.urlimg }}psuRegLin.jpg" alt="">
    </div>
</div>
<p>image credit: https://www.elprocus.com/</p>
<p></p>

<h2>My Dual Rail Short Protected Linear Power Supply</h2>
<div class="row">
    <div class="column.large-centered">
    <img src="{{ site.urlimg }}psuFullOpAmpCircuitRun.jpg" alt="">
    </div>
</div>
<h2>Why build a supply with dual rails?</h2>
<h3> Operational Amplifiers (opamps)</h3>
<p>Having a supply with + & - voltage rail allows the user to amplify analog signals like music or sensor data with massive signal gain. One way to do this is to use an opamp.</p>
<!-- <div class="row">
    <div class="column.large-centered">
    <img src="{{ site.urlimg }}psuOpAmp.jpg" alt="">
    </div>
</div> -->
<a href="https://everycircuit.com/circuit/6586919818625024">Non-inverting and inverting op-amp simulation</a><br>
<iframe width="560" height="360" src="https://everycircuit.com/embed/6586919818625024" frameborder="0"></iframe>
<p>Using the circuit configuration shown in the above simulation we can both amplify and invert any input signal within that opamps capability. The results in real life are nothing short of astounding...</p>
<h4>100x signal gain using using a non-inverting amplifier w/negative feedback</h4>
<div class="row">
    <div class="column.large-centered">
    <img src="{{ site.urlimg }}psuinputAmplified.jpg" alt="">
    </div>
</div>
Here, I use my input supply with +/- 10V rails to amplify an input signal (sine wave) of 20 mVpp to nearly 2 Vpp (~100x gain) with near perfect accuracy using a <a href="https://www.futurlec.com/Motorola/MC33174.shtml">Motorolla MC33174</a>. In order to amplify the signal without clipping the waveform, the range of the rails must be larger than the highest amplified output on both edges. In this case, we were going for 100x amplification and nearly got it.</p>
<h4>Waveform Inversion & 100x signal gain using an inverting amplifier</h4>
<div class="row">
    <div class="column.large-centered">
    <img src="{{ site.urlimg }}psuinputAmplifiedReversed.jpg" alt="">
    </div>
</div>

<h2>Custom Built Overcurrent Protection Circuit</h2>
<div class="row">
    <div class="column.large-centered">
    <img src="{{ site.urlimg }}psuprot0.jpg" alt="">
    </div>
</div>

<h3><a href="https://everycircuit.com/circuit/6734605162643456/overcurrent-short-circuit-protection-circuit">See the live EveryCircuit simulation of this custom circuit</a></h3>
<div class="row">
    <div class="column.large-centered">
    <img src="{{ site.urlimg }}psuEverycirc.png" alt="">
    </div>
</div>
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
