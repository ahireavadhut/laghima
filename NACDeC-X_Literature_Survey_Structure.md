# NACDeC-X Literature Survey: Structure (10 pages)

**Title:** Literature Survey for a Sounding Rocket Optimised for Scientific Microgravity Missions (S-ARM)

---

## Page Allocation

| Pg | Section | Main Content |
|---|---|---|
| 1 | 1. Problem Understanding | Requirements table, mass boundary diagram, FoM breakdown |
| 2 | 2. Microgravity Environment | Flight profile figure, disturbance sources, first-order sizing |
| 3 | 3. Existing Sounding Rockets (A) | Master comparison table |
| 4 | 3. Existing Sounding Rockets (B) | Derived metrics, plots, observations |
| 5 | 4. Architecture Options | Morphological chart, candidate table, FoM sensitivity, down-select |
| 6 | 5. Subsystem Survey (A) | Propulsion, aerodynamics |
| 7 | 5. Subsystem Survey (B) | Structures, attitude control and µg quality |
| 8 | 5. Subsystem Survey (C) | Avionics, separation, trajectory and simulation |
| 9 | 6. Launch Sites, Range Safety, Launcher | Site table, impact footprint, launcher types, recovery and fabrication |
| 10 | 7. Gap Analysis + 8. References | Findings to design inputs, target envelope, references |

*If references are excluded from the page limit, give Section 7 the full page 10 and put references on page 11.*

---

## 1. Problem Understanding (Pg 1)

### 1.1 Mission Statement
One line: what is being designed, for what, and what defines success.

### 1.2 Requirements Table (Table 1)
| ID | Requirement | Threshold | Source (PS section) | How It Will Be Verified |
|---|---|---|---|---|
| R1 | Payload mass | ≥ 25 kg | §1 | Mass budget |
| R2 | Payload volume | ≥ ɸ0.28 m × 1 m | §1 | CAD envelope |
| R3 | µg window | ≥ 300 s | §1 | 6-DOF trajectory |
| R4 | Launch sites | TERLS / SHAR / SLC / mobile | §4 | Range safety study |
| R5 | Deliverables | M-1 to M-4, F-1 to F-4 | Tasks | Report checklist |

### 1.3 Mass Boundary Diagram (Figure 1)
Block diagram of what is inside the 25 kg customer payload and what is vehicle overhead (avionics, sensors, separation, DAQ, power bus).

### 1.4 FoM Breakdown (Table 2 + Figure 2)
| Variable | Direction | Controlled By | Subsystem Lever |
|---|---|---|---|
| T_µg | ↑ | Burnout velocity, drag | Propulsion, aero |
| m_payload | ↑ | Mission choice | Payload |
| a_residual | ↓ | Attitude control, separation | Avionics, aero, RCS |
| M_dry | ↓ | Structure, mass fraction | Structures, propulsion |
| C_complexity | ↓ | Architecture | Staging, RCS |

Figure 2: FoM tree showing each variable and the design decisions that move it.

### 1.5 FoM Behaviour (Figure 3)
- Plot FoM vs a_residual (note the log₁₀ term: zero at 1 µg, negative below).
- Table of C values: single = 1.0, single + RCS = 1.2, two-stage = 1.3, two-stage + RCS = 1.5.

### 1.6 Scope Map (Table 3)
Mapping of M-1 to M-4 and F-1 to F-4 to the sections of this survey.

---

## 2. Microgravity Environment (Pg 2)

### 2.1 Free-Fall Physics and Flight Profile (Figure 4)
Altitude-time plot with phases marked: lift-off, burn, burnout, coast, µg start (drag < 10⁻⁴ g), apogee, µg end, re-entry.

### 2.2 Disturbance Sources (Table 4)
| Source | Phase | Typical Magnitude | Mitigation |
|---|---|---|---|
| Residual aero drag | Start/end of window | | |
| Vehicle spin / coning | Coast | | |
| Despin / separation shock | Pre-window | | |
| RCS thruster firing | Coast | | |
| Fluid slosh, payload motion | Coast | | |
| Vibration, structural modes | Burn / coast | | |

### 2.3 First-Order Sizing (Table 5 + Figure 5)
- Relations: T_µg ≈ 2v/g, coast height ≈ v²/2g.
- Table: T_µg (300, 360, 420, 480 s) vs required upward velocity at window start, coast height, approximate apogee.
- Figure: T_µg vs required velocity and apogee.

