# NACDeC-X Problem Statement

## "S-ARM: Sounding rocket for Advanced Research in Microgravity"

---

## 1. Core Design Mission & Problem Statement

The objective of the NACDeC-X competition is to completely design a single-stage or multi-stage sounding rocket optimized for scientific microgravity missions. The vehicle must be designed to safely carry the user payload and provide a high-quality microgravity environment.

| Design Parameter | Minimum Target Threshold Requirement |
|---|---|
| Scientific Payload Mass Capacity | ≥ 25 kg (Net customer experiment mass available) |
| Scientific Payload Volume | ≥ ɸ0.28 x 1 m Length |
| Microgravity Experiment Windows | ≥ 5 minutes (Continuous microgravity environment time) |

---

## 2. System Mass Budget & Boundary Conditions

To ensure compliance, team sub-systems must carefully account for the strict boundary definitions between the customer's payload and the vehicle's house-keeping instrumentation:

- **Scientific Payload Constraints:** The 25 kg limit belongs strictly to the customer. All experimental internal mechanisms, dedicated power supplies, and specialized furnaces (e.g., for material science experiments) must be packaged completely inside this 25 kg mass allocation. The payload volume should be within ɸ0.28 x 1 m Length or higher.
- **Excluded Vehicle Avionics:** Telemetry systems, sequencing modules, telecommand packages, and navigation hardware are categorized as vehicle overhead and cannot subtract from the 25 kg scientific payload mass allocation.
- **Excluded Vehicle Sensors:** Structural health/vehicle monitors including accelerometers, body rate sensors, magnetometers, chamber pressure taps, and temperature transducers are outside the customer payload budget.
- **Excluded Operational Mechanisms:** The nose cone separation mechanics, data acquisition (DAQ) baseboard nodes, and core vehicle power bus strings do not count toward the 25 kg payload mass.

---

## 3. Work Breakdown Structure (WBS) & Engineering Disciplines

Participating teams must perform complete mathematical modeling, engineering design, verification, and manufacturing plan definition across the following core technical domains:

- **Propulsion Systems:** Motor selection (solid, liquid, or hybrid), grain geometry design, thermal design, nozzle sizing, total impulse calculations, etc.
- **Aerodynamic Design:** Nose cone profile, fin planform, and interstage design while ensuring enough static margin across all Mach regimes; drag coefficient estimation, aero-heating modeling, etc.
- **Structural Design:** Motor case design, flange designs, material selection, stress/buckling limits under pressure load, launch loads, maximum dynamic pressure, transonic conditions, weight optimization, and internal mounts for components.
- **Avionics System Design:** Power distribution networks, sequencing logic boards, RF architecture, telemetry link budget, and sensor data handling systems.
- **Trajectory Design & Simulation:** 6-DOF flight dynamic simulation, multi-stage optimization, wind weighting dispersion analyses, apogee validation, and timeline generation.
- **Separation System Design:** Nose cone/stage/payload separation system design, mechanical staging layout, pyrotechnic or mechanical spring mechanisms, and clean extraction kinematics.
- **Launcher Requirements:** Launch guide length, tilt angles, ground support equipment (GSE), and structural limits of the launch pad assembly.

---

## 4. Launch Sites & Range Safety Constraints

Teams must explicitly design their trajectory, the launch azimuth and elevation angles, and carry out Range Safety Studies (including impact zones considering dispersions and wind) for one or more of the following designated launch sites:

- **TERLS:** Thiruvananthapuram, Kerala.
- **SDSC SHAR:** Sriharikota, Andhra Pradesh.
- **SLC:** Kulasekharapatnam, Tamil Nadu.
- **Mobile Launchers:** Alternative highly enterprising deployment mode. Requires full specification of transporter-erector-launcher (TEL) mechanisms.

---

## 5. Design Extensions & Value-Add Tasks

To gain competitive advantages, teams can optionally scope further systems engineering design challenges if timeline margins allow:

- **Fabrication Outline:** Provide explicitly structured manufacturing routing steps, tooling plans, material certifications, and assembly integrations for the primary structure and specialized separation sub-assemblies.
- **Recovery System Design:** Although excluded from the core evaluation criteria, highly enterprising teams can architect parachute deployments, deceleration systems, marine/land location beacons, and floatation mechanisms.

---

## 6. Team Verification & Compliance Checklist

Use this dynamic checklist matrix during engineering reviews to track design readiness before final design report submission.

| Sub-System / Task | Core Deliverable Target | Status |
|---|---|---|
| Payload & Spacecraft | Verify payload meets minimum mass and volume constraints 25 kg | [ ] Open |
| Propulsion & Aero | Confirm rocket design delivers 5+ mins microgravity time | [ ] Open |
| Structures & Systems | Perform structural safety factor & airframe stress analysis | [ ] Open |
| Avionics & Control | Complete electrical wiring harness & telemetry link budget | [ ] Open |
| Trajectory & Safety | Run 6-DOF simulation & map launch range safety impact zones | [ ] Open |
| Fabrication & Options | Draft step-by-step manufacturing routing & optional recovery layers | [ ] Open |

---

## Section Addendum: Microgravity Environment & Engineering Evaluation

### Elaboration on the Microgravity Environment

