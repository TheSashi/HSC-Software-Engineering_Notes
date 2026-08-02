---
title: Mechatronics
subject: Software Engineering
type: final
unit: Year 11
syllabus_topic: Programming Mechatronics
tags:
  - software-engineering
  - mechatronics
  - hsc
  - final
  - exam-ready
  - year-11
aliases:
  - Programming Mechatronics
  - Control Systems
  - CPU vs Microcontroller
---

# Mechatronics — HSC Final Notes

> **Year 11, Unit 3** | What mechatronics is, CPUs vs microcontrollers, sensors and actuators, wiring diagrams, control algorithms and electricity fundamentals.

---

## 1. What Mechatronics Is

**Definition**: Mechatronics = **Mechanics + Electronics + Computing + Control Systems**.

> "Mechatronics is a field that combines mechanical, electrical, electronic, and software engineering to create smarter and more efficient systems."

**Origin**: The term was coined in Japan by **Tetsuro Mori**, an engineer at **Yaskawa Electric Corporation** — a combination of "mechanics" and "electronics".

**Where it is found**: robotics, automated systems, smart home devices, robotic arms, drones, self-driving cars.

| Benefits | Drawbacks |
|---|---|
| Efficiency and speed | Job loss in some sectors |
| Reduced human error | High costs |
| Can take on **dangerous or repetitive** tasks | Ethical concerns (surveillance, dependency) |

**Applications for people with disability:**

- **Exoskeleton suits** — for cerebral palsy
- **Robotic prosthetic limbs** — for amputations
- **Brain–machine interfaces** — for spinal injuries
- Custom robotic enhancements

---

## 2. CPUs and Microcontrollers

### 2.1 CPU Components

| Component | Role |
|---|---|
| **Control Unit (CU)** | Runs the CPU, and thus the fetch–execute cycle |
| **Arithmetic Logic Unit (ALU)** | Runs mathematical and logical operations |
| **Registers** | Temporary memory locations mainly accessible to the CPU |

### 2.2 The Registers

> **A register is a temporary memory location mainly accessible to the CPU.**

| Register | Full name | Holds |
|---|---|---|
| **PC** | Program Counter | The **address of the next** instruction to be executed |
| **MAR** | Memory Address Register | The memory address **currently being accessed** |
| **MDR** | Memory Data Register | The **data** fetched from or being written to that address |
| **ACC** | Accumulator | The **results** of the current operations |
| **CIR / IR** | Current Instruction Register | The **current instruction** being executed |

> **Confusing pair — MAR vs MDR**
> **MAR** holds the **address** (*where* in memory).
> **MDR** holds the **data** (*what* is at that address).
> Address register = the house number; data register = what's inside the house.

### 2.3 The Fetch–Execute Cycle

```
BEGIN
    PC → MAR                        fetch: address of next instruction
    MAR sends address to RAM
    RAM sends data at address to MDR
    MDR → CIR                       instruction now in the instruction register
    CU decodes CIR contents         decode
    OPCODE  ← CIR[bits 0–3]         what to do
    OPERAND ← CIR[bits 4–7]         what to do it to
    IF OPCODE == 0101 THEN load operand into ACC
    IF OPCODE == 0001 THEN ACC ← ACC + MDR
    IF OPCODE == 0010 THEN ACC ← ACC − MDR
    PC ← PC + 1                     point at the next instruction
END
```

**Step by step (one cycle):**

1. CU copies **PC** to **MAR**
2. Address goes onto the **Address Bus**
3. Memory loads the value onto the **Data Bus**
4. Value arrives in **MDR**
5. Value moves to **CIR**
6. **PC is incremented**
7. Decode Unit splits the instruction into **opcode** and **operand**
8. Opcode `0000` means **end program**

> **Confusing pair — Opcode vs Operand**
> **Opcode** = the **operation** to perform (bits 0–3) — the verb.
> **Operand** = the **data or address** to perform it on (bits 4–7) — the noun.

### 2.4 Machine Language Worked Examples

Instructions and data are stored as **binary in RAM**.

> Addresses `0010 1000` (= 5) and `0010 1001` (= 3) match the values typed in.
> Memory 6 contained `A1`; the program added Memory 5 (`30`) → **`A1 + 30 = D1`** in hex.

**Worked: multiply Memory 5 by three, storing the result in Memory 7**