### 2.4 Experiment Classes (Table 6)
| Class | Example | Mass / Volume Need | Power | Duration | µg Level Needed |
|---|---|---|---|---|---|
| Materials | Furnace, crystal growth | | | | |
| Fluid physics | Convection, boiling | | | | |
| Biology | Cell cultures | | | | |
| Pharmaceutical | Protein crystallisation | | | | |

---

## 3. Existing Sounding Rockets (Pg 3–4)

### 3.1 Master Comparison Table (Table 7, full page)

**Columns:** Vehicle | Agency / Country | No. of Stages | Propulsion (type, motor) | Lift-off Mass | Length | Diameter | Payload Mass | Payload Volume | Apogee | µg Time | µg Level | Attitude Control (spin / RCS) | Recovery | Heritage / Reliability | Source

**Rows (candidate vehicles to fill from sources):**

| Group | Vehicles |
|---|---|
| Dedicated µg vehicles | TEXUS, MAXUS, MASER, VSB-30 |
| Indian sounding rockets | RH-200, RH-300, RH-560, ATV |
| Research sounding rockets | Black Brant (IX / XII), Improved Orion, Terrier-Orion, S-520 / SS-520, Skylark |
| Other µg platforms | New Shepard (reusable), Mapheus |

### 3.2 Derived Metrics (Table 8)
Computed for each vehicle from Table 7:

| Vehicle | Payload Fraction | Dry Mass Fraction | µg Time per kg Lift-off | Estimated FoM (NACDeC formula) |
|---|---|---|---|---|
| | | | | |

### 3.3 Plots (Figures 6 to 8)
- Figure 6: Payload mass vs µg time (bubble size = lift-off mass).
- Figure 7: µg time vs apogee, grouped by number of stages.
- Figure 8: Payload fraction vs lift-off mass.

### 3.4 Staging and Attitude Strategy Matrix (Table 9)
| Vehicle | Single / Two-Stage | Despin | RCS | Nose-Cone Separation |
|---|---|---|---|---|

### 3.5 Observations (Table 10)
| Observation | Evidence | Implication for S-ARM |
|---|---|---|

---

## 4. Architecture Options (Pg 5)

### 4.1 Morphological Chart (Figure 9)
| Decision | Options |
|---|---|
| Stages | Single / Two |
| Propulsion | Solid / Hybrid / Liquid |
| Attitude control | Passive spin / Despin / Cold-gas RCS |
| Launch mode | Fixed site / Mobile |
| Recovery | None / Parachute |

### 4.2 Candidate Architectures (Table 11)
| ID | Stages | Propulsion | Attitude Control | C_complexity | Expected M_dry | Main Risk |
|---|---|---|---|---|---|---|
| A1 | 1 | Solid | Passive | 1.0 | | |
| A2 | 1 | Solid | RCS | 1.2 | | |
| A3 | 2 | Solid | Passive | 1.3 | | |
| A4 | 2 | Solid | RCS | 1.5 | | |
| A5 | 1 | Hybrid | Passive / RCS | 1.0 / 1.2 | | |
| A6 | 1 | Liquid | RCS | 1.2 | | |

### 4.3 FoM Sensitivity (Figure 10)
Bar chart of relative FoM across A1 to A6, and the break-even M_dry / payload gain needed for two-stage to beat single-stage.

### 4.4 Down-Select (Table 12)
Weighted decision matrix: criteria (FoM, heritage, indigenous availability, manufacturability, risk) against candidate architectures. Output: 2 to 3 shortlisted architectures carried into the Design Philosophy report.

---

## 5. Subsystem Survey (Pg 6–8)

### 5.1 Propulsion (Pg 6)
- Table 13: Solid vs hybrid vs liquid (Isp, density, cutoff control, thrust profile, complexity, cost, indigenous availability, µg-vibration impact).
- Table 14: Propellant options (HTPB/AP/Al, paraffin/N₂O, others) with Isp, burn rate, density.
- Table 15: Grain geometries (BATES, star, finocyl, etc.) with thrust profile, volumetric loading, use case.
- Figure 11: ΔV budget (Tsiolkovsky) vs mass ratio for single and two-stage.
- Short list: nozzle types, thermal protection methods, available motors.