In the context of suborbital sounding rockets, microgravity (µg) is not the absence of Earth's gravity. Instead, it is an environment created when the rocket's payload section enters a state of unconstrained free fall after motor/engine burnout and leaving the atmosphere. During this ballistic phase, the vehicle and the internal scientific payload accelerate toward Earth at the exact same rate, causing the apparent weight of the system to drop to near-zero (10⁻⁴ g to 10⁻⁶ g).

For physical, biological, pharmaceutical and materials science experiments, this environment fundamentally alters physical behaviours by effectively eliminating:

- **Buoyancy-Driven Convection:** Eliminates density-driven fluid currents, allowing pure diffusion to dictate thermal and mass transport.
- **Sedimentation and Stratification:** Prevents heavier particles or crystalline structures from sinking, enabling perfectly homogeneous material synthesis and uniform crystal growth.

---

## Figure of Merit (FoM) for NACDeC-X Competition

$$
FoM = \frac{T_{\mu g} \times m_{payload}}{\log_{10}(a_{residual}) \times M_{Dry} \times C_{complexity}}
$$

### Metric Definitions & Variable Targets

| Variable | Metric Component | Measurement Unit | Design Target / Objective |
|---|---|---|---|
| T<sub>µg</sub> | Microgravity Duration | Seconds (s) | ≥ 300 s (The mandatory 5 min threshold) |
| m<sub>payload</sub> | Scientific Payload Mass | Kilograms (kg) | ≥ 25 kg (Excludes housekeeping avionics) |
| a<sub>residual</sub> | Peak Residual Acceleration | Micro-g (µg) | Minimize |
| M<sub>Dry</sub> | Vehicle Total Dry Mass | Kilograms (kg) | Minimize |
| C<sub>complexity</sub> | System Complexity Factor | Multiplier (1.0–2.0) | Penalizes multi-stage separation risks |

### Parameter Breakdown for Team Tracking

- **Microgravity Duration (T<sub>µg</sub>):** Measured strictly from the moment the vehicle crosses the threshold where atmospheric drag acceleration falls below 10⁻⁴ g on ascent, to the moment it re-enters denser air layers on descent.
- **Peak Residual Acceleration (a<sub>residual</sub>):** The maximum disturbances/g-jitters encountered during the free-fall phase. A more stable aerodynamic design or an active cold-gas Reaction Control System (RCS) keeps this value low, drastically improving the quality of the microgravity window.
- **Vehicle Dry Mass (M<sub>Dry</sub>):** Reflects structural optimization. A lighter dry mass implies advanced composites or ultra-efficient propellant mass fractions, yielding a higher FoM.
- **Complexity Factor (C<sub>complexity</sub>):** A penalty metric defined by the team based on architecture:
  - **Single-Stage Rocket:** 1.0 (Lowest staging risk)
  - **Two-Stage Rocket:** 1.3 (Staging/separation mechanics risk)
  - **Active RCS/Despin Mechanism added:** Add +0.2 to the factor due to avionic and hardware complexity.

---

## Time Line for NACDeC-X

### Launch of Competition & Preparation for DCE

| Deadline (2026) | Task |
|---|---|
| 19th Oct | Release of Problem Statement |
| 30th Nov | Deadline for Team Registration |

### Stages – I, II & III

| Deadline (2027) | Task |
|---|---|
| 15th Jan | Online Design Competency Exam (DCE) |
| 31st Jan | Shortlisting of teams for Stage-I |
| 30th Apr | Mid Term Report (MTR) Submission |
| 15th May | Shortlisting for Stage-02 |
| 30th Jul | Final Design Report (FDR) Submission |
| 30th Aug | Shortlisting for Stage-03 |
| 15th Sep | Final Round |

---

## Tasks Expected to be Carried Out

### Stage-II: Mid Term Report (MTR)

- **M-1: Literature Survey** — Conduct a literature survey for design of the single stage/multi stage sounding rocket optimised for scientific micro gravity missions.
- **M-2: Propulsion System** — Motor selection (solid, liquid, or hybrid), grain geometry design, thermal design, nozzle sizing, total impulse calculations, etc.
- **M-3: Aerodynamic Design** — Nose cone profile, fin planform, and interstage design while ensuring enough static margin across all Mach regimes, drag coefficient estimation, aero-heating modeling, etc.
- **M-4: Structural Design** — Motor case design, flange designs, material selection, stress/buckling limits under pressure load, launch loads, maximum dynamic pressure, transonic conditions, weight optimization, and internal mounts for components.

### Stage-III: Final Design Report (FDR) (with inclusion of MTR)

- **F-1: Avionics System Design** — Power distribution networks, sequencing logic boards, RF architecture, telemetry link budget, and sensor data handling systems.
- **F-2: Trajectory Design & Simulation** — 6-DOF flight dynamic simulation, multi-stage optimization, wind weighting dispersion analyses, apogee validation, and timeline generation.
- **F-3: Separation System Design** — Nose cone/stage/payload separation system design, mechanical staging layout, pyrotechnic or mechanical spring mechanisms, and clean extraction kinematics.
- **F-4: Launcher Requirements** — Launch guide length, tilt angles, ground support equipment (GSE), and structural limits of the launch pad assembly.
