# Projects

A collection of VLSI physical design and EDA projects completed during M.Tech coursework and lab work at IIT Bhubaneswar.

---

## 1. OpenLane Full VLSI Flow — picorv32a on Sky130A

!!! abstract "Overview"
    Ran a complete RTL-to-GDSII flow for the **picorv32a** RISC-V processor core using the open-source OpenLane/OpenROAD toolchain on the SkyWater Sky130A PDK.

**Technologies:** OpenLane, OpenROAD, Magic VLSI, ngspice, Sky130A PDK, Docker

**Key Work:**
- Configured OpenLane design files (`config.json`, SDC constraints)
- Resolved DRC violations in Magic VLSI (metal spacing, via rules)
- Integrated custom standard cell **sky130_vsdinv** into the flow
- Performed ngspice transient simulation for inverter characterization with iterative SPICE netlist debugging
- Achieved clean DRC-free layout through to GDSII

**Flow Stages Completed:**

| Stage | Tool | Status |
|-------|------|--------|
| Synthesis | Yosys + ABC | ✅ |
| Floorplan | OpenROAD | ✅ |
| Placement | OpenROAD | ✅ |
| CTS | TritonCTS | ✅ |
| Routing | TritonRoute | ✅ |
| DRC/LVS | Magic | ✅ |
| GDSII | KLayout | ✅ |

---

## 2. Cadence Innovus — DES Core Frequency & Layer Sweep Analysis

!!! abstract "Overview"
    Comprehensive Innovus place-and-route analysis of a **DES (Data Encryption Standard)** core, examining timing, area, and congestion behaviour across frequency and metal layer configurations.

**Technologies:** Cadence Innovus, Python (matplotlib, pandas), TCL scripting

**Part 1 — Frequency Sweep (500 MHz – 2 GHz):**
- Swept target clock frequency at 7 operating points
- Extracted WNS, TNS, cell count, routing congestion
- Generated publication-quality matplotlib figures

**Part 2 — Metal Layer Ceiling Sweep at 1 GHz:**
- Restricted routing to Metal 2 through Metal 8 progressively
- Analysed impact on wirelength, via count, and DRC violations
- Exported clean Excel data files and interactive HTML dashboards

**Results:** Identified the critical frequency knee and the minimum metal layer stack needed for DRC-clean routing at 1 GHz.

---

## 3. Synopsys PrimeTime STA — Full Lab Series (Labs 1–9)

!!! abstract "Overview"
    Completed all 9 labs of the Synopsys PrimeTime Static Timing Analysis course as part of the VLSI Physical Design course at IIT Bhubaneswar.

**Technologies:** Synopsys PrimeTime, SDC, TCL

**Labs Covered:**

| Lab | Topic |
|-----|-------|
| Lab 1 | PrimeTime environment setup, basic timing report |
| Lab 2 | Clock definition and propagation |
| Lab 3 | Input/output delay constraints |
| Lab 4 | False path and multicycle path exceptions |
| Lab 5 | Hold timing analysis and fixing |
| Lab 6 | Clock tree analysis and skew |
| Lab 7 | Multi-corner analysis |
| Lab 8 | Timing ECO and incremental analysis |
| Lab 9 | Full chip timing signoff flow |

**Deliverable:** Comprehensive PPTX presentation covering all lab flows, block diagrams, and key STA concepts.

---

## 4. ILP-Based Floorplanning (Lim Textbook Problems)

!!! abstract "Overview"
    Implemented and solved Integer Linear Programming (ILP) formulations for VLSI floorplanning problems from *Practical Problems in VLSI Physical Design Automation* (Lim).

**Technologies:** Python, PuLP, lp_solve, SVG visualization

**Key Work:**
- Formulated non-overlapping, boundary, and area constraints as ILP
- Solved using PuLP (CBC solver) and lp_solve
- Generated SVG floorplan visualizations of solved layouts
- Analysed wirelength and area objectives

---

## 5. Mixed-Signal VLSI Design — SAR ADC & CDAC Analysis

!!! abstract "Overview"
    Coursework projects for EC6L057 Mixed-Signal VLSI Design covering ADC/DAC architectures and error analysis.

**Technologies:** MATLAB/Python, analytical derivation

**Topics Covered:**
- SAR ADC architecture and conversion algorithm
- Split CDAC design and sizing
- INL/DNL calculation and plot generation
- Static and dynamic ADC performance metrics

---

## 6. AlN/β-Ga₂O₃ MOSHEMT Biosensor — Device Simulation & Publication Figure

!!! abstract "Overview"
    Contributed to device-level research on a wide-bandgap semiconductor biosensor, producing an IEEE-style publication figure template.

**Technologies:** Device simulation tools, Python (matplotlib), IEEE figure standards

**Key Work:**
- Analysed AlN/β-Ga₂O₃ MOSHEMT biosensor I-V and C-V characteristics
- Created IEEE-style publication-quality figure with proper axis labels, fonts, and formatting
- Applied professional data visualization standards for conference/journal submission

---

!!! tip "More Details"
    Full lab reports, scripts, and data files are available on request. Some repositories are private due to institutional guidelines — contact me for access.
