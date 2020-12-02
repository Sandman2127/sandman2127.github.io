---
layout: page-fullwidth
title:  "A Universal DC adapter"
categories:
    - design
header:
   image_fullwidth: psufull.jpg
---
<h2><strong>A Linear Regulator</strong></h2>
<p></p>


<h3><strong>The Build</strong></h3>
<p><strong>AC electricity</strong></p>
<p><strong>Intermediate forms</strong></p>
<p><strong>Regulated DC electrical potential</strong></p>

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

<h2><strong>Custom Built Overcurrent Protection Circuit</strong></h2>
<div class="row">
    <div class="column.large-centered">
    <img src="{{ site.urlimg }}psuprot0.jpg" alt="">
    </div>
</div>

<h3><strong><a href="https://everycircuit.com/circuit/6734605162643456/overcurrent-short-circuit-protection-circuit">See the live EveryCircuit simulation of this custom circuit</a></strong></h3>
<div class="row">
    <div class="column.large-centered">
    <img src="{{ site.urlimg }}psuEverycirc.png" alt="">
    </div>
</div>
<h3><strong>Description of Operation</strong></h3>
<p>This is a functional overcurrent protection circuit. It measures the voltage drop across the 220 mOhm resistor on the far left supply. That voltage is boosted and compared against a reference voltage in the second opamp (comparator mode) and an SR latch is used to latch the overcurrent result.</p> 
<p>If the output of the first opamp is lower than the inverting input (-) voltage the output of the second opamp is low, otherwise the output goes high.</p>  
<p>The output of the second opamp is fed to an SR latch (2 NOR gates). When the opamp output and the reset switch are low the output Q is low and the relay is off (i.e. the circuit operates normally).</p> 
<p>When the opamp goes high (due to sensing an overcurrent event across the 0.22 ohm resistor) Q latches, the red LED turns on and the circuit deactivates nearly instantly protecting your supply.  You can simulate overcurrent by reducing the 8 ohm resistor resistance.</p> 
<p>To reset the system properly, flip the switch to high and back to low. This resets the latch (and green LED protected indicator). Note the circuit will only continue operating again when you increase resistance of the primary load (>= 8 ohm). </p>
<!-- <h3>An intermediate build stage</h3> -->
<!-- <div class="row">
    <div class="column.large-centered">
    <img src="{{ site.urlimg }}psuprot1.jpg" alt="">
    </div>
</div> -->
<h3><strong>Power supply in shutdown state (red led active)</strong></h3>
<div class="row">
    <div class="column.large-centered">
    <img src="{{ site.urlimg }}psuprot3.jpg" alt="">
    </div>
</div>
<p>My system is hardwired to allow no more than 2A @ 16VDC. If the resistance of load drops below a threshold that higher than 2A <em>would flow</em> the protection circuit activates and immediately shuts off the supply. It can only be reactivated through the reset switch.</p>

<h3><strong>Power supply in active passing current state (blue led active)</strong></h3>
<div class="row">
    <div class="column.large-centered">
    <img src="{{ site.urlimg }}psuprot2.jpg" alt="">
    </div>
</div>
