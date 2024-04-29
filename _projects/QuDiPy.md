---
layout: page
title: Quantum Dots In Python
description: Ongoing development of a semiconductor quantum dot simulator.
img: assets/img/qudipy/2D_DQD_potential.png
importance: 1
category: research
---

The Quantum Dots in Python (QuDiPy) simulator is a collaborative and ongoing project that aims at 
simulating specific aspects of electrostatically defined quantum dots fabricated 
in semiconducting materials. Specifically, devices which are able to be fabricated 
with commercial semiconductor processes for Complementary Metal–Oxide–Semiconductor 
(CMOS) style quantum dot devices. The primary developers/maintainers are 
myself and my colleague Bohdan Krohmets. The current progress can be review on the 
[QuDiPy](https://maincsg.github.io) webpage.

An example of such devices is a laterally defined electrostatic double quantum 
dot device. A two-dimensional electron gas (2DEG) can be formed at cryogenic 
temperatures at a hetero junction interfaces of Si and an insulator (such as 
SiO_2). This 2DEG can be depleted into a regime where only a few electrons are 
occupied in desired regions in the device. Such regions are referred to as quantum 
dots (QDs) and have the ability to host electron spin qubits.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/qudipy/DQD_3d.png" 
        title="example image" 
        class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/qudipy/DQD_2d_cross_section_v2.png" 
        title="example image" 
        class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/qudipy/2D_DQD_potential.png" 
        title="example image" 
        class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    (Left) Simple 3D representation of a double QD and associated electrostatic potential landscape 
    (Middle) 2D cross section displaying how a 2DEG is formed using a combination of plunger, barrier, and screening 
    electrodes (Right) 2D cross section displaying the potential lanscaped formed for a given voltage configuration in a 
    double QD device.
</div>

The QuDiPy simulator leverages electrostatic potentials simulated using a finite 
element Poisson solver for a desired device geometry and various voltage configurations 
to simulate specific physics in a QD (or N-dimensional array of QDs), such as, 
Hubbard Hamiltonian parameters, one/two qubit gates, and electron/state shuttling.

<div class="row">
    <div class="col-sm mt-3 mt-md-0  text-center">
        {% include figure.html path="assets/img/qudipy/SpinArray_module.png" 
        title="example image" 
        class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Graphical representation showing how QuDiPy is able to simulate specific 
    electron spin qubits using electrostatic potentials from a finute element 
    Poisson solver.
</div>

The simulator has the ability to simulate voltage control pulses from various control 
methodologies for both one and two qubits. 

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/qudipy/BS_hadamard.gif" 
        title="example image" 
        class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/qudipy/pot_hadamard.gif" 
        title="example image" 
        class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    An example single qubit Hadamard gate applied to a three qubit QD device using 
    a control method developed by B. Krohmets. 
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/qudipy/spin_wave2.gif" 
        title="example image" 
        class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/qudipy/pot_spin_wave.gif" 
        title="example image" 
        class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    An example two qubit SWAP gate applied to a three qubit QD device using 
    a control method developed by B. Krohmets; performing a chain of SWAPs. 
</div>


<div class="row">
    <div class="col-sm mt-3 mt-md-0  text-center">
        {% include figure.html path="assets/img/qudipy/NN_csd_2_rot_labeled2.png" 
        title="example image" 
        class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Allowed votlage ranges for voltage control pulses are deterimend from charge 
    stability regions simulated with QuDiPy; developed by Z. Merino. 
</div>

One of the aims of the simulator is to simulate voltage control pulses for a 
node network architecture which has the potential to implement a fault tolerant 
surface code for quantum computing applications.

<div class="row">
    <div class="col-sm mt-3 mt-md-0  text-center">
        {% include figure.html path="assets/img/qudipy/Network-animation_v2.gif" 
        title="example image" 
        class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Animationg showing how a surface code can be formed with a network of QD 
    devices; defined as nodes.
</div>

An aspect of performing a fault tolerant surface requires the formation of a 
maximally entangle Bell/GHZ state. 

<div class="row">
    <div class="col-sm mt-3 mt-md-0  text-center">
        {% include figure.html path="assets/img/qudipy/Bell_state_preperation.png" 
        title="example image" 
        class="img-fluid rounded z-depth-1" 
        width="60%"%}
    </div>
</div>
<div class="caption">
    Example of a quantum ciruit to prepare a three qubit GHZ state.
</div>

This GHZ state can be formed in a three QD system by applying the following 
necessary voltage pulses which cause effective parameters (such as g-factor 
deviation and exchange energy) to have the desired time dependence.

<div class="row">
    <div class="col-sm mt-3 mt-md-0  text-center">
        {% include figure.html path="assets/img/qudipy/cnot_pulses.png" 
        title="example image" 
        class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Voltage control pulses and resultant effective parameter evolution which 
    generates and three qubit GHZ state in a QD device. 
</div>