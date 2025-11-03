# FireShield

# RapidFire: Drone Fire-Suppression Payload Module

### Overview

**RapidFire** is a low-cost, modular payload attachment designed for drones to deploy fire retardant or suppressant fluid over small-scale wildfires or ignition points.  
This project focuses on rapid prototyping and CAD-based development of a refillable gravity-drop cartridge, optimized for cost-effectiveness and early wildfire containment.

### Features

- Lightweight 3D-printed frame (PLA/PETG compatible)
- Quick-release mount for standard drone undersides
- Servo-actuated or gravity-drop release mechanism
- Supports refillable bottles or small fluid cartridges
- Designed for easy scaling and open-source adaptation

### Tools & Materials

- **CAD Software:** Fusion 360, Onshape, or SolidWorks  
- **3D Printer:** FDM type with PLA or PETG filament  
- **Servo:** SG90 or MG90S micro servo  
- **Controller:** Arduino Nano or compatible flight controller output (INAV/Betaflight supported)  
- **Fasteners:** M3 bolts, zip ties, or lightweight clamps  
- **Fluid Container:** 250–500 mL plastic bottle (e.g., PET water bottle with 28 mm neck)

## Assembly

1. Mount CRADLE onto PLATE boss (press-fit or M3 screw from bottom).
2. Insert PIN through CRADLE holes so it protrudes both sides; it locks the bottle neck in place.
3. Slide servo BRACKET adjacent to CRADLE so its PIN hole aligns horizontally with CRADLE pin.
4. Fasten servo to BRACKET with servo screws; attach servo horn to pivot point.
5. Fit LATCH arm onto servo horn (small screw). LATCH engages PIN; when servo rotates 90° it pulls PIN out about 8–12 mm.
6. Secure BRACKET to PLATE with two M3 screws or glue; ensure cable routing through slot.
7. Insert bottle into CRADLE (cap toward top). Push bottle down so neck sits behind PIN. Test pull/release action by toggling servo.

## Design for 3D Printing

- Material: PLA for speed; PETG for more durability. Avoid brittle resins for the pin surfaces.
- Layer height: 0.2 mm recommended
- Infill: Plate 20%; Cradle 30%; Latch 50% (more strength on moving part)
- Walls (shells): 3 perimeters
- Supports: Bracket and LATCH may require minimal support under overhangs
- Tolerance Adjustments: Print a 2–3 mm test pin and hole to dial-in fit (tolerance ±0.2 mm)

## Fasteners & Non-printed parts

- Pin: 3 mm stainless steel rod cut to 40 mm length (or use a 3 mm carbon rod)
- Screws: M3 × 8 mm (x6); M2.5 × 8 mm for servo if needed
- Zip ties/Velcro: 2 × 200 mm
- Servo: 9 g micro-servo (e.g., SG90 class) — ensure servo horn geometry matches LATCH pivot

## Wiring & Electronics

- Route servo cable to the PLATE edge and create a recessed channel underneath the Plate for a JST connector (male/female pair) so the payload is fully detachable.
- Reserve area on the Plate (30 × 20 mm) for a small connector and a label.
- If you want a small status LED or button, add a 10 mm × 6 mm pocket for a tactile switch.

### Recommended Fire Suppressant

For safety and testing:
- Use **Class A foam concentrate (1–3%)** diluted in water, or  
- **Water + baking soda** (eco-safe test fluid)  
*Avoid caustic chemicals during prototype testing.*

### How It Works

1. The module mounts beneath the drone using a universal clamp or bolt-on plate.  
2. The container is filled with retardant fluid and sealed to the adapter.  
3. Upon signal from the controller, a servo opens the gate valve or flips the lid, releasing the suppressant over the fire target.  
4. The release rate and spread can be tuned by adjusting nozzle size and servo angle.

### Estimated Performance

| Container Size | Fluid Type | Approx. Coverage Area | Fire Intensity Level |
|----------------|-------------|-----------------------|----------------------|
| 250 mL | Water | ~0.5–1 m² | Ignition spot / small debris fire |
| 500 mL | Foam mix | ~1–2 m² | Small brush or ground fire |
| 1 L | Foam mix | ~2–4 m² | Containment edge or hotspot |

### Simulation & Control

- Prototype compatible with **INAV** autopilot systems or manual control via **Arduino Nano**.  
- Simulate drops using **Mission Planner** or **Gazebo** with GPS-based waypoint triggers.  
- Servo PWM control via `servo_release.ino` in the `/Code/` folder.

### Future Goals

- Integrate temperature/humidity sensors for real-time decision logic.  
- Build a drone swarm model for collaborative fire suppression.  
- Add dashboard integration for monitoring and AI-driven deployment logic.

### License

This project is released under the **MIT License**.  
Attribution is appreciated. Not for live fire use without professional supervision.