```
LOAD  (Reg1, Mem 5)        ; Reg1 = Mem5           = x
ADD   (Reg2, Reg1, Reg1)   ; Reg2 = x + x          = 2x
ADD   (Reg3, Reg2, Reg1)   ; Reg3 = 2x + x         = 3x
STORE (Reg3, Mem 7)        ; Mem7 = 3x
STOP
```

> Note the technique: there is no MULTIPLY instruction, so multiplication is achieved by **repeated addition**.

### 2.5 CPU vs Microcontroller

> "A **CPU** is just the processor and needs extra parts to work, handling many tasks fast. A **microcontroller** has a CPU, memory, and I/O **in one chip** for specific tasks."

| | **CPU** | **Microcontroller** |
|---|---|---|
| What it is | Processor only | CPU + memory + I/O **on one chip** |
| Needs extra parts? | **Yes** | **No** |
| Registers | More, and faster | Fewer |
| Opcodes | Complex | Simpler, for hardware control |
| Purpose | General-purpose, many fast tasks | Specific / **embedded** tasks |
| Example use | Desktop computer, phone | Arduino, micro:bit, washing machine |

> **Why microcontrollers suit mechatronics**: everything needed to read a sensor and drive an actuator is already on the chip — no separate memory or I/O hardware, lower cost, lower power, smaller size.

---

## 3. Mechatronic Hardware — Sensors and Actuators

### 3.1 Core Definitions

| Term | Definition |
|---|---|
| **Sensor** | A device that **transduces** a physical quantity such as pressure, light, motion or temperature **into an electrical signal** that can be read by a control system |
| **Actuator** | A mechanism that **converts electrical input into a mechanical action** — motion or force |
| **End effector / gripper** | Grips objects using mechanical jaws or fingers, often driven by servos or pneumatics |

> **Confusing term — Transduce**
> To **transduce** means to convert energy from one form into another.
> A **sensor** transduces physical → electrical (light becomes a voltage).
> An **actuator** transduces electrical → physical (a voltage becomes movement).
> They are mirror images of each other.

### 3.2 Sensors and Actuators Across Industries

| Industry | Sensors | Actuators |
|---|---|---|
| **Manufacturing** | Position, temperature, flow, pressure | Motors, valves, conveyor belts, robotic arms |
| **Healthcare** | Vital signs, movement, environment | Prosthetics, surgical tools, infusion and breathing pumps |
| **Agriculture** | Soil moisture, temperature, crop health, obstacle detection | Irrigation, spray systems, driverless tractors |
| **Construction** | Structural stress, orientation | Hydraulic machinery — excavators, lifts |
| **Transportation** | Speed, proximity, orientation | Braking, steering, doors, suspension, autonomous systems |

### 3.3 How Specific Sensors Work

| Sensor | Mechanism |
|---|---|
| **PIR** (passive infrared) | Detects **changes in infrared radiation** (body heat) across paired segments; differential signals are amplified and compared |
| **Accelerometer** | Measures **acceleration and tilt** via MEMS, across 3 axes |
| **Gyroscope** | Measures **angular velocity** via vibrating structures or a rotating mass |
| **Ultrasonic distance** | Emits pulses and measures the **echo return time** → distance |
| **LDR** (light dependent resistor) | Resistance changes with light — **dark = high** resistance, **bright = low** |
| **Analogue sensor** | Output voltage varies **continuously**; needs an **ADC** to interface with digital systems |
| **I²C light sensor** | Uses the I²C **serial protocol** for a digital light reading |
| **Joystick** | Potentiometers or hall-effect sensors giving **X/Y axis** control |

> **ADC (Analogue-to-Digital Converter)**: converts a continuously varying voltage into a discrete number the microcontroller can process. Needed because sensors produce analogue signals but processors work in binary.

### 3.4 How Specific Actuators Work

| Actuator | Mechanism |
|---|---|
| **Rotary / linear / micro servo** | Converts electrical signals to **precise movement**. Rotary servos travel up to **180°**; continuous servos rotate indefinitely |
| **Hydraulic actuator** | Fluid pressure moves a piston → **high-force** linear or rotary motion |
| **Robotic gripper** | Picks up, holds and releases objects, controlled by sensor signals |

### 3.5 Device Classification — worked

| Device | Input/Output | Type |
|---|---|---|
| DC motor | Output | Actuator |
| DC motor + gearing to clamp | Output | **End effector** (and actuator) |
| Accelerometer (3 axes) | Input | Sensor |
| Photodiode | Input | Sensor |
| 180° positional servo | Output | Actuator |