### 5.2 Aerodynamics (Pg 6)
- Table 16: Nose cone profiles (tangent ogive, von Kármán, Haack, conical) with drag by Mach regime, fabrication, heating.
- Table 17: Fin planform options (trapezoidal, clipped delta, etc.) with stability, drag, flutter risk.
- Figure 12: Typical C_D vs Mach curve and static margin vs Mach.
- Table 18: Aero-heating estimation methods and tools (OpenRocket, RASAero, CFD, empirical).

### 5.3 Structures (Pg 7)
- Table 19: Load cases (launch, max-q, transonic, burnout, separation) with governing effect.
- Table 20: Material comparison (steel grades, aluminium, CFRP, titanium) with specific strength, cost, manufacturability, thermal limit.
- Table 21: Motor case joints and flange options.
- Short list: buckling and stress analysis methods, internal mounting approaches.

### 5.4 Attitude Control and µg Quality (Pg 7)
- Table 22: Passive spin vs despin (yo-yo) vs cold-gas RCS: mass, complexity, achievable a_residual, C penalty.
- Figure 13: a_residual vs C_complexity trade (links to the FoM).

### 5.5 Avionics (Pg 8)
- Figure 14: Avionics block diagram (power, sequencer, telemetry, telecommand, sensors, DAQ).
- Table 23: Telemetry bands and link budget parameters.
- Table 24: Sensor suite (accelerometer, rate gyro, magnetometer, pressure, temperature) with range and purpose.

### 5.6 Separation Systems (Pg 8)
- Table 25: Mechanisms (pyro bolt, clamp band, spring, pneumatic) with shock level, reliability, mass, reusability.
- Short list: nose-cone, stage and payload separation kinematics.

### 5.7 Trajectory and Simulation (Pg 8)
- Table 26: 6-DOF tools and methods (in-house MATLAB/Python, OpenRocket, commercial) with fidelity and effort.
- Short list: wind weighting, dispersion (Monte Carlo), apogee validation.

---

## 6. Launch Sites, Range Safety, Launcher (Pg 9)

### 6.1 Launch Site Comparison (Table 27)
| Site | Latitude | Allowed Azimuth Range | Impact Zone | Existing Infrastructure | Sounding Rocket Heritage |
|---|---|---|---|---|---|
| TERLS | | | | | |
| SDSC SHAR | | | | | |
| SLC (Kulasekharapatnam) | | | | | |
| Mobile launcher | n/a | | | | |

### 6.2 Range Safety Methods (Figure 15)
Schematic of impact footprint with wind and dispersion ellipse, plus the method used to compute it.

### 6.3 Launcher Types (Table 28)
Rail vs tower vs mobile TEL: guide length, tilt, GSE, structural limits, transportability.

### 6.4 Value-Add Options (Table 29)
| Option | Literature Approaches | Added Mass / Complexity | Worth Scoping? |
|---|---|---|---|
| Recovery system | | | |
| Fabrication routing | | | |

---

## 7. Gap Analysis and Design Inputs (Pg 10)

### 7.1 Findings to Design Decisions (Table 30)
| Finding | Evidence (Section / Table) | Design Implication | Feeds Report Section |
|---|---|---|---|

### 7.2 Preliminary Target Envelope (Table 31)
| Parameter | Range From Literature | Starting Value for Design |
|---|---|---|
| Lift-off mass | | |
| Burnout velocity | | |
| Apogee | | |
| Dry mass fraction | | |
| Achievable a_residual | | |

### 7.3 Open Questions (Table 32)
Items to clarify with organizers or resolve in design (e.g. FoM treatment below 1 µg, µg window definition, range constraints).

---

## 8. References (Pg 10)

Numbered list: papers, agency user manuals (TEXUS, MAXUS, MASER, VSB-30, RH series), textbooks, NACDeC-IX reports.

---

## Figure and Table Inventory

| Section | Figures | Tables |
|---|---|---|
| 1 | 1 to 3 | 1 to 3 |
| 2 | 4 to 5 | 4 to 6 |
| 3 | 6 to 8 | 7 to 10 |
| 4 | 9 to 10 | 11 to 12 |
| 5 | 11 to 14 | 13 to 26 |
| 6 | 15 | 27 to 29 |
| 7 | none | 30 to 32 |

*Total: 15 figures, 32 tables. Tables in Sections 5 to 7 can be merged or shrunk to fit the 10-page limit.*
