# Skills

A summary of my technical skills across EDA tools, physical design methodology, programming, and academic areas.

---

## Physical Design

=== "Floorplanning"
    - Die area estimation, aspect ratio selection
    - Macro placement and pin assignment
    - Power planning: VDD/VSS ring and stripes
    - Blockage creation (hard, soft, partial)
    - Tools: **Cadence Innovus**, **OpenLane/OpenROAD**

=== "Placement"
    - Standard cell placement (global + detailed)
    - Timing-driven placement
    - Congestion analysis and ECO placement
    - Placement constraint handling (don't-touch, fixed cells)
    - Custom cell integration (e.g., sky130_vsdinv in OpenLane)

=== "Clock Tree Synthesis"
    - CTS specification and constraints (max skew, insertion delay)
    - Buffer/inverter insertion
    - Clock tree debugging and optimization
    - SDC clock definitions and clock gating
    - Tools: **Innovus CTS**, **OpenROAD TritonCTS**

=== "Routing"
    - Global and detailed routing
    - DRC violation analysis and fixing
    - Via optimization
    - Signal integrity awareness
    - Metal layer utilization analysis

=== "Signoff"
    - DRC/LVS with **Magic VLSI**
    - IR drop and EM analysis
    - Post-route timing closure
    - GDS/GDSII export
    - Antenna rule checking

---

## Static Timing Analysis

| Topic | Proficiency | Tools |
|-------|-------------|-------|
| Setup/Hold Analysis | ★★★★☆ | PrimeTime, Innovus |
| SDC Constraint Writing | ★★★★☆ | PrimeTime, Innovus |
| Timing Path Debugging | ★★★★☆ | PrimeTime |
| Clock Domain Crossing | ★★★☆☆ | PrimeTime |
| Multi-Corner Multi-Mode (MCMM) | ★★★☆☆ | PrimeTime |
| Statistical STA (SSTA) | ★★☆☆☆ | PrimeTime |

!!! note "Lab Experience"
    Completed a full 9-lab PrimeTime STA series covering: basic timing analysis, constraint creation, exception handling (false paths, multicycle paths), clock analysis, and timing ECO.

---

## EDA Tools

<div class="tools-grid" markdown>

<div class="tool-card" markdown>
### Cadence Innovus
Full place-and-route flow. DES core frequency sweep analysis (500 MHz – 2 GHz), metal layer ceiling experiments, timing vs. utilization tradeoffs.
</div>

<div class="tool-card" markdown>
### Synopsys PrimeTime
Static timing analysis, constraint development, hold/setup fixing, clock tree analysis. Labs 1–9 completed.
</div>

<div class="tool-card" markdown>
### Magic VLSI
Layout editing, DRC rule checking, LVS, custom cell creation, Sky130A PDK integration.
</div>

<div class="tool-card" markdown>
### OpenLane / OpenROAD
Complete RTL-to-GDSII open-source flow. Ran picorv32a full flow on Sky130A PDK with custom cell integration.
</div>

<div class="tool-card" markdown>
### ngspice
SPICE netlist simulation, transient analysis, DC operating point. Used for sky130_vsdinv characterization.
</div>

<div class="tool-card" markdown>
### Synopsys Design Compiler
Logic synthesis, technology mapping, constraint-driven optimization.
</div>

</div>

---

## Programming & Scripting

```tcl title="TCL — EDA Automation"
# Example: Innovus batch mode frequency sweep
set freqs {500 750 1000 1250 1500 2000}
foreach freq $freqs {
    set period [expr {1000.0 / $freq}]
    create_clock -name clk -period $period [get_ports clk]
    place_design
    ccopt_design
    route_design
    report_timing > reports/timing_${freq}MHz.rpt
}
```

```python title="Python — Data Analysis & Automation"
# Example: Parse Innovus timing reports across frequency sweep
import pandas as pd
import matplotlib.pyplot as plt

data = parse_timing_reports("reports/")
df = pd.DataFrame(data)
df.plot(x="frequency_MHz", y=["wns_ns", "tns_ns"])
plt.savefig("timing_vs_freq.png", dpi=150)
```

| Language | Use Case |
|----------|----------|
| **TCL** | EDA tool scripting (Innovus, PrimeTime, DC) |
| **Python** | Data parsing, matplotlib plots, PuLP ILP solver |
| **Shell / Bash** | Flow automation, job scheduling on lab machines |
| **Verilog** | RTL design and testbench writing |
| **SystemVerilog** | Verification constructs |

---

## Academic & Domain Knowledge

- **CMOS Digital Design** — logic families, static/dynamic circuits, power analysis
- **Mixed-Signal Design** — DAC/ADC architectures (SAR ADC, split CDAC), INL/DNL
- **Device Physics** — AlN/β-Ga₂O₃ MOSHEMT biosensor research (device simulation)
- **Floorplanning Theory** — ILP-based formulations (Lim textbook problems)
- **Low Power Design** — Clock gating, power domains, multi-Vt strategies
