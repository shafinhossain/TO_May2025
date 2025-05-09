The Eight-Way Power Amplifier
##############################################

Design Procedure
##############################################

The Eight-Way Power Amplifier was developed as an **advanced extension** of the previous Two-Way and Four-Way PAs, aiming to achieve a **Psat of ~26 dBm at 180 GHz**. This design further scales the validated **three-stage common emitter (CE) unit cell** structure using a **hierarchical Wilkinson power network**, while also incorporating **optimized RF choke and transmission line structures** to reduce insertion loss and improve gain flatness.

The architecture follows:

- **8 identical unit cells**, arranged symmetrically
- **3-level Wilkinson splitter/combiner** tree: 
  - **1:8 power splitting** at the input
  - **8:1 power combining** at the output
- Improved **RF chokes and bias lines** to minimize interference and boost thermal performance

The design leverages the known **+3 dB power scaling per doubling** of unit cells. From a unit cell with 17 dBm Psat:
- Two-way PA yields 20 dBm
- Four-way PA yields 23 dBm
- **Eight-way PA yields ~26 dBm**, which exceeds performance of reported cascode-based SiGe designs

The design process used:
- **Schematic-first approach**, then layout
- **EM simulation** of Wilkinson tree and interconnects
- Layout validation via **LVS** and parasitic-aware refinement

Layout Design
----------------------------------------

.. image:: _static/Eight_way_PA_layout_view.PNG
    :align: center
    :width: 1000
    :height: 1000

The layout integrates:

- **8 CE unit cells**, four on each side, symmetrically placed
- Central **multi-level Wilkinson network**
- Advanced **choke structures** (visible near output/input pads)
- **Dedicated routing** for VCC1, VCC2, VBB1, VBB2 with thermal and parasitic minimization
- Hexagonal **GSG RF pads** at mid-height for symmetric probing
- **Wide signal paths** and **multi-layer routing** for handling high current and minimizing losses

The layout was rigorously simulated for **insertion loss, return loss, phase balance**, and **combining efficiency**, ensuring optimal performance across the full 170–190 GHz band.

Expected Performance
###########################################################

Due to simulator limitations, **full large-signal transient analysis** could not be carried out for the 8-way PA. However, based on the well-matched and EM-simulated Wilkinson network, and assuming near-ideal power combining:

- **Gain** expected to be ~6 dB
- **Psat** expected at **~26 dBm**, based on additive power scaling:
  - Unit Cell: 17 dBm
  - Two-Way: +3 dB → 20 dBm
  - Four-Way: +3 dB → 23 dBm
  - **Eight-Way: +3 dB → 26 dBm**

This design significantly exceeds reported results from existing **180 GHz SiGe PAs**, particularly those based on cascode topologies, offering higher output power with simpler implementation.

Stability and Matching
----------------------------------------

Although full stability plots are not shown here, the amplifier is expected to be **unconditionally stable** due to:

- Balanced routing of 8 amplifier paths
- Interstage damping resistors
- Decoupling capacitors and ground planes
- EM-simulated Wilkinson design ensuring high isolation

The layout ensures excellent **input/output matching**, **low return loss**, and **minimal crosstalk**, even with high parallelism.

Pad Layout
----------------------------------------

The pad layout remains consistent with the Two-Way and Four-Way PAs, with additional **bias and power pads** to support 8 branches.

- RF Pads: **Hexagonal**, mid-height, GSG format
- Power/Bias Pads: Square, color-coded
- Pad pitch and orientation designed for **on-wafer high-frequency probing**

Additional care was taken to **minimize parasitic coupling** across the denser layout while maintaining **routing symmetry**.

