---
title: Scope
layout: home
---

# Scope

The goal is to write simple code for an RC plane autopilot that is easy to understand, easy to trace, and follows best practices for safety-critical embedded firmware.
- For small hand-launched and belly landing fixed-wing UAVs
- Automatic takeoff, waypoint following, and landing
- Maximum operation time of 24 hrs
- Maximum distance from home of 50 km
- Maximum altitude of 3 km
- Maximum number of waypoints of 255
- The GCS is mandatory for operation like most military UAVs
- A takeoff point, landing point, and minimum of 1 waypoint required for operation
- Extra servo channels for payloads
- The parameters are loaded through radio. This is more convenient and also safer compared to modifying the firmware because you might make mistake in firmware.
- 8 PWM output channels
- PWM Channel 1, 2, and 3 reserved for aileron, elevator, and throttle. Re-arrange wires to swap, not in software.
- RC Channel 1, 2, 3, 4, 5, and 6 is aileron, elevator, rudder, throttle, manual switch, and mode switch respectively. Change settings in transmitter, not parameters. Only those 6 input channels are supported.
- You can calibrate mag and accel by sending raw data through telemetry... GCS requests or there is a calibration page before the parameters page
- Only the same frequency servos (configured based on HAL)
- No flaps or landing gear, only aileron elevator rudder throttle
- Choose between Optical flow and baro-only operation
- Only Elevator and Rudder control
- If baro-only, you can set landing altitude
- Does not handle when RC transmitter not connected (if flying without autopilot and this happens it would crash anyways)

## Purpose of Scope

I am writing down the scope of the project because it helps me make decisions and save time. 
- Throughout the project I have found myself adding features that turns out I didn't need, and then deleting them later which wastes time. 
- I also don't need to worry about adding more features by limiting the scope.
- Additionally, I have found myself spending hours on the fence between two ways to solve a problem that both work, but I don't know which one I should choose. The solution is to refer back to the scope and requirements list.
