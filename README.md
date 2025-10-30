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

### File Structure

/CAD/
payload_module_v1.f3d
bottle_adapter_v1.stl
/Code/
servo_release.ino
/Docs/
exploded_view.pdf
dimensions.md

### Tools & Materials
- **CAD Software:** Fusion 360, Onshape, or SolidWorks  
- **3D Printer:** FDM type with PLA or PETG filament  
- **Servo:** SG90 or MG90S micro servo  
- **Controller:** Arduino Nano or compatible flight controller output (INAV/Betaflight supported)  
- **Fasteners:** M3 bolts, zip ties, or lightweight clamps  
- **Fluid Container:** 250–500 mL plastic bottle (e.g., PET water bottle with 28 mm neck)

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
