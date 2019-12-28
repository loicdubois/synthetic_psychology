# synthetic_psychology
## Introduction
Valentino Braitenberg presented in 1986 a simple, yet extremely interesting, way of creating simple robots (vehicles) using direct sensors to actuators wirings. In an increasing level of complexity, various behaviours can be derived from these simple connections, from simply moving around to attraction or agression (vehicles 1 to 3). For the vehicles 4 and 5, nonlinear relation between inputs and outputs, as well as threshold devices (logic gates) allows to introduce **values**, **numbers** and **memory**. 

This type of architecture is a prime example of what is called reactive architecture, in which there is a proximity between sensors and actuators. 

The implementation of the five first Braitenberg's vehicles is proposed for the Thymio 2 Robot using the Aseba language.

## Structure
 - _vehicles.aesl_: Implementation of vehicles inspired by Braitneberg's ideas. The vehicles implemented also cover a more extensive use of the Aseba language for the Thymio 2 robot
   - Reset: By pressing the button in the center
   - Vehicle 1 (yellow): Moving towards the more stimulated (1D only) direction  using the horizontal proximity sensors. Pressing the backward arrow enbles the use of the backward facing sensors (backward LED turned on in the LED circle). Pressing the forward arrow limits the use to the frontward facing sensors (default mode, front and back LEDs turned on in the LED circle)
   - Vehicle 2 (orange): Using the horizontal proximity sensors, agression by pressing the front arrow (default mode, front LED turned on in the LED circle)  or fear by pressing the back arrow (backward LED turned on in the LED circle)
   - Vehicle 3 (red): Rotating by pressing the front and back arrows between love (default mode, front LED turned on in the LED circle), exploration (front left and front right LEDs turned on in the LED circle) and multi-sensors vehicle (front, back, left and right LEDs turned on in the LED circle)
   - Vehicle 4 (pink): Transition from agression to love depending on the maximum proximity sensor value and rotation depending on mic intensity
   - Vehicle 5 (purple): In the defined temperature range, rotates 4 times in one direction and then once in the opposite direction. Rotation during 1 second at a speed related to the ground reflectivity. Time between rotations is a function of the temperature
 - _vehicles_v2.aesl_: Implementation of vehicles following Braitenberg's ideas more closely. The motor output is mostly a scaled sensor input.
   - Vehicle 1 (yellow): Forward speed is proportional to the temperature
   - Vehicle 2 (orange): Using the horizontal proximity sensors, agression by pressing the front arrow (default mode, front LED turned on in the LED circle)  or fear by pressing the back arrow (backward LED turned on in the LED circle)
   - Vehicle 3 (red): Rotating by pressing the front and back arrows between love (default mode, front LED turned on in the LED circle), exploration (front left and front right LEDs turned on in the LED circle) and multi-sensors vehicle (front, back, left and right LEDs turned on in the LED circle)
   - Vehicle 4 (pink): Transition from agression to love depending on the maximum proximity sensor value and rotation depending on mic intensity
   - Vehicle 5 (purple): By pressing the frontward arrow, backward motion when something is detected by the proximity sensors in the front until there is something behind the Thymio, then rotation on itself until there is a path free of obstacles (default mode, back LEDs turned on in the LED circle). Or, by pressing the backward arrow, love until a shock is detected, then fear until the sound intensity drops below a certain threshold (front LEDs turned on in the LED circle)

## Reference
Braitenberg, Valentino. _Vehicles: Experiments in synthetic psychology._ MIT press, 1986.