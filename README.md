# Automated-Waste-Segregation-System

An IoT-based automated waste sorter using Arduino Uno and a multi-sensor array to classify refuse into Metallic, Wet, and Dry categories for sustainable waste management.



Overview

Traditional waste management suffers from human error and inefficiency during manual sorting. This project implements an automated "at-source" segregation system that uses physical properties (inductance, moisture, and infrared reflection) to sort waste with high precision.



Hardware Stack

\- Microcontroller: Arduino Uno

\- Sensors: - Inductive Proximity Sensor (Metallic detection)

&nbsp; - IR Sensor (Object detection)

&nbsp; - Raindrop/Soil Moisture Sensor (Wet waste detection)

\- Actuators:

&nbsp; - Servo Motor (Dispensing mechanism)

&nbsp; - 28BYJ-48 Stepper Motor (Sorting platform rotation)

&nbsp; - Active Buzzer (System alerts)

\- Libraries: `CheapStepper`, `Servo`



Logical Workflow

1\. Detection: The system idles until the IR Sensor detects an object.

2\. Analysis:

&nbsp;  - Metallic: The Proximity sensor checks for metal. If detected, the platform rotates 240° CCW.

&nbsp;  - Wet: If not metallic, the moisture sensor takes 3 readings and maps them to a percentage. If moisture > 20%, the platform rotates 240° CW.

&nbsp;  - Dry: If neither condition is met, the waste is treated as dry and dispensed directly.

3\. Action: The Servo Motor opens the lid to drop the waste into the respective bin, and the stepper resets to the home position.



Sustainability Impact

Constructed following the 3Rs Principle (Reduce, Reuse, Recycle), the physical chassis uses repurposed PVC pipes, plywood, and plastic containers to minimize the carbon footprint of the device itself.

![Project Poster](Automated Waste Segregation System.png)