### 3.6 The Software / Data Layer

| Data type | Content |
|---|---|
| **Operational data** | Real-time sensor readings — temperature, motion |
| **Diagnostic data** | Error codes, system health metrics |
| **Optimisation data** | Historical performance for **predictive maintenance** |

> "Sensors capture raw data. The controller processes this via **filtering, analytics and decision logic** to determine actuator responses. This **feedback loop** ensures adaptability, precision and safety."

**The feedback loop:**

```
SENSOR  →  CONTROLLER  →  ACTUATOR
   ↑                          │
   └──────────────────────────┘
      (sensor reads the result of the action)
```

---

## 4. Wiring Diagrams

### 4.1 NESA Symbol Set

| Component | Function |
|---|---|
| **Capacitor** | Stores energy as an electric field |
| **Diode** | Allows current in **one direction only** |
| **Resistor** | Limits current |
| **Potentiometer** | Adjustable resistor |
| **2-way switch** | Selects between two paths |
| **On/off switch** | Opens or closes the circuit |
| **Speaker** | Converts electrical signal to sound |
| **Motor** | Converts electrical energy to rotation |
| **LED** | Light-emitting diode — indicator output |
| **Lightbulb** | Light output |
| **Integrated circuit** | A microcontroller or chip |
| **Voltage source** / **DC voltage source** | Supplies power |
| **Amplifier** (operational amplifier) | Increases signal strength |

> If a wiring diagram requires other electrical components, **the components must be clearly labelled** for identification.

### 4.2 Wiring a Real Circuit

