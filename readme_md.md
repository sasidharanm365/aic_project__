# Smart Helmet Alert System Using 555 Timer IC

A low-cost, hardware-based safety system designed to enforce proper helmet usage among two-wheeler riders. Using an infrared (IR) proximity sensor, a conductive chin-strap switch mechanism, and an **NE555 Timer IC**, the system triggers an immediate audible buzzer warning if the rider wears the helmet without fastening the chin strap.

---

## Project Overview

Many riders wear helmets without buckling the chin strap, rendering the helmet ineffective during an impact. This project provides a real-time, microcontroller-free hardware alert system that monitors both head presence and strap closure.

![Smart Helmet Project Overview](images/project-overview.jpg)

*Figure 1: Side profile of the Smart Helmet prototype showing the breadboard circuit, power switch, and wiring mounted onto the helmet shell.*

---

## Hardware Components

The circuit uses basic, low-cost analog/digital components without requiring any programming or microcontroller:

| Component | Specification / Rating | Role in System |
| :--- | :--- | :--- |
| **NE555 Timer IC** | 8-Pin DIP (Monostable / Bistable control) | Acts as the core control element driving the buzzer output. |
| **IR Sensor Module** | MH-8 Reflective Optical Sensor | Detects whether the rider's head is inside the helmet. |
| **Piezo Buzzer** | 5V DC Active Buzzer | Provides an immediate audible warning when the strap is unfastened. |
| **Capacitor** | $1\,\mu\text{F}$ / $0.01\,\mu\text{F}$ | Stabilizes the Control Voltage (Pin 5) against noise. |
| **Strap Switch** | Conductive wire integrated into buckle | Acts as a closed-loop switch when the chin strap is fastened. |
| **Power Supply** | 5V DC Battery & Slide Switch | Powers the sensing and alert circuitry. |
| **Breadboard & Wires** | Mini Solderless Breadboard + Jumpers | Houses the circuit connections mounted on the helmet. |

![Hardware Components](images/components.jpg)

*Figure 2: Key electronic components used in the build — NE555N Timer IC, MH-8 IR sensor module, and 5V DC buzzer.*

---

## Circuit Diagram

### Pin Configuration & Connections

* **Pin 1 (GND) & Pin 8 ($V_{CC}$):** Connected to the 5V DC ground and positive supply rails.
* **Pin 2 (Trigger) & Pin 6 (Threshold):** Shorted together and connected to the `DATA` (`OUT`) pin of the IR sensor.
* **Pin 3 (Output):** Drives the positive terminal of the 5V buzzer.
* **Pin 4 (Reset):** Tied to $+V_{CC}$ to prevent accidental resets.
* **Pin 5 (Control Voltage):** Decoupled to ground via a $1\,\mu\text{F}$ capacitor.
* **Pin 7 (Discharge):** Left unconnected (inactive in this configuration).

![Circuit Diagram](images/circuit-diagram.jpg)

*Figure 3: Schematic diagram and breadboard wiring layout connecting the IR sensor, NE555 timer IC, strap switch, and buzzer.*

### Working Principle

1. **Helmet Worn, Strap Unfastened (Alert State):** When the rider puts on the helmet, the IR sensor detects the head and pulls the NE555 Trigger (Pin 2) **LOW**. The internal SR flip-flop sets, driving Output (Pin 3) **HIGH** and sounding the buzzer.
2. **Helmet Worn, Strap Fastened (Safe State):** Buckling the chin strap completes the conductive loop across the strap switch, cutting off current to the alert circuit and silencing the buzzer.

![Chin Strap Switch Mechanism](images/strap-switch-mechanism.jpg)

*Figure 4: Conductive wire routing inside the chin strap buckle acting as a closed-loop switch upon fastening.*

---

## Working Model

The hardware prototype integrates the IR sensor inside the inner padding of the helmet while mounting the mini breadboard and buzzer externally for easy inspection and testing.

![Working Model](images/working-model.jpg)

*Figure 5: Top-interior view of the assembled working model showing the IR sensor placement near the rim, external breadboard, and buzzer wiring.*

---

## Project Demonstration

> **[PLACEHOLDER: `images/project-demo.jpg`]**  
> *No live demonstration photograph was included in the presentation slides. Once you capture a photo or GIF showing the active LED/buzzer alert during testing, save it to `images/project-demo.jpg` and remove this blockquote.*

![Project Demonstration](images/project-demo.jpg)

*Figure 6: Live testing demonstrating buzzer activation when the IR sensor detects the rider's head without the chin strap fastened.*

---

## Repository Structure

```text
smart-helmet-alert-system/
├── README.md
├── docs/
│   └── AIC SMART HELMATE.pptx
└── images/
    ├── project-overview.jpg        # Slide 1: Main side-profile helmet photograph
    ├── components.jpg              # Slide 4/5: NE555 IC, IR sensor, and buzzer
    ├── circuit-diagram.jpg         # Slide 7: Schematic & breadboard layout
    ├── strap-switch-mechanism.jpg  # Slide 8: Conductive chin-strap diagram
    ├── working-model.jpg           # Slide 9: Assembled helmet prototype photo
    └── project-demo.jpg            # [Add your live test photo here]
```

---

## Applications & Future Scope

* **Two-Wheeler Road Safety:** Enforces proper chin-strap fastening before starting a ride.
* **Industrial & Construction Zones:** Ensures workers secure safety helmets on hazardous sites.
* **Future Enhancements:** Wireless RF/Bluetooth ignition interlocking with the vehicle, GPS accident alerts, and compact PCB miniaturization inside the helmet shell.

---

## Team Members

* **Sasi Dharan M**
* **Vishnu Prasath S**
* **Niranjan S**
* **Pranav M**

---

## References

* Texas Instruments — *NE555 Precision Timers Datasheet*