| Goal | Wiring |
|---|---|
| **Variable speed via potentiometer** | One end to power, other end to ground; **centre tap to an analog input** |
| **On/off via switch** | One end to power, other to a digital input; **resistor to ground** prevents the input "floating" when the switch is open |
| **User feedback via LED** | One end to a digital output, other to ground **through a resistor** (limits current so the LED isn't destroyed) |
| **Power the microcontroller** | USB to voltage source; negative side to ground |

> **Confusing term — Floating input**
> A digital input not connected to either power or ground picks up electrical noise and reads randomly high or low. A **pull-down resistor** to ground gives it a defined value (0) when the switch is open.

---

## 5. Control Algorithms

> **Definition**: "A control algorithm is code that controls the operation of a mechatronic system. It uses values from the available **sensors** to compute outputs that it then sends to connected **actuators**."

### 5.1 Typical Structure

**1. Set-up / calibration** — measure the range of sensor values.
*Example*: a line-follower measures reflected light from the line versus the background, so it knows what "on the line" looks like.

**2. Main control loop** (repeated continuously):

```
(a) Read sensors           →  determine the current state
(b) Compute control values →  move toward a desired SET POINT
(c) Output to actuators
```

> **Set point** = the target value the system is trying to reach and hold — room temperature, car speed, position on the line.

> **Worked comparison from class**: the first algorithm produced **jerky on/off control** with constant overcorrection. The second used **proportional control**, where the size of the correction depends on **how far** the robot is from the line — noticeably smoother.

### 5.2 Open-Loop vs Closed-Loop

| | **Open-loop** | **Closed-loop** |
|---|---|---|
| **Feedback?** | **No** | **Yes** |
| How it works | Runs on a **fixed plan**, ignoring the result | **Measures the result** and corrects |
| Accuracy | Lower | "More accurate because the system constantly monitors feedback and adjusts itself" |
| Cost/complexity | Simple and cheap | "More complex and expensive — requires sensors, feedback mechanisms and faster processing" |

> **Closed-loop error** = the difference between the **desired set point** and the **actual sensor value**. Everything a closed-loop controller does is an attempt to drive that error to zero.

**Classification table — learn these examples:**

| System | Loop type |
|---|---|
| TV remote | **Open** |
| Vehicle cruise control | **Closed** |
| Vehicle steering | **Closed** |
| Ceiling fan speed | **Open** |
| Air conditioner temperature | **Closed** |
| Washing machine cycle timing | **Open** |
| Traffic light control | **Open** |
| Robotic arm (predetermined path) | **Open** |
| Line-following robot | **Closed** |

> **The test to apply**: does the system **measure its own output** and change behaviour based on it? A washing machine timer runs for 40 minutes whether or not the clothes are clean → **open**. An air conditioner keeps measuring the room temperature and switching accordingly → **closed**.

### 5.3 The Three Autonomous Control Algorithms

All three are **closed-loop**.

| Type | How it works | Weakness |
|---|---|---|
| **On/off ("bang-bang")** | Switches abruptly between two extremes — fully on or fully off. No intermediate levels | Constant overshoot and oscillation; jerky |
| **Proportional** | "Adjusts the output **continuously based on the size of the error**" — bigger error, bigger correction. Reduces oscillation | A small **steady-state error** may remain permanently |
| **PID** (Proportional, Integral, Derivative) | **P** responds to the current error; **I** accumulates error over time to **eliminate the steady-state error**; **D** responds to the **rate of change**, damping overshoot | More complex to tune |

> **What each PID term actually fixes**
> **P** — "how far off am I *right now*?" Gets you most of the way there.
> **I** — "how long have I been off?" Removes the small leftover error P can't fix.
> **D** — "how fast am I approaching?" Slows you down so you don't overshoot.

---

## 6. Electricity Fundamentals

### 6.1 Circuits

**Complete vs incomplete circuits**: an ammeter reads **zero** if a wire is missing between battery and bulb, the battery is wrongly connected, or the bulb is blown. It reads a value when "the circuit is connected correctly / it is a complete circuit."

### 6.2 Measuring Instruments

> **The rule to memorise: the ammeter goes in SERIES, the voltmeter goes in PARALLEL.**

| Instrument | Placement | Measures |
|---|---|---|
| **Ammeter** | In **series** with the component | Current (amps) |
| **Voltmeter** | In **parallel** with the material | Potential difference (volts) |

To **change the current** in a circuit: "adjust / use the **variable resistor**."

### 6.3 Ohm's Law — Worked Example

```
V = I × R          R = V ÷ I          I = V ÷ R
```

> **Worked (conducting putty at 25 cm, current 0.15 A):**
> - Resistance = **37.5 Ω** (accept 36–39)
> - Potential difference = R × I = 37.5 × 0.15 = **5.625 V** (mark scheme: 5.6)

**Key finding**: "The **thicker** the putty, the **lower** the resistance." A thicker conductor gives current more paths to flow through.

**Improving reliability**: "**Repeat readings and take a mean**" — *not* simply "take more readings." The mark scheme requires the averaging step.

### 6.4 Energy

**Flywheel energy** is stored as **kinetic energy**. A brighter bulb draws more energy per second, so the flywheel "**slows down more quickly**." Energy is lost from the axle and bearings (as heat and sound) and from the wires (as heat).

| Resource | Notes |
|---|---|
| **Fossil fuels** | Coal, gas (also petrol/oil) |
| **Solar panel** | Source is **the Sun**; "cannot work at night because there is no light" |
| **Wind turbine** | Blades turn due to **wind**; "cannot generate all the time because it might not be windy" |
| **Renewable** | Sun/solar, waves, wind |

---

## 7. HSC Exam Response Structures

### Common Question Types

| Question type | How to answer |
|---|---|
| **"Distinguish between a CPU and a microcontroller"** | Define both → integration of memory/IO → register count and opcode complexity → typical use case each |
| **"Describe the fetch–execute cycle"** | Name each register in order and state what moves where; finish with PC increment |
| **"Classify this system as open or closed loop, and justify"** | State the classification → identify whether a sensor measures the **output** → explain what feedback does or doesn't happen |
| **"Explain why PID is used instead of proportional control"** | Define both → identify the **steady-state error** proportional control leaves → explain how the integral term eliminates it and derivative damps overshoot |
| **"Design a control algorithm for [scenario]"** | Set-up/calibration → main loop: read sensors → compute toward set point → output to actuators |
| **"Draw a wiring diagram"** | Use the NESA symbols; label any non-standard component; include the current-limiting resistor for LEDs and the pull-down resistor for switches |

### Paragraph Scaffold

```
Topic sentence (define the term)
  → explain the mechanism (how the hardware or algorithm actually works)
  → apply to a scenario (line-follower, cruise control, your project)
  → link to a syllabus concept (feedback, accuracy vs cost, safety)
```

---

## 8. Glossary — Terms Students Mix Up

| Term | Plain meaning | Don't confuse with |
|---|---|---|
| **Sensor** | Physical → electrical | **Actuator** — electrical → physical |
| **Actuator** | Produces motion or force | **End effector** — the tool at the end that grips |
| **Transduce** | Convert energy from one form to another | Transmit (just moving a signal) |
| **CPU** | Processor only; needs external memory and I/O | **Microcontroller** — all on one chip |
| **MAR** | Holds the **address** | **MDR** — holds the **data** |
| **PC** (Program Counter) | Address of the **next** instruction | **CIR** — the **current** instruction |
| **ACC** (Accumulator) | Holds operation **results** | A general register |
| **Opcode** | The operation (bits 0–3) | **Operand** — the data/address (bits 4–7) |
| **Register** | Temporary storage inside the CPU | RAM (external main memory) |
| **Open loop** | No feedback; runs a fixed plan | **Closed loop** — measures and corrects |
| **Set point** | The target value | The current sensor reading |
| **Error** (control) | Set point **minus** actual value | A software bug |
| **On/off (bang-bang)** | Fully on or fully off | **Proportional** — correction scaled to error |
| **Proportional** | Leaves a small steady-state error | **PID** — integral removes that error |
| **Steady-state error** | Small permanent offset from the set point | Overshoot (going past the target) |
| **Analogue** | Continuously varying signal | **Digital** — discrete values; needs an **ADC** to bridge |
| **LDR** | Resistance falls as light increases | Photodiode (produces current from light) |
| **Potentiometer** | Adjustable resistor, used as a variable input | Fixed resistor |
| **Ammeter in series** | Measures current | **Voltmeter in parallel** — measures voltage |
| **Floating input** | Unconnected input reading random noise | A grounded input (defined at 0) |
| **Operational data** | Live sensor readings | **Diagnostic** — error codes; **Optimisation** — historical |

---

## 9. Key Definitions Quick Reference

| Term | One-Line Definition |
|---|---|
| Mechatronics | Mechanics + electronics + computing + control systems |
| Sensor | Transduces a physical quantity into an electrical signal |
| Actuator | Converts electrical input into mechanical action |
| End effector | The gripping tool at the end of a robotic arm |
| CPU | The processor; requires external memory and I/O |
| Microcontroller | CPU, memory and I/O integrated on a single chip |
| Control Unit | Runs the CPU and the fetch–execute cycle |
| ALU | Performs mathematical and logical operations |
| Register | Temporary memory location accessible to the CPU |
| Program Counter | Holds the address of the next instruction |
| MAR | Holds the memory address currently being accessed |
| MDR | Holds the data at that address |
| Accumulator | Holds the results of current operations |
| CIR | Holds the current instruction being executed |
| Opcode | The operation portion of an instruction |
| Operand | The data or address the operation acts on |
| Fetch–execute cycle | PC → MAR → RAM → MDR → CIR → decode → execute → PC+1 |
| ADC | Converts an analogue voltage into a digital value |
| Control algorithm | Code using sensor values to compute actuator outputs |
| Set point | The target value the system aims to reach and hold |
| Open loop | Control without feedback |
| Closed loop | Control that measures the result and corrects |
| On/off control | Switches abruptly between two extremes |
| Proportional control | Correction sized according to the error |
| PID control | Proportional + integral + derivative control |
| Steady-state error | Small permanent offset remaining under proportional control |
| Operational data | Real-time sensor readings |
| Diagnostic data | Error codes and system health metrics |
| Optimisation data | Historical performance used for predictive maintenance |
| Ohm's law | V = I × R |

---

## 10. Quick Revision Checklist

- [ ] Define mechatronics and name its four component fields
- [ ] Benefits, drawbacks and disability applications
- [ ] Name all five registers and what each holds
- [ ] Recite the fetch–execute cycle in order
- [ ] Opcode vs operand, and the bit ranges
- [ ] CPU vs microcontroller across all six comparison rows
- [ ] Sensor vs actuator vs end effector
- [ ] How PIR, ultrasonic, LDR and accelerometer work
- [ ] Classify devices as input/output and sensor/actuator
- [ ] Operational vs diagnostic vs optimisation data
- [ ] NESA wiring diagram symbols
- [ ] Why an LED needs a resistor and a switch needs a pull-down
- [ ] The control algorithm structure: calibrate → read → compute → output
- [ ] Open vs closed loop, plus the nine classification examples
- [ ] On/off vs proportional vs PID, and what each PID term fixes
- [ ] Ammeter in series, voltmeter in parallel
- [ ] Ohm's law calculation and the reliability answer ("repeat and take a mean")

---

> **See also:** [[Programming_Fundamentals]] | [[Object_Oriented_Programming]] | [[Programming_For_The_Web]] | [[Software_Automation]] | [[Secure_Software_Architecture]] | [[MOC]]